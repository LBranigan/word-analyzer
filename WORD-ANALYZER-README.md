# Word Analyzer - Reading Comprehension Tool

**Version**: 2025-01-22 (Guided UX)
**Institution**: Morningside Academy
**Live Demo**: https://lbranigan.github.io/word-analyzer/

A web-based application for analyzing reading comprehension by comparing expected text with spoken audio recordings. Features guided step-by-step workflow, word-level accuracy tracking, and detailed error reporting.

---

## 🎯 Features

### Core Functionality
- **Guided Workflow**: 5-step process with visual breadcrumb navigation
- **OCR Text Recognition**: Google Cloud Vision API for 99%+ accuracy
- **Audio Recording**: Up to 5 minutes with real-time timer
- **Word-Level Analysis**: Compare expected vs. spoken words
- **Multiple Export Formats**: PDF reports and video transcripts
- **Smart Validation**: Prevents invalid actions with helpful tooltips

### User Experience
- **Click-to-Select Words**: Click any word to select/deselect
- **Drag Selection**: Select multiple words at once
- **Expandable Preview**: Toggle image size in audio section
- **Zoom & Pan**: Navigate large images easily
- **Mobile Responsive**: Works on tablets and phones
- **Progress Tracking**: Always know which step you're on

---

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Google Cloud Platform account (for API keys)
- Camera and microphone permissions

### Setup (2 minutes)

