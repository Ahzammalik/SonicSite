# Package Scripts Documentation

This document explains all available npm scripts in the CopySonic AI project.

## Development Scripts

### `npm run dev`
Starts the development server with hot reload enabled.
- Runs both frontend (Vite) and backend (Express) simultaneously
- Frontend available at `http://localhost:5000`
- Backend API available at `http://localhost:5000/api`
- Hot Module Replacement (HMR) for instant updates

### `npm start`
Production start script (same as `npm run dev` currently).

## Build Scripts

### `npm run build`
Creates optimized production build.
- Compiles TypeScript to JavaScript
- Bundles and minifies frontend assets
- Optimizes images and static files
- Outputs to `dist/` directory

### `npm run preview`
Serves the production build locally for testing.
- Useful for testing the production build before deployment
- Runs on `http://localhost:4173` by default

## Code Quality Scripts

### `npm run lint`
Runs ESLint to check code quality and style.
- Checks for syntax errors
- Enforces coding standards
- Identifies potential bugs

### `npm run lint:fix`
Automatically fixes ESLint issues where possible.

### `npm run format`
Formats code using Prettier.
- Ensures consistent code formatting
- Works on all TypeScript, JavaScript, CSS, and Markdown files

### `npm run format:check`
Checks if code is properly formatted without making changes.

## Type Checking Scripts

### `npm run type-check`
Runs TypeScript compiler to check for type errors.
- No output files generated
- Only checks for type safety
- Useful in CI/CD pipelines

### `npm run type-check:watch`
Runs TypeScript compiler in watch mode.
- Continuously checks for type errors as you code
- Useful during development

## Database Scripts

### `npm run db:generate`
Generates database migration files using Drizzle.
- Creates SQL migration files based on schema changes
- Must be run after modifying database schemas

### `npm run db:migrate`
Applies database migrations.
- Runs pending migrations against the database
- Updates database schema to match code

### `npm run db:push`
Pushes schema changes directly to database (development only).
- Skips migration files
- Useful for rapid prototyping
- Not recommended for production

### `npm run db:studio`
Opens Drizzle Studio for database management.
- Web-based database browser
- Allows viewing and editing data
- Available at `http://localhost:4000`

## Testing Scripts

### `npm test`
Runs the test suite.
- Executes all unit and integration tests
- Shows coverage report
- Exits with error code if tests fail

### `npm run test:watch`
Runs tests in watch mode.
- Re-runs tests when files change
- Useful during development

### `npm run test:coverage`
Runs tests with detailed coverage report.
- Generates HTML coverage report
- Shows which lines are not covered by tests

### `npm run test:ui`
Opens testing UI for interactive test running.
- Visual test runner
- Useful for debugging tests

## Deployment Scripts

### `npm run deploy`
Deploys the application (if deployment is configured).
- Builds the production version
- Deploys to configured hosting service
- May require environment variables

### `npm run deploy:staging`
Deploys to staging environment.
- Useful for testing before production deployment

## Utility Scripts

### `npm run clean`
Cleans build artifacts and temporary files.
- Removes `dist/`, `build/`, and cache directories
- Useful when builds are corrupted

### `npm run update-deps`
Updates all dependencies to latest versions.
- Updates package.json
- Runs security audit
- Tests that everything still works

### `npm run security-audit`
Runs security audit on dependencies.
- Identifies known vulnerabilities
- Suggests fixes for security issues

## Environment-Specific Scripts

### Development
```bash
npm run dev          # Start development server
npm run type-check   # Check types during development
npm run lint         # Check code quality
```

### Testing
```bash
npm test             # Run all tests
npm run test:watch   # Test in watch mode
npm run test:coverage # Get coverage report
```

### Production Build
```bash
npm run build        # Create production build
npm run preview      # Test production build locally
npm run deploy       # Deploy to production
```

### Database Management
```bash
npm run db:generate  # Create migration files
npm run db:migrate   # Apply migrations
npm run db:studio    # Open database browser
```

## Common Workflows

### Starting Development
```bash
npm install          # Install dependencies
npm run dev          # Start development server
```

### Before Committing
```bash
npm run lint:fix     # Fix linting issues
npm run format       # Format code
npm run type-check   # Check types
npm test             # Run tests
```

### Preparing for Production
```bash
npm run build        # Create production build
npm run preview      # Test build locally
npm run security-audit # Check for vulnerabilities
```

### Database Changes
```bash
# After modifying schema files:
npm run db:generate  # Generate migration
npm run db:migrate   # Apply migration
```

## Environment Variables

Some scripts may require environment variables:

- `NODE_ENV`: Set to 'development', 'production', or 'test'
- `DATABASE_URL`: PostgreSQL connection string
- `SESSION_SECRET`: Secret for session encryption

## Troubleshooting

### Common Issues

**Build Fails**
```bash
npm run clean        # Clean build artifacts
npm install          # Reinstall dependencies
npm run build        # Try build again
```

**Type Errors**
```bash
npm run type-check   # See all type errors
# Fix errors in code
npm run type-check   # Verify fixes
```

**Test Failures**
```bash
npm run test:watch   # Run tests in watch mode
# Fix failing tests
npm test             # Verify all tests pass
```

**Database Issues**
```bash
npm run db:studio    # Open database browser
# Check database state
npm run db:migrate   # Apply pending migrations
```