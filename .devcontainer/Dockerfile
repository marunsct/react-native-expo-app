FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-14

# Install Expo CLI
RUN npm install -g expo-cli

# Install Android SDK
RUN apt-get update && apt-get install -y \
    openjdk-11-jdk \
    android-sdk \
    && rm -rf /var/lib/apt/lists/*

# Set environment variables for Android SDK
ENV ANDROID_HOME /usr/lib/android-sdk
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

# Install additional dependencies
RUN npm install -g react-native-cli

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN useradd -ms /bin/bash vscode

# Set the working directory
WORKDIR /workspace

# Expose ports for React Native
EXPOSE 19000 19001 19002 8081

# Start the Expo server
CMD ["expo", "start", "--tunnel"]