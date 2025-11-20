# Word Counter Web App

A mobile-optimized web application that uses Google Cloud Vision API to count words in photos of text from books or documents.

## Live Demo

🌐 **https://lbranigan.github.io/word-counter/**

## Purpose

Designed for teachers and students to quickly verify word counts from reading exercises without manual counting.

**Use Case:** A student reads from a book for one minute. The teacher uses this app to:
1. Take a photo of the page
2. Drag to select the words the student read
3. Get an instant, accurate word count

## Features

✅ **High Accuracy**: Uses Google Cloud Vision API (99%+ accuracy)
✅ **Mobile-First**: Optimized for smartphones with touch interaction
✅ **Camera or Upload**: Take a new photo or upload existing images
✅ **Smart Filtering**: Automatically filters out punctuation-only marks
✅ **Export Function**: Review exactly which words were counted
✅ **Offline Storage**: API key stored locally in browser
✅ **Free Tier**: 1,000 photos/month free with Google Cloud

## Quick Start

### 1. Get Google Cloud Vision API Key

1. Go to [Google Cloud Console](https://console.cloud.google.com/apis/credentials)
2. Create a new project (or select existing)
3. Create an API key
4. Enable "Cloud Vision API" for your project

**Cost:** Free tier includes 1,000 API requests per month

### 2. Use the App

1. Open: https://lbranigan.github.io/word-counter/
2. Enter your API key (first time only)
3. Take a photo or upload an image
4. Wait for green word detection boxes
5. Drag from first word to last word
6. See word count in header

## How It Works

### Word Detection
- Google Cloud Vision API detects all text in the image
- Each word gets a bounding box
- Words displayed with green outlines
- Punctuation-only items filtered out (e.g., standalone commas, periods)

### Word Selection
- Drag from first word to last word you want to count
- Red line shows during selection
- Selected words turn yellow
- All words between start and end point are counted

### Word Counting Rules
- Each detected word = 1 count
- Words with punctuation included (e.g., "don't" = 1 word)
- Pure punctuation marks excluded (e.g., "," not counted)
- Numbers counted as words (e.g., "1966" = 1 word)

## User Interface

### Header
- **Left**: "Word Counter" title
- **Right**: Live word count display

### Camera View
- Live camera preview
- **Capture Photo** button
- **Upload Photo** button

### Image Analysis View
- Photo with green word detection boxes
- Selected words highlighted in yellow
- **Retake Photo** | **Upload Photo** buttons
- **Clear Selection** button
- **Export Selected Words** button (green)
- Status messages

### Export Feature
- Shows numbered list of all selected words
- Displays plain text version for copying
- Explains counting methodology
- Helps verify accuracy

## Technical Details

### Tech Stack
- **Frontend**: Pure HTML, CSS, JavaScript (no frameworks)
- **API**: Google Cloud Vision API (Document Text Detection)
- **Hosting**: GitHub Pages (free)
- **Storage**: LocalStorage (API key only)

### Browser Requirements
- **Mobile**: Chrome, Safari (iOS 11+, Android 5+)
- **Desktop**: Any modern browser
- **Requirement**: HTTPS for camera access

### Files
- `index.html` - App structure
- `styles.css` - Responsive styling
- `app.js` - Core functionality and API integration

## Privacy & Security

✅ **No data sent to external servers** (except Google Cloud Vision for OCR)
✅ **API key stored locally** in browser only
✅ **No account required**
✅ **No tracking or analytics**
✅ **Images processed temporarily** and not stored

## API Usage & Costs

### Free Tier
- 1,000 requests per month = 1,000 photos
- Perfect for classroom use (30-40 photos per school day)

### Paid Tier
- After 1,000: $1.50 per 1,000 additional requests
- Example: 2,000 photos/month = $1.50

### What Counts as 1 Request
- ✅ Each photo taken or uploaded = 1 request
- ❌ Selecting/re-selecting words = 0 requests (local)
- ❌ Clear selection = 0 requests
- ❌ Export = 0 requests

### Sharing API Keys
You can share your API key with others (e.g., colleagues):
- All users share the same 1,000/month quota
- Monitor usage in Google Cloud Console

## Development

### Local Development

```bash
# Clone repository
git clone https://github.com/LBranigan/word-counter.git
cd word-counter

# Start local server
python -m http.server 8000

# Access on same network (mobile testing)
# http://YOUR_IP_ADDRESS:8000
```

### HTTPS Testing (for camera on mobile)

```bash
# Install localtunnel
npx localtunnel --port 8000

# Use the provided HTTPS URL on your mobile device
```

## Troubleshooting

### Camera Not Working
- **Problem**: "Camera access denied" error
- **Solution**: Must use HTTPS. Use GitHub Pages URL or localtunnel

### Image Not Displaying After Capture
- **Problem**: Black screen or blank image
- **Solution**: Refresh the page and try again

### Overcounting Words
- **Problem**: Count seems too high
- **Solution**: Click "Export Selected Words" to see exact words counted

### API Key Errors
- **Problem**: "Invalid API key" message
- **Solution**:
  - Verify API key is correct
  - Ensure Cloud Vision API is enabled in Google Cloud Console
  - Check API key restrictions

### Touch Selection Not Working
- **Problem**: Can't select words by dragging
- **Solution**:
  - Ensure page is fully loaded (green boxes visible)
  - Try dragging slower
  - Make sure you start and end on word centers

## Known Issues

- None currently reported

## Roadmap / Future Features

Potential improvements:
- Multiple selection regions
- Word count history/log
- Offline OCR (local processing)
- Support for other languages
- PDF upload support
- Voice readout of count

## Credits

Built by Branigan Liam with assistance from Claude Code (Anthropic)

## License

MIT License - Free to use and modify

## Support

For issues or questions:
- GitHub Issues: https://github.com/LBranigan/word-counter/issues

## Changelog

See commit history for detailed changes:
https://github.com/LBranigan/word-counter/commits/main

### Recent Updates
- ✅ Punctuation filtering (no more standalone commas counted)
- ✅ File upload option added
- ✅ Export selected words feature
- ✅ Fixed retake photo display bug
- ✅ Mobile UI optimizations
