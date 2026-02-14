# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the documentation site for Mascotbot SDK, built with Mintlify - a modern documentation framework. The site documents the Mascotbot AI-powered mascots SDK with real-time lip-sync technology for React and React Native applications.

## Development Commands

```bash
# Install Mintlify CLI globally (required for development)
npm i -g mintlify

# Run development server locally
mintlify dev

# If dev server fails to start
mintlify install
```

## Architecture & Structure

### Technology Stack
- **Documentation Framework**: Mintlify with MDX support
- **Theme**: Maple theme with light/dark mode
- **API Documentation**: OpenAPI 3.1.0 specification
- **Content Format**: MDX (Markdown + JSX components)

### Directory Structure
- `/api-reference/` - API documentation and OpenAPI spec
  - `openapi.yaml` - Viseme Prediction API specification
  - `endpoint/` - Individual endpoint documentation
  - `lipsync-integration.mdx` - Integration examples
- `/libraries/` - SDK documentation
  - `react-sdk.mdx` - React SDK guide with WebGL2 renderer
  - `react-native-sdk.mdx` - React Native SDK guide
- `/mascots/` - Pre-built mascot gallery
- `/images/` - Documentation assets and screenshots
- `/logo/` - Brand assets (light/dark variants)

### Navigation Configuration
The site has two main dropdown sections configured in `docs.json`:
1. **Documentation** - Getting started, SDK libraries, ready-made mascots
2. **API Reference** - API introduction, endpoints, integration examples

## Key Development Tasks

### Adding Documentation Pages
1. Create MDX file in appropriate directory
2. Add frontmatter with title, description, and icon
3. Update navigation in `docs.json` under appropriate group
4. Preview locally with `mintlify dev`

### Updating API Documentation
1. Modify `api-reference/openapi.yaml` for API spec changes
2. Update endpoint MDX files in `api-reference/endpoint/`
3. Ensure examples match the OpenAPI specification

### Working with Code Examples
- Use proper language identifiers for syntax highlighting
- Include complete, runnable examples
- Test code examples for accuracy
- Show both TypeScript and JavaScript variants where applicable

### Testing Changes
1. Always preview with `mintlify dev` before committing
2. Check both light and dark theme appearance
3. Verify all links and images load correctly
4. Test interactive MDX components render properly
5. Ensure responsive design works on mobile viewports

## Content Guidelines

### MDX Best Practices
- Use semantic headings (start with ##, not #)
- Include descriptive frontmatter for SEO
- Use Mintlify components: Note, Warning, Tip, Info callouts
- Add code examples with proper syntax highlighting
- Include screenshots and diagrams where helpful

### API Documentation Standards
- Keep OpenAPI spec synchronized with actual API
- Document all parameters, request/response bodies
- Include realistic example values
- Document error responses and status codes
- Show streaming (SSE) examples for real-time endpoints

### SDK Documentation Focus
- Provide complete setup instructions
- Show common use cases with code examples
- Document all hooks and components
- Include troubleshooting sections
- Explain performance considerations (e.g., WebGL2 renderer)

## Important Notes

- The main branch auto-deploys via GitHub App integration
- Mintlify provides built-in search functionality
- External links configured: support email, Twitter/X, main website
- The site uses contextual menu with copy, view, ChatGPT, and Claude options
- Focus on accuracy - this is the primary resource for developers using Mascotbot SDK