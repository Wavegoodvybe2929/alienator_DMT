# VS Code AI Assistant Extension

[![VS Marketplace](https://img.shields.io/vscode-marketplace/v/yourpublisher.vscode-ai-assistant.svg)](https://marketplace.visualstudio.com/items?itemName=yourpublisher.vscode-ai-assistant)  
[![Installs](https://img.shields.io/vscode-marketplace/i/yourpublisher.vscode-ai-assistant.svg)](https://marketplace.visualstudio.com/items?itemName=yourpublisher.vscode-ai-assistant)  
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Overview

The VS Code AI Assistant is a powerful extension that integrates Puter.js AI capabilities to provide intelligent code assistance through a chat interface directly within Visual Studio Code. Leveraging Puter.js, this extension offers free access to multiple advanced AI models such as GPT-4o, Claude Sonnet, and others, without the need for API keys or subscriptions. It enables developers to get real-time code explanations, bug detection, optimizations, documentation generation, and more, all while seamlessly incorporating code context from your workspace.

Key benefits include:
- **No API Key Management**: Users don't need personal OpenAI or Claude API keys—Puter.js handles it via its "User Pays" model.
- **Multiple AI Models**: Switch between models like GPT-4o, Claude 3.5 Sonnet, o1, o3-mini, and DALL-E 3.
- **Persistent Storage**: Chat history saved using Puter.js KV storage.
- **Code Context Integration**: Automatically includes selected code, file content, and workspace details in queries.
- **Free and Accessible**: No cost barriers, making AI assistance available to all developers.

This extension was developed following a 6-week implementation plan, focusing on ease of use, performance, and integration with VS Code APIs.

## Features

- **Chat Interface**: Interactive chat panel for conversing with AI models.
  - Supports text messages, code blocks with syntax highlighting, file references, and inline suggestions.
  - Model selection dropdown (e.g., GPT-4o, Claude Sonnet).
  - Interactive elements: Apply code suggestions directly to the editor, copy code blocks, save conversations.
- **Code Assistance**:
  - Explain selected code.
  - Detect bugs and suggest fixes.
  - Optimize code for performance.
  - Generate documentation and comments.
  - Refactor code structures.
  - Create boilerplate code, test cases, and configuration templates.
- **Context-Aware Functionality**:
  - Extracts current file content, selected text, workspace structure, and relevant files.
  - Conversation threading and history search.
- **Advanced Integration**:
  - Uses VS Code APIs for hover suggestions, custom commands, and editor interactions.
  - Error handling for network issues, rate limits, and service availability.
- **UI/UX**:
  - Integrates with VS Code themes.
  - Responsive design, loading indicators, and typing animations.

## Installation

### From VS Code Marketplace
1. Open Visual Studio Code.
2. Go to the Extensions view (Ctrl+Shift+X or Cmd+Shift+X on macOS).
3. Search for "VS Code AI Assistant".
4. Click Install.

### From VSIX File (for Development or Offline Installation)
1. Download the `.vsix` file from the [releases page](https://github.com/yourusername/vscode-ai-assistant/releases).
2. In VS Code, go to Extensions view > More Actions (...) > Install from VSIX...
3. Select the downloaded file.

### Prerequisites
- Visual Studio Code version 1.60.0 or higher.
- Internet connection for Puter.js AI services (no API keys required).

## Usage

### Opening the Chat
- Use the command palette (Ctrl+Shift+P or Cmd+Shift+P): Type "AI Assistant: Open Chat".
- Or, use the status bar icon (if configured) or keybinding.

### Commands
The extension provides several commands accessible via the command palette:
- **AI Assistant: Open Chat**: Opens the chat panel.
- **AI Assistant: Explain Code**: Explains the selected code in the editor.
- **AI Assistant: Generate Tests**: Generates test cases for selected code.
- **AI Assistant: Optimize Code**: Suggests optimizations for selected code.
- **AI Assistant: Generate Documentation**: Creates docs for selected code.

### Chat Interaction
1. Select a model from the dropdown (default: GPT-4o).
2. Type your query in the input field and press Send (or Enter).
3. The AI responds with formatted text/code.
4. For code responses: Click "Apply Code" to insert into the active editor.
5. Save conversations using the "Save Conversation" button—stored via Puter.js KV.

### Configuration
Customize the extension via VS Code Settings (File > Preferences > Settings > Extensions > AI Assistant):
- `aiAssistant.defaultModel`: Default AI model (e.g., "gpt-4o").
- `aiAssistant.maxTokens`: Maximum tokens for responses (default: 2000).
- `aiAssistant.includeFileContext`: Include file context in queries (default: true).
- `aiAssistant.autoSaveConversations`: Automatically save chat history (default: true).

## Development and Contributing

### Project Structure
```
vscode-ai-assistant/
├── src/
│   ├── extension.ts        # Main entry point
│   ├── chatProvider.ts     # Chat webview management
│   ├── aiService.ts        # Puter.js AI integration
│   └── utils/
│       ├── codeAnalysis.ts # Code context extraction
│       └── messageFormat.ts # Message formatting
├── webview/                # Chat UI files
│   ├── index.html
│   ├── script.js
│   └── style.css
├── media/                  # Icons and assets
├── package.json            # Extension metadata
├── tsconfig.json           # TypeScript configuration
└── README.md               # This file
```

### Building Locally
1. Clone the repository: `git clone https://github.com/yourusername/vscode-ai-assistant.git`
2. Install dependencies: `npm install`
3. Compile: `npm run compile`
4. Run in debug mode: Press F5 in VS Code (opens a new window with the extension loaded).

### Contributing
We welcome contributions! Please follow these steps:
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -m "Add new feature"`
4. Push to the branch: `git push origin feature/new-feature`
5. Open a Pull Request.

Report issues or suggest features via [GitHub Issues](https://github.com/yourusername/vscode-ai-assistant/issues).

### Testing
- Unit tests: Core functions in `aiService.ts` and utils.
- Integration tests: VS Code API interactions.
- Run tests: `npm test`

## Known Issues
- Puter.js availability: Dependent on Puter.js service; handle offline scenarios gracefully.
- Large files: Context inclusion may truncate for very large files.
- Model limitations: Some models (e.g., DALL-E) may not support code-specific tasks.

## Changelog
See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Built with [Puter.js](https://puter.com/) for AI integration.
- Inspired by VS Code extension best practices from Microsoft documentation.

For more details, visit the [project repository](https://github.com/yourusername/vscode-ai-assistant).