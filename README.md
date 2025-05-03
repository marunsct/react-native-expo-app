# React Native Expo App

This project is a React Native application built using Expo. It is set up to run in a development container using GitHub Codespaces, providing a seamless environment for developing mobile applications for both Android and iOS.

## Project Structure

```
react-native-expo-app
├── .devcontainer
│   ├── devcontainer.json
│   ├── Dockerfile
├── src
│   ├── App.js
│   └── components
│       └── ExampleComponent.js
├── package.json
├── README.md
```

## Getting Started

To get started with this project, follow these steps:

1. **Open in GitHub Codespaces**: Click on the "Code" button and select "Open with Codespaces" to launch the development environment.

2. **Install Dependencies**: Once the Codespace is running, install the necessary dependencies by running:
   ```
   npm install
   ```

3. **Run the Application**: Start the Expo development server with:
   ```
   npm start
   ```

4. **Open in Expo Go**: Use the Expo Go app on your mobile device or an emulator to scan the QR code displayed in the terminal or browser to view your application.

## Development Environment

This project uses a Docker container configured with the following tools:

- Node.js
- Expo CLI
- Android SDK
- iOS SDK (for macOS users)

## VS Code Extensions

The following extensions are recommended for a better development experience:

- ESLint
- Prettier - Code formatter
- React Native Tools

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any enhancements or bug fixes.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.