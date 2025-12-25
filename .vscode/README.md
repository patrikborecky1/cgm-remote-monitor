# VS Code Configuration for Nightscout

This directory contains VS Code workspace configuration files for the Nightscout project.

## Files

- **settings.json** - Editor settings optimized for Nightscout development
- **extensions.json** - Recommended VS Code extensions
- **launch.json** - Debug configurations for running and testing

## Prerequisites for Debug Configurations

The debug configurations in `launch.json` require environment files:

1. **my.env** - For development mode
   - Copy `my.env.template` to `my.env` and configure
   
2. **my.prod.env** - For production mode (optional)
   - Copy `my.env.template` to `my.prod.env`
   - Change `NODE_ENV=production`
   
3. **test.env** - For running tests
   - Create this file with test-specific environment variables
   - See `my.env.template` for reference

## Usage

These files are automatically loaded by VS Code when you open the project. No additional configuration needed!

For more information, see the main documentation:
- [AI Agents Quick Start (Czech)](../NÁVOD-AI-AGENTI.md)
- [AI Agents Full Guide](../docs/AI-AGENTS-VSCODE.md)
