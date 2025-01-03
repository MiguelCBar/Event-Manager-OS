# Part 2 Project

## Overview
Part 2 builds upon Part 1 by transforming the EMS into a client-server application. The server interacts with clients via named pipes and handles session-based communication. Additionally, the system supports signal-based interactions.

## Key Features
1. **Client-Server Model**: The server manages multiple client sessions using named pipes.
2. **Session Management**:
   - Each session is uniquely identified.
   - Sessions are terminated upon client request.
3. **Signal Handling**:
   - SIGUSR1 is used for asynchronous state reporting.

## Usage

1. Build the project using `make`.

2. **Server**:
   ```
   ./server/ems <server_pipe_name> [delay]
   ```
3. **Client**:
   ```
   ./client/client <request-pipe-path> <response-pipe-path> <server-pipe-path> <path-jobs-directory>
   ```

## Requirements
- Ensure that the server is running before starting clients.
