# Deployment Guide

This guide covers different deployment options for CopySonic AI.

## 🚀 Quick Deployment Options

### 1. Replit Deployment (Recommended)

Replit provides the easiest deployment option with built-in hosting and database.

#### Steps:
1. **Import to Replit**
   ```bash
   # On Replit, import from GitHub URL:
   https://github.com/yourusername/copysonic-ai
   ```

2. **Configure Environment Variables**
   In Replit Secrets tab, add:
   ```
   DATABASE_URL=your_postgresql_url
   SESSION_SECRET=your_session_secret
   NODE_ENV=production
   ```

3. **Deploy**
   - Click "Deploy" button in Replit
   - Choose "Autoscale" for automatic scaling
   - Your app will be available at `yourappname.youruser.repl.co`

#### Benefits:
- Zero configuration deployment
- Built-in PostgreSQL database
- Automatic SSL certificates
- Custom domain support
- Integrated monitoring

### 2. Vercel Deployment

Perfect for frontend-focused deployments with serverless functions.

#### Steps:
1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Configure vercel.json**
   ```json
   {
     "functions": {
       "server/index.ts": {
         "runtime": "@vercel/node"
       }
     },
     "rewrites": [
       {
         "source": "/api/(.*)",
         "destination": "/server/index.ts"
       },
       {
         "source": "/(.*)",
         "destination": "/client/$1"
       }
     ]
   }
   ```

3. **Deploy**
   ```bash
   vercel --prod
   ```

### 3. Railway Deployment

Great for full-stack applications with PostgreSQL.

