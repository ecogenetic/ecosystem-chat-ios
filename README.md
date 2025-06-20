# ecoChat

A modern ChatGPT-like iOS app built with SwiftUI that supports multiple AI backends including OpenAI Cloud, local Ollama, and Ecogentic services.

## Features

- **Multi-Backend Support**: Switch between OpenAI Cloud, local Ollama, and Ecogentic AI services
- **Real-time Streaming**: Live token streaming for word-by-word responses with typing indicators
- **Modern Chat Interface**: Role-based message bubbles with markdown and code block rendering
- **Secure Storage**: API keys and settings stored securely in iOS Keychain
- **Dark Theme**: Beautiful dark-themed interface optimized for readability
- **Auto-scroll**: Automatic scrolling to latest messages
- **Message Status**: Visual indicators for message sending, received, streaming, and error states
- **Conversation History**: Maintains context across multiple messages

## Requirements

- iOS 18.5+
- Xcode 16.4+
- Swift 5.0+

## Setup

### OpenAI Cloud
1. Get an API key from [OpenAI](https://platform.openai.com/api-keys)
2. In the app, go to Settings → Backend → "OpenAI"
3. Enter your API key and model name (default: gpt-4)

### Local Ollama
1. Install [Ollama](https://ollama.ai/)
2. Pull a model: `ollama pull llama3.2`
3. In the app, go to Settings → Backend → "Ollama"
4. Enter the host URL (default: http://localhost:11434/v1/chat/completions)
5. Enter the model name (default: llama3.2)

### Ecogentic AI
1. In the app, go to Settings → Backend → "Ecogentic"
2. The host URL is pre-configured (https://meserver.ecosystem.ai/api/v1/chat/completions)
3. Enter the model name (default: ecosystem.Ai)

## Architecture

The app follows MVVM (Model-View-ViewModel) architecture with clean separation of concerns:

- **Models**: Data structures for messages, settings, backend types, and authentication
- **ViewModels**: Business logic and state management for chat and settings
- **Views**: SwiftUI user interface components with custom theming
- **Services**: Network communication, keychain storage, and streaming functionality

## Project Structure

```
ecoChat/
├── Models/
│   ├── BackendType.swift          # Backend configuration and defaults
│   ├── ChatMessage.swift          # Message data structure and status
│   ├── ChatSettings.swift         # App settings and validation
│   └── LoginResponse.swift        # Authentication response models
├── ViewModels/
│   ├── ChatViewModel.swift        # Chat state and message handling
│   └── SettingsViewModel.swift    # Settings management
├── Views/
│   ├── ChatView.swift             # Main chat interface
│   ├── MessageBubbleView.swift    # Individual message display
│   ├── ComposerView.swift         # Message input component
│   ├── SettingsView.swift         # Settings configuration
│   └── Theme.swift                # App theming and styling
├── Services/
│   ├── ChatService.swift          # API communication and streaming
│   ├── KeychainService.swift      # Secure credential storage
│   └── StreamingService.swift     # Real-time response streaming
├── ContentView.swift              # Main app container
└── ecoChatApp.swift               # App entry point
```

## Backend Support

### OpenAI Cloud
- **URL**: https://api.openai.com/v1/chat/completions
- **Default Model**: gpt-4
- **Authentication**: Bearer token (API key)

### Local Ollama
- **URL**: http://localhost:11434/v1/chat/completions
- **Default Model**: llama3.2
- **Authentication**: None (local)

### Ecogentic AI
- **URL**: https://meserver.ecosystem.ai/api/v1/chat/completions
- **Default Model**: ecosystem.Ai
- **Authentication**: None (public service)

## Features in Detail

### Message Streaming
- Real-time token streaming with typing indicators
- Support for markdown rendering in responses
- Code block syntax highlighting
- Message status tracking (sending, sent, received, streaming, error)

### Security
- API keys stored securely in iOS Keychain
- No hardcoded secrets in the codebase
- Secure network communication with proper headers

### User Experience
- Dark theme optimized for readability
- Smooth animations and transitions
- Auto-scroll to latest messages
- Responsive design for different screen sizes
- Custom styling with consistent theming

## Development

### Building the Project
1. Clone the repository
2. Open `ecoChat.xcodeproj` in Xcode
3. Select your target device or simulator
4. Build and run the project

### Dependencies
- **SwiftUI**: Native iOS UI framework
- **Foundation**: Core iOS functionality
- **Keychain Services**: Secure storage

## License

This project is part of the Ecogentic LLC ecosystem.

## Contributing

This is a proprietary project developed by Ecogentic LLC. For questions or support, please contact the development team. 