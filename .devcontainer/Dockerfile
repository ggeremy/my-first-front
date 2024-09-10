# Use an official Node.js image as the base
FROM node:18

# Create a 'vscode' user and set up the environment
RUN useradd -ms /bin/bash vscode

# Set the working directory in the container
WORKDIR /workspace

# Install degit globally
RUN npm install -g degit

# Switch to the 'vscode' user for the dev container session
USER vscode

# Default command
CMD ["bash"]
