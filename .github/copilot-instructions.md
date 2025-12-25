# GitHub Copilot Instructions for Nightscout CGM Remote Monitor

## Project Overview
Nightscout (cgm-remote-monitor) is a web-based Continuous Glucose Monitor (CGM) application that allows multiple caregivers to remotely view a patient's glucose data in real time. The server reads from MongoDB and displays glucose values graphically with predictions and alarms.

## Technology Stack
- **Backend**: Node.js with Express.js
- **Database**: MongoDB
- **Frontend**: jQuery, D3.js for visualizations
- **Build Tools**: Webpack, Babel
- **Testing**: Mocha with Should.js assertions
- **API**: RESTful API documented with Swagger

## Code Style Guidelines

### JavaScript Style
- Use **2 spaces** for indentation (no tabs)
- Use **single quotes** for strings
- Use **comma-first style** for object/array literals:
  ```javascript
  var data = {
    value: 'the value'
    , detail: 'the details...'
    , time: Date.now()
  };
  ```
- Include a **space before function parameters**:
  ```javascript
  function boom (name, callback) { }
  ```
- **Name your callback functions**:
  ```javascript
  boom('the name', function afterBoom (result) { });
  ```
- Follow **ESLint** configuration (eslint:recommended with babel-eslint parser)
- Use ES6 features where appropriate (const/let, arrow functions, template literals)

### File Structure
- **lib/** - Core application logic
  - `lib/plugins/` - Plugin system for features
  - `lib/api/` - REST API endpoints
  - `lib/server/` - Server configuration
  - `lib/client/` - Client-side code
- **tests/** - Test files (*.test.js)
- **static/** - Static assets
- **views/** - EJS templates

## Development Workflow

### Branch Strategy
- Develop on the `dev` branch
- All pull requests should target `dev`
- `master` branch is only for distributing tested releases

### Local Development
1. Copy `my.env.template` to `my.env` and configure
2. Run with `npm run dev` (uses nodemon for auto-restart)
3. Production mode: Use `my.prod.env` and `npm run prod`
4. Set `INSECURE_USE_HTTP=true` for local HTTP development

### Testing
- Test framework: **Mocha** with **Should.js**
- Run tests: `npm test`
- Coverage: `npm run coverage`
- All tests are in `tests/*.test.js`
- Tests use fixtures from `tests/fixtures/`

### Building
- Build for production: `npm run bundle`
- Build for development: `npm run bundle-dev`
- Analyze bundle: `npm run bundle-analyzer`

## Plugin Architecture
- Nightscout uses a plugin system for features
- Most new features should be implemented as plugins
- Plugins live in `lib/plugins/`
- Each plugin has a clear separation of concerns
- Avoid modifying existing plugins when adding new features

## API Guidelines
- REST API follows Swagger documentation (see `/api-docs` when running)
- All dates must be **ISO-8601 format**
- Dates in URLs must be properly URL-encoded (watch for '+' signs)
- API documentation files: `swagger.json` and `swagger.yaml`

## Common Patterns

### Error Handling
- Use Node.js error-first callbacks: `callback(err, result)`
- Handle errors appropriately in async operations
- Log errors for debugging

### Data Models
- SGV (Sensor Glucose Values) - main glucose readings
- Device Status - device information
- Treatments - insulin, carbs, and other treatments
- Profile - user settings and preferences

### Security
- API endpoints require authentication
- Use `API_SECRET` for authentication
- Default roles configured via `authDefaultRoles`
- Helmet.js used for security headers

## Testing Patterns
- Use `require('should')` for assertions
- Use `supertest` for API testing
- Use `benv` for browser environment simulation
- Mock MongoDB with `mongomock`
- Test files follow naming: `featurename.test.js`

Example test structure:
```javascript
'use strict';

require('should');
var request = require('supertest');

describe('Feature Name', function () {
  this.timeout(10000);
  var self = this;

  beforeEach(function (done) {
    // Setup
    done();
  });

  it('should do something', function (done) {
    // Test implementation
    done();
  });
});
```

## Important Considerations
- This is a medical application - be careful with glucose calculations
- Maintain backward compatibility with existing deployments
- Consider the #WeAreNotWaiting community impact
- Test thoroughly before submitting PRs
- Document any new environment variables
- Update swagger documentation for API changes

## Dependencies
- Node.js: ^10.15.2 || ^8.15.1
- npm: ^6.4.1
- MongoDB connection required for operation

## Environment Variables
Key environment variables (see `my.env.template`):
- `MONGO_CONNECTION` - MongoDB connection string
- `API_SECRET` - Secret for API authentication
- `ENABLE` - Space-separated list of enabled plugins
- `NODE_ENV` - 'development' or 'production'
- `INSECURE_USE_HTTP` - Set to 'true' for local HTTP development

## When Suggesting Code
1. Follow the comma-first style for objects and arrays
2. Use 2-space indentation consistently
3. Add spaces before function parameters
4. Name callback functions descriptively
5. Use single quotes for strings
6. Consider plugin architecture for new features
7. Write tests for new functionality
8. Update Swagger docs for API changes
9. Respect the existing code patterns and structure
10. Remember this is a community-maintained healthcare application