#### Steps:
1. **Connect GitHub Repository**
   - Go to [Railway](https://railway.app)
   - Connect your GitHub account
   - Select the repository

2. **Add PostgreSQL Service**
   - Click "New Service" → "PostgreSQL"
   - Railway will provide DATABASE_URL automatically

3. **Configure Environment Variables**
   ```
   SESSION_SECRET=your_session_secret
   NODE_ENV=production
   ```

4. **Deploy**
   - Railway automatically builds and deploys
   - Custom domain available in settings

### 4. DigitalOcean App Platform

Scalable deployment with built-in database options.

#### Steps:
1. **Create App**
   - Go to DigitalOcean App Platform
   - Connect GitHub repository

2. **Configure Build Settings**
   ```yaml
   name: copysonic-ai
   services:
   - name: web
     source_dir: /
     github:
       repo: yourusername/copysonic-ai
       branch: main
     run_command: npm start
     environment_slug: node-js
     instance_count: 1
     instance_size_slug: basic-xxs
   databases:
   - name: db
     engine: PG
     version: "13"
   ```

3. **Set Environment Variables**
   - Add SESSION_SECRET in app settings
   - DATABASE_URL is provided automatically

### 5. Heroku Deployment

Traditional platform-as-a-service deployment.

#### Steps:
1. **Install Heroku CLI**
   ```bash
   npm install -g heroku
   ```

2. **Create Heroku App**
   ```bash
   heroku create copysonic-ai
   heroku addons:create heroku-postgresql:hobby-dev
   ```

3. **Configure Environment**
   ```bash
   heroku config:set SESSION_SECRET=your_session_secret
   heroku config:set NODE_ENV=production
   ```

4. **Deploy**
   ```bash
   git push heroku main
   ```

## 🔧 Manual Server Deployment

For VPS or dedicated server deployment.

### Prerequisites
- Ubuntu 20.04+ or similar Linux distribution
- Node.js 18+
- PostgreSQL 13+
- Nginx (recommended)
- SSL certificate (Let's Encrypt recommended)

### Steps:

1. **Server Setup**
   ```bash
   # Update system
   sudo apt update && sudo apt upgrade -y
   
   # Install Node.js
   curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
   sudo apt-get install -y nodejs
   
   # Install PostgreSQL
   sudo apt install postgresql postgresql-contrib
   
   # Install Nginx
   sudo apt install nginx
   
   # Install PM2 for process management
   sudo npm install -g pm2
   ```

2. **Database Setup**
   ```bash
   # Create database and user
   sudo -u postgres psql
   CREATE DATABASE copysonic_ai;
   CREATE USER copysonicuser WITH PASSWORD 'your_password';
   GRANT ALL PRIVILEGES ON DATABASE copysonic_ai TO copysonicuser;
   \q
   ```

3. **Application Deployment**
   ```bash
   # Clone repository
   git clone https://github.com/yourusername/copysonic-ai.git
   cd copysonic-ai
   
   # Install dependencies
   npm ci --production
   
   # Build application
   npm run build
   
   # Set up environment variables
   cp .env.example .env
   # Edit .env with your configuration
   
   # Run database migrations
   npm run db:migrate
   ```

4. **Process Management**
   ```bash
   # Create PM2 ecosystem file
   cat > ecosystem.config.js << EOF
   module.exports = {
     apps: [{
       name: 'copysonic-ai',
       script: 'npm',
       args: 'start',
       env: {
         NODE_ENV: 'production',
         PORT: 3000
       }
     }]
   };
   EOF
   
   # Start with PM2
   pm2 start ecosystem.config.js
   pm2 save
   pm2 startup
   ```

5. **Nginx Configuration**
   ```nginx
   # /etc/nginx/sites-available/copysonic-ai
   server {
       listen 80;
       server_name yourdomain.com www.yourdomain.com;
       
       location / {
           proxy_pass http://localhost:3000;
           proxy_http_version 1.1;
           proxy_set_header Upgrade $http_upgrade;
           proxy_set_header Connection 'upgrade';
           proxy_set_header Host $host;
           proxy_set_header X-Real-IP $remote_addr;
           proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
           proxy_set_header X-Forwarded-Proto $scheme;
           proxy_cache_bypass $http_upgrade;
       }
   }
   ```

6. **SSL Setup with Let's Encrypt**
   ```bash
   # Install certbot
   sudo apt install certbot python3-certbot-nginx
   
   # Get SSL certificate
   sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com
   
   # Enable and start nginx
   sudo ln -s /etc/nginx/sites-available/copysonic-ai /etc/nginx/sites-enabled/
   sudo systemctl enable nginx
   sudo systemctl restart nginx
   ```

## 🌐 Domain and DNS Setup

### Custom Domain Configuration

1. **Buy Domain**
   - Use providers like Namecheap, GoDaddy, or Cloudflare

2. **Configure DNS**
   ```
   Type    Name    Value
   A       @       your_server_ip
   A       www     your_server_ip
   CNAME   api     @
   ```

3. **SSL Certificate**
   - Let's Encrypt (free) or CloudFlare (free with proxy)
   - Ensure HTTPS redirect is enabled

## 📊 Monitoring and Analytics

### Application Monitoring
```bash
# Install monitoring tools
npm install --save @sentry/node
npm install --save newrelic
```

### Google Analytics Setup
1. Create GA4 property
2. Add tracking code to `client/index.html`
3. Configure goals and conversions

### Performance Monitoring
- Use tools like Lighthouse for performance audits
- Monitor Core Web Vitals
- Set up uptime monitoring with services like UptimeRobot

## 🔐 Security Considerations

### Environment Variables
- Never commit `.env` files
- Use secure secrets management
- Rotate secrets regularly

### Database Security
- Use strong passwords
- Enable SSL connections
- Regular backups
- Access restrictions

### Application Security
- Keep dependencies updated
- Use HTTPS everywhere
- Implement rate limiting
- Regular security audits

## 🚨 Troubleshooting

### Common Issues

**Build Failures**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
npm run build
```

**Database Connection Issues**
```bash
# Check database status
sudo systemctl status postgresql
# Check connection string in .env
```

**Performance Issues**
```bash
# Monitor with PM2
pm2 monit
# Check logs
pm2 logs copysonic-ai
```

**SSL Certificate Issues**
```bash
# Renew certificate
sudo certbot renew
# Check certificate status
sudo certbot certificates
```

## 📋 Pre-Deployment Checklist

- [ ] Environment variables configured
- [ ] Database migrations applied
- [ ] SSL certificates installed
- [ ] Domain DNS configured
- [ ] Google Analytics set up
- [ ] AdSense code implemented
- [ ] Performance optimization applied
- [ ] Security headers configured
- [ ] Backup strategy implemented
- [ ] Monitoring tools configured

## 🔄 Continuous Deployment

### GitHub Actions Setup
The included `.github/workflows/ci.yml` provides:
- Automated testing
- Security audits
- Build verification
- Staging deployment
- Production deployment

### Environment-Specific Configurations
- **Development**: Full debugging, hot reload
- **Staging**: Production-like environment for testing
- **Production**: Optimized build, monitoring enabled

## 📈 Scaling Considerations

### Horizontal Scaling
- Load balancers (Nginx, AWS ALB)
- Multiple application instances
- Database read replicas
- CDN for static assets

### Vertical Scaling
- Increase server resources
- Optimize database queries
- Implement caching (Redis)
- Asset optimization

## 💰 Cost Optimization

### Free Tier Options
- **Replit**: Free tier with custom domain
- **Vercel**: Hobby plan for personal projects
- **Railway**: $5/month for starter projects
- **DigitalOcean**: $5/month droplet

### Production Scaling
- Monitor usage and scale accordingly
- Use CDNs for static assets
- Implement efficient caching
- Optimize database queries

Choose the deployment method that best fits your needs, budget, and technical requirements.