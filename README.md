# Sora Queue Manager - Remote Configuration

This repository hosts the remote configuration for the [Sora Queue Manager](https://github.com/adntgv/sora-queue) Chrome extension.

## Purpose

This separate public repository allows the extension to fetch configuration updates while keeping the main source code repository private.

## How It Works

1. The extension fetches `config.json` from this repository
2. Configuration is cached locally for 24 hours
3. Falls back to default values if fetch fails

## Updating Configuration

### Quick Edit (GitHub Web)
1. Click on `config.json`
2. Click the pencil icon to edit
3. Make your changes
4. Commit directly to main branch

### Local Edit
```bash
# Clone this repo
git clone https://github.com/YOUR_USERNAME/sora-queue-config.git
cd sora-queue-config

# Edit configuration
nano config.json

# Commit and push
git add config.json
git commit -m "Update config"
git push origin main
```

## Configuration Options

See the main repository documentation for detailed configuration options.

### Features
- `teamButtons`: Show/hide team features
- `studioBanner`: Show/hide promotional banner
- `sidePanel`: Enable/disable Chrome side panel
- `analytics`: Enable/disable analytics

### Limits
- `maxConcurrent`: Maximum concurrent generations
- `maxQueueSize`: Maximum queue size
- `maxPromptLength`: Maximum prompt character length

### Timing
- `checkInterval`: Queue check interval (ms)
- `submissionCooldown`: Submission cooldown (ms)
- `retryDelay`: Retry delay (ms)
- `maxRetries`: Maximum retry attempts

### UI
- `calendlyUrl`: Calendly booking link
- `bannerText`: Promotional banner text
- `bannerCta`: Banner call-to-action

## Important Notes

- Changes take up to 24 hours to propagate (cache TTL)
- Always validate JSON before committing
- The extension falls back to defaults if config is invalid
