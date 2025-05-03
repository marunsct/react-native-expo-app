# Use a Debian-based Node.js image
FROM node:18-bullseye

# Install required packages, including sudo
RUN apt-get update && apt-get install -y \
    sudo \
    openjdk-11-jdk-headless \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Install Android Command Line Tools
RUN mkdir -p /usr/lib/android-sdk/cmdline-tools && \
    wget -q https://dl.google.com/android/repository/commandlinetools-linux-9477386_latest.zip -O /tmp/cmdline-tools.zip && \
    unzip /tmp/cmdline-tools.zip -d /usr/lib/android-sdk/cmdline-tools && \
    mv /usr/lib/android-sdk/cmdline-tools/cmdline-tools /usr/lib/android-sdk/cmdline-tools/latest && \
    rm /tmp/cmdline-tools.zip

# Set environment variables for Android SDK
ENV ANDROID_HOME=/usr/lib/android-sdk
ENV PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$ANDROID_HOME/platform-tools:$PATH

# Install Expo CLI and React Native CLI
RUN npm install -g expo-cli react-native-cli

# Add vscode user and configure sudo
RUN useradd -ms /bin/bash vscode && \
    mkdir -p /etc/sudoers.d && \
    echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/vscode && \
    chmod 0440 /etc/sudoers.d/vscode

# Set the working directory
WORKDIR /workspace

# Expose ports for React Native development
EXPOSE 19000 19001 19002 8081

# Start the Expo server
CMD ["expo", "start", "--tunnel"]
