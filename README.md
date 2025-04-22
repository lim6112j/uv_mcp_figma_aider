# mcp setting for aider with claude desktop app
1. claude desktop install
2. desktop settings - mcp enable
3. ~/Library/Application Support/Claude/claude_desktop_config.json edit
echo '{
  "mcpServers": {
    "figma-mcp": {
      "command": "npx",
      "args": ["figma-mcp"],
      "env": {
        "FIGMA_API_KEY": "<YOUR_API_KEY>"
      }
    }
  }
}' > ~/Library/Application\ Support/Claude/claude_desktop_config.json
4. npm install -g mcpm-aider
5. mcpm-aider start-bridge
6. edit ~/.aider.model.settings.yml

```
- name: anthropic/claude-3-5-sonnet-latest
  streaming: false
  extra_params:
    max_tokens: 8192
    model: openai/claude-3-5-sonnet-latest
    api_key: this-key-is-used-by-the-bridge
    api_base: http://localhost:8000/v1/
```
7. restart claude desktopapp
8. aider --model anthropic/claude-3-5-sonnet-latest
