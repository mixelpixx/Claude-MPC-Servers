# Filesystem MCP Server

Node.js server implementing Model Context Protocol (MCP) for filesystem operations.

## Features


**Note**: The server will only allow operations within directories specified via `args`.

## API

### Resources


### Tools

  - Read complete contents of a file
  - Input: `path` (string)
  - Reads complete file contents with UTF-8 encoding

  - Read multiple files simultaneously
  - Input: `paths` (string[])
  - Failed reads won't stop the entire operation

  - Create new file or overwrite existing (exercise caution with this)
  - Inputs:
    - `path` (string): File location
    - `content` (string): File content

  - Create new directory or ensure it exists
  - Input: `path` (string)
  - Creates parent directories if needed
  - Succeeds silently if directory exists

  - List directory contents with [FILE] or [DIR] prefixes
  - Input: `path` (string)

  - Move or rename files and directories
  - Inputs:
    - `source` (string)
    - `destination` (string)
  - Fails if destination exists

  - Recursively search for files/directories
  - Inputs:
    - `path` (string): Starting directory
    - `pattern` (string): Search pattern
  - Case-insensitive matching
  - Returns full paths to matches

  - Get detailed file/directory metadata
  - Input: `path` (string)
  - Returns:
    - Size
    - Creation time
    - Modified time
    - Access time
    - Type (file/directory)
    - Permissions

  - Preview the first few lines or bytes of a file
  - Inputs:
    - `path` (string): File location
    - `bytes` (number, optional): Number of bytes to preview
  - Returns: Specified number of bytes or lines from the file

  - Calculate size of a file or directory
  - Input: `path` (string)
  - Returns: Total size in bytes

  - Detect file type based on content
  - Input: `path` (string)
  - Returns: Detected MIME type

  - List all directories the server is allowed to access
  - No input required
  - Returns:
    - Directories that this server can read/write from

## Usage with Claude Desktop
Add this to your `claude_desktop_config.json`:
