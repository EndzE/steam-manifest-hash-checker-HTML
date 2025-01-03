# Steam Manifest Hash Checker HTML

## Overview
The Steam Manifest Hash Checker is a web-based tool designed to verify the integrity of Steam game files against their manifest data. This standalone application allows users to validate their game files by comparing their SHA-1 hashes with the expected values from a Steam manifest file.

## Acknowledgments
Thanks to SteamKit2 code, which was used as a reference for the manifest file decoding. Without this reference implementation, parsing the Steam manifest format would have been much more challenging.

Thanks to anadius for recommending hash-wasm - this suggestion significantly improved the tool's performance over the original implementation.

This project exists thanks to Masquerade, who came up with the idea and helped test it extensively. Their testing was crucial in identifying and fixing various issues.

## AI Attribution Notice
This project was developed with partial assistance from Claude, an AI language model by Anthropic. The AI contributed to code optimization, implementation strategies, and documentation. The core functionality and original concept remain human-developed, with AI serving as a development aid for code refinement and feature implementation.

## Hash Implementation
The application uses hash-wasm version 4.11.0 for SHA-1 hash computation. hash-wasm is a high-performance WebAssembly implementation of various cryptographic hash functions. The SHA-1 implementation processes files in 8MB chunks for optimal memory usage while maintaining high performance. Using hash-wasm instead of native JavaScript implementations provides several advantages:

- Significantly faster hash computation through WebAssembly
- Consistent performance across different browsers
- Memory-efficient processing of large files
- Hardware-accelerated computation where available
- Reliable handling of large file chunks

## Features
The application provides a modern, efficient interface for file verification with the following capabilities:

- Drag-and-drop interface for manifest and game files
- Real-time hash verification with progress tracking
- Processing speed monitoring in MB/s
- File search functionality
- Intelligent folder structure management
- Automatic missing file detection
- Complete file path display in mismatch reports
- Dark mode support with a metallic blue theme
- Memory-efficient processing of large files

### Recent Feature Additions
- **Missing File Detection**: Automatically identifies and marks files as "Missing" when they're listed in the manifest but not found in the provided directory
- **Folder Structure Optimization**: Removes redundant folder entries while preserving file listings for cleaner navigation
- **Enhanced Path Display**: Shows complete file paths in the mismatches list for easier file location and verification

## Technical Implementation
The application uses several modern web technologies and approaches:

- hash-wasm for high-performance SHA-1 hash computation
- Chunked file processing (8MB chunks) for memory efficiency
- Asynchronous file handling
- WebAssembly for optimal hash calculation performance
- Protobuf parsing for Steam manifest files
- Intelligent file path tracking and management
- Advanced file status handling system

## Usage Instructions

1. Open the HTML file in a modern web browser
2. Drop your Steam manifest file into the first drop zone
3. Drop the files you want to verify into the second drop zone
4. Monitor the verification progress through the progress bar
5. Use the search function to locate specific files
6. View results showing matched, mismatched, missing, and folder entries
7. Check the mismatches list for complete file paths of any problematic files

## Requirements
- Modern web browser with JavaScript enabled
- WebAssembly support
- Internet connection (for loading hash-wasm library)

## Performance Considerations
The tool is optimized for handling large game directories efficiently:

- Files are processed in 8MB chunks to manage memory usage
- Progress updates are throttled to maintain UI responsiveness
- Hash computation is performed using WebAssembly for optimal performance
- Intelligent folder structure management reduces memory overhead

## Security
This tool operates entirely in your browser with no external connections except for loading the hash-wasm library. No data is transmitted to any servers, and all file processing occurs locally.

## Limitations
- Requires modern browser capabilities
- Processing speed depends on local hardware performance

## Browser Compatibility
Tested and supported on:
- Chrome 90+
- Firefox 88+
- Edge 90+
- Safari 14+

## Technical Details
The application uses several key components:

- Binary protobuf parsing for manifest files
- Streaming file processing
- Web Workers for background processing
- CSS Grid and Flexbox for responsive layout
- Advanced file path management system
- Intelligent file status tracking

## License
This tool is provided as-is for personal use. Please verify licensing requirements for commercial applications.

## Support
For issues, questions, or improvements, please submit them through the project's issue tracking system.
