# Claude Code Plugin Marketplace

This is a marketplace for Claude Code plugins.

## Structure

- `.claude-plugin/marketplace.json` - Main marketplace configuration
- `plugins/` - Directory for plugin sources (optional, if hosting plugins locally)

## Adding This Marketplace

To add this marketplace to Claude Code:

```bash
/plugin marketplace add <your-github-username>/<repo-name>
```

Or if using a different git service:

```bash
/plugin marketplace add <git-url>
```

## Adding Plugins

Edit `.claude-plugin/marketplace.json` and add plugins to the `plugins` array:

```json
{
  "plugins": [
    {
      "name": "my-plugin",
      "source": "./plugins/my-plugin",
      "description": "Description of my plugin",
      "version": "1.0.0",
      "author": {
        "name": "Your Name",
        "email": "your.email@example.com"
      },
      "keywords": ["keyword1", "keyword2"],
      "license": "MIT"
    }
  ]
}
```

### Plugin Source Options

1. **Local relative path:**
   ```json
   "source": "./plugins/my-plugin"
   ```

2. **GitHub repository:**
   ```json
   "source": {
     "source": "github",
     "repo": "owner/repo"
   }
   ```

3. **Git URL:**
   ```json
   "source": {
     "source": "url",
     "url": "https://github.com/owner/repo.git"
   }
   ```

## Installing Plugins

Users can install plugins from your marketplace using:

```bash
/plugin install plugin-name@marketplace-name
```

## Plugin Structure

Each plugin should follow the Claude Code plugin structure. See [Claude Code Plugin Documentation](https://code.claude.com/docs/en/plugins) for details.