1. **Get Google Cloud API Key**
   - Go to [Google Cloud Console](https://console.cloud.google.com/apis/credentials)
   - Create a new project or select existing
   - Click "Create Credentials" → "API Key"
   - Enable these APIs:
     - Cloud Vision API (for text recognition)
     - Cloud Speech-to-Text API (for audio analysis)

2. **Launch Application**
   - Open `index.html` in your browser
   - Or visit: https://lbranigan.github.io/word-analyzer/
   - Enter your API key when prompted
   - Click "Save & Start"

3. **You're Ready!**
   - API key stored locally (never sent to servers)
   - Free tier: 1,000 Vision requests + 60 minutes Speech/month

---

## 📖 How to Use

### Step 1: Capture Image
1. Point camera at text document
2. Click "Capture Photo" OR "Upload Photo"
3. System processes text automatically
4. Advances to audio recording

### Step 2: Record Audio
1. View captured text preview
2. Click "Expand" for larger view (optional)
3. Click "Record Audio" button
4. Choose duration (1-5 minutes)
5. Read the text aloud
6. Click "Stop" or wait for auto-stop
7. Click "Next: Highlight Text"

### Step 3: Highlight Text
1. **Select words that were read aloud**:
   - Click individual words to select/deselect
   - Drag to select multiple words
   - Right-click to pan image
2. Use zoom controls if needed (+, -, reset)
3. Click "Clear Selection" to start over
4. Click "Analyze Reading" when ready

### Step 4: View Results
1. Review accuracy statistics
2. See color-coded transcript:
   - **Green**: Correct words
   - **Yellow**: Skipped words
   - **Red**: Misread/substituted words
3. Export options:
   - "Download Output (PDF)" for printable report
   - "Generate Video" for synchronized playback
4. Navigate:
   - "Back to Edit" to adjust selection
   - "Start New Analysis" to begin fresh

---

## 🎨 User Interface Guide

### Breadcrumb Navigation
```
[✓ Setup] → [✓ Capture] → [● Audio] → [○ Highlight] → [○ Results]
```
- ✓ Green = Completed (clickable)
- ● Blue = Current step
- ○ Grey = Not yet accessible

**Tips**:
- Click completed steps to jump back
- Hover locked steps to see requirements
- Mobile: Breadcrumb shows icons only

### Button States
- **Enabled (Blue)**: Ready to use
- **Disabled (Grey)**: Requirements not met
- **Hover disabled**: Shows tooltip explaining why

### Color Coding
- **Green borders**: Unselected words
- **Yellow highlight**: Selected words
- **Green text**: Correct pronunciation
- **Yellow text**: Skipped words
- **Red text**: Errors

---

## 🔧 Technical Details

### Architecture
- **Frontend**: Vanilla JavaScript (ES6+)
- **Styling**: Custom CSS with responsive design
- **APIs**: Google Cloud Vision + Speech-to-Text
- **Storage**: Browser localStorage (API key only)

### File Structure
```
word-analyzer/
├── index.html              # Main application
├── app.js                  # Core logic (2,600+ lines)
├── styles.css              # Styling (900+ lines)
├── WORD-ANALYZER-README.md # This file
├── QA-CHECKLIST.md         # Quality assurance
└── DOCUMENTATION.md        # Technical docs
```

### Key Components
1. **State Management**: Centralized app state
2. **Step Navigation**: Breadcrumb-driven workflow
3. **OCR Processing**: Google Vision API integration
4. **Audio Analysis**: Speech-to-text alignment
5. **PDF Generation**: jsPDF library
6. **Video Generation**: Canvas + MediaRecorder API

### Browser Support
| Browser | Support | Notes |
|---------|---------|-------|
| Chrome 90+ | ✅ Full | Recommended |
| Firefox 88+ | ✅ Full | Recommended |
| Safari 14+ | ✅ Full | Requires permissions |
| Edge 90+ | ✅ Full | Chromium-based |
| Mobile | ⚠️ Partial | Best on tablets |

---

## 📊 Analysis Output

### PDF Report Includes
- Analysis timestamp
- Total words, correct count, error count
- Accuracy percentage
- Full transcript with color coding
- Error breakdown by category
- Skipped lines detection
- Repeated phrases identification

### Video Output Includes
- Synchronized word highlighting
- Audio playback with visual tracking
- Color-coded accuracy display
- Auto-download as .webm file

---

## 🔒 Privacy & Security

### Data Storage
- **API Key**: Stored in browser localStorage only
- **Images**: Processed in-browser, not uploaded
- **Audio**: Sent to Google Cloud for transcription only
- **Results**: Never stored on servers

### Permissions Required
- **Camera**: To capture text images
- **Microphone**: To record audio
- **Storage**: To save API key locally

### API Usage
- Free tier limits: 1,000 Vision calls/month
- Speech-to-Text: 60 minutes/month free
- Costs beyond free tier: Pay-as-you-go

---

## 🐛 Troubleshooting

### Common Issues

**"No text detected"**
- Ensure good lighting
- Text should be clear and in focus
- Try uploading instead of camera
- Check API key is valid

**"API key error"**
- Verify Vision API is enabled
- Check API key has no restrictions
- Generate new key if needed

**"Audio recording failed"**
- Grant microphone permissions
- Check microphone is connected
- Try shorter duration (1-2 minutes)
- Close other apps using microphone

**"Video generation error"**
- Ensure audio was recorded
- Check browser supports MediaRecorder
- Try Chrome if using Safari

**Button not working**
- Hard refresh browser (Ctrl+F5)
- Clear cache and cookies
- Check browser console for errors
- Ensure JavaScript is enabled

---

## 📝 Version History

### v2025-01-22 (Guided UX) - Current
- ✅ Guided step-by-step workflow with breadcrumb navigation
- ✅ Click-to-select/deselect individual words
- ✅ In-place expandable image preview (400px → 800px)
- ✅ Smart button validation with tooltips
- ✅ Dedicated audio recording section
- ✅ Dedicated results section
- ✅ Mobile responsive breadcrumb
- ✅ Updated terminology: "Reading Comprehension"
- ✅ Fixed all button responsiveness issues
- ✅ Comprehensive error handling

### v2025-01-21 19:35 UTC
- Reduced audio bitrate to fix file size errors
- Force deployment of currency expansion fix
- Number normalization for digits vs words
- Complete rewrite of alignment algorithm

---

## 🤝 Contributing

### Reporting Issues
Please include:
- Browser and version
- Steps to reproduce
- Expected vs actual behavior
- Console error messages (if any)

### Future Enhancements
- [ ] Offline mode with cached API calls
- [ ] Multi-language support
- [ ] Custom error categories
- [ ] Batch processing multiple texts
- [ ] Progress saving/loading
- [ ] Export to additional formats

---

## 📄 License

© 2025 Morningside Academy. All rights reserved.

This software is provided for educational purposes. Google Cloud Platform services are subject to their respective terms of service.

---

## 🆘 Support

For technical support or questions:
- Check troubleshooting section above
- Review QA checklist for known issues
- Consult technical documentation
- Contact system administrator

---

## 🎓 Credits

**Developed for**: Morningside Academy
**Built with**: Claude Code (Anthropic)
**APIs**: Google Cloud Vision & Speech-to-Text
**Libraries**: jsPDF for PDF generation

---

**Ready to analyze reading comprehension? Get started now! 🚀**
