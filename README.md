# FFmpeg Web Converter

A modern, web-based video converter powered by FFmpeg. Convert videos between multiple formats with an easy-to-use interface designed for compatibility with low-end devices and legacy firmware.

## 🎯 Features

- **Multiple Format Support** - Convert between AVI, MP4, MOV, MKV, FLV, and more
- **Device Optimization** - Pre-configured profiles for low-end devices and legacy firmware (e.g., YP3 2.0.4)
- **Batch Processing** - Convert multiple files simultaneously
- **Quality Control** - Adjustable bitrate, resolution, and codec options
- **Web-Based** - No installation required; works directly in your browser
- **Real-time Progress** - Monitor conversion progress with live updates
- **File Preview** - Preview video information before conversion

## 🚀 Getting Started

### Prerequisites

- Node.js 14+ (for backend server)
- FFmpeg installed on the system
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/JustWazy/Avi-Converter.git
   cd Avi-Converter
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Verify FFmpeg installation**
   ```bash
   ffmpeg -version
   ```

4. **Start the server**
   ```bash
   npm start
   ```

5. **Open in browser**
   Navigate to `http://localhost:3000`

## 📖 Usage

### Basic Conversion

1. Upload a video file
2. Select output format
3. Choose quality/preset (optional)
4. Click "Convert"
5. Download the converted file

### Advanced Options

- **Codec Selection** - Choose specific video/audio codecs
- **Bitrate Control** - Set custom bitrate for quality/size tradeoff
- **Resolution** - Scale video to specific dimensions
- **Frame Rate** - Adjust FPS for compatibility
- **Audio Settings** - Control audio codec and sample rate

### Device Presets

Pre-configured profiles for common low-end devices:

- **MP3 Players** - AVI format, MPEG-4 codec, 320x240 resolution
- **YP3 Firmware (2.0.4)** - MP4 format, H.264 codec, 480x360 resolution
- **Legacy Devices** - Custom settings for older hardware

## 🛠️ Technology Stack

- **Frontend** - HTML, CSS, JavaScript
- **Backend** - Node.js / Express.js
- **Video Engine** - FFmpeg
- **Real-time Communication** - WebSockets (optional)

## 📁 Project Structure

```
Avi-Converter/
├── public/               # Frontend assets
│   ├── index.html       # Main page
│   ├── css/             # Stylesheets
│   └── js/              # Client-side scripts
├── src/                 # Backend code
│   ├── server.js        # Main server file
│   ├── routes/          # API endpoints
│   └── utils/           # Helper functions
├── uploads/             # Temporary upload directory
├── downloads/           # Converted files directory
└── README.md            # This file
```

## 🔧 Configuration

Edit `config.json` to customize:

```json
{
  "port": 3000,
  "maxFileSize": 500,
  "uploadDir": "./uploads",
  "outputDir": "./downloads",
  "presets": {
    "mp3Player": {
      "format": "avi",
      "codec": "mpeg4",
      "resolution": "320x240",
      "bitrate": "256k"
    },
    "yp3Device": {
      "format": "mp4",
      "codec": "h264",
      "resolution": "480x360",
      "bitrate": "384k"
    }
  }
}
```

## 🎨 Supported Formats

**Input:** AVI, MP4, MOV, MKV, FLV, WMV, WebM, OGV, and more

**Output:** AVI, MP4, MOV, MKV, FLV, WebM, OGV

## ⚙️ API Endpoints

### POST `/api/convert`
Convert a video file
```json
{
  "file": "video.mp4",
  "format": "avi",
  "preset": "mp3Player"
}
```

### GET `/api/presets`
Retrieve available conversion presets

### GET `/api/status/:jobId`
Check conversion job status

### GET `/api/download/:fileId`
Download converted file

## 🐛 Troubleshooting

### FFmpeg not found
```bash
# Ubuntu/Debian
sudo apt-get install ffmpeg

# macOS
brew install ffmpeg

# Windows
choco install ffmpeg
```

### Port already in use
```bash
# Change port in config.json or use environment variable
PORT=3001 npm start
```

### Large file uploads timing out
- Increase server timeout in configuration
- Use chunked upload for files > 500MB
- Check available disk space

## 📊 Performance Tips

- Use device presets for optimized conversion times
- Lower resolution for faster processing
- Close other applications to free up system resources
- For batch jobs, process files sequentially to avoid memory issues

## 🔒 Security

- File uploads are validated before processing
- Converted files are automatically deleted after download
- Input sanitization prevents injection attacks
- CORS headers are properly configured

## 📝 License

[Specify your license here - e.g., MIT, GPL, etc.]

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m 'Add YourFeature'`)
4. Push to branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 📞 Support

For issues, questions, or suggestions, please:

- Open an [Issue](https://github.com/JustWazy/Avi-Converter/issues)
- Check existing documentation
- Review closed issues for solutions

## 🙏 Acknowledgments

- FFmpeg team for the powerful video processing library
- Community contributions and feedback

---

**Last Updated:** 2026

**Repository:** [JustWazy/Avi-Converter](https://github.com/JustWazy/Avi-Converter)
