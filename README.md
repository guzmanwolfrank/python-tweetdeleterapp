# python-tweetdeleterapp
tweet deleter app 



# Twitter Tweet Deleter 🐦🗑️

A Python GUI application for bulk deleting tweets with advanced filtering options. Clean up your Twitter timeline safely and efficiently with a user-friendly interface.

![Python](https://img.shields.io/badge/python-v3.7+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)

## ✨ Features

- **🖥️ User-Friendly GUI** - Clean tkinter interface, no command line needed
- **🛡️ Safe by Design** - Dry run mode enabled by default with preview functionality
- **🎯 Advanced Filtering** - Filter by date, content, engagement metrics, and tweet types
- **⚡ Rate Limit Handling** - Automatic compliance with Twitter's API limits
- **💾 Preset System** - Save and load your favorite filter configurations
- **📊 Real-Time Progress** - Live updates and progress tracking
- **🔒 Secure** - API credentials stored locally, never transmitted

## 📋 Prerequisites

- Python 3.7 or higher
- Twitter Developer Account with API access
- `tweepy` library

## 🚀 Installation

1. **Clone or download this repository**
```bash
git clone https://github.com/yourusername/twitter-tweet-deleter.git
cd twitter-tweet-deleter
```

2. **Install required dependencies**
```bash
pip install tweepy
```

3. **Run the application**
```bash
python simple_tweet_deleter_gui.py
```

## 🔑 Getting Twitter API Access

1. **Apply for Developer Access**
   - Visit: https://developer.twitter.com
   - Sign up for a developer account
   - Create a new app

2. **Configure Your App**
   - **App Type**: Choose "Native App"
   - **Permissions**: Set to "Read and Write"
   - **Callback URL**: `http://localhost:3000/callback` (placeholder)
   - **Website**: `https://example.com` (placeholder for personal use)

3. **Get Your Credentials**
   You'll need these 5 values:
   - Bearer Token
   - API Key (Consumer Key)
   - API Secret (Consumer Secret)
   - Access Token
   - Access Token Secret

## 📖 How to Use

### 1. **Setup API Credentials**
- Launch the application
- Enter your Twitter API credentials in the "API Configuration" section
- Click "Save Config" to store them locally
- Click "Test Connection" to verify everything works

### 2. **Configure Deletion Filters**
Choose your filtering criteria:
- **Date Filter**: Delete tweets older than X days
- **Content Filter**: Include/exclude tweets containing specific text
- **Engagement Filter**: Filter by maximum likes/retweets
- **Type Filter**: Exclude replies and/or retweets

### 3. **Preview Before Deleting**
- **Always start with "Preview Deletion"** to see what would be deleted
- Review the results in the Results tab
- Adjust your filters if needed

### 4. **Execute Deletion**
- Uncheck "Dry run" mode
- Click "Start Deletion"
- Confirm the deletion when prompted
- Monitor progress in real-time

## ⚠️ Safety Features

- **Dry Run Default**: Preview mode is enabled by default
- **Confirmation Prompts**: Double confirmation before actual deletion
- **Preview Functionality**: See exactly what will be deleted
- **Rate Limit Compliance**: Automatic delays to respect Twitter's limits
- **Error Handling**: Graceful handling of API errors and network issues

## 🎛️ Filter Options

| Filter Type | Description | Example |
|-------------|-------------|---------|
| **Date** | Delete tweets older than specified days | `365` (1 year old) |
| **Contains Text** | Only delete tweets containing specific words | `"old opinion"` |
| **Exclude Text** | Skip tweets containing certain words | `"important"` |
| **Max Likes** | Delete tweets with likes ≤ threshold | `5` (low engagement) |
| **Exclude Replies** | Skip reply tweets | ✅ Checked |
| **Exclude Retweets** | Skip retweets | ✅ Checked (recommended) |

## 📊 Common Use Cases

### 🧹 **General Cleanup**
```
✅ Delete tweets older than: 730 days (2 years)
✅ Exclude retweets: Yes
✅ Max likes: 10
```

### 🎯 **Content-Specific Cleanup**
```
✅ Contains text: "hot take"
✅ Exclude text: "important"
✅ Older than: 180 days
```

### 📈 **Low Engagement Cleanup**
```
✅ Max likes: 5
✅ Older than: 90 days
✅ Exclude replies: Yes
```

## 🔧 Troubleshooting

### **401 Unauthorized Error**
- Verify all API credentials are correct
- Ensure app permissions are "Read and Write"
- Regenerate Access Token after changing permissions
- Check for extra spaces in credential fields

### **Processing Takes Forever**
This is normal for large accounts:
- **Small account** (< 1,000 tweets): 1-3 minutes
- **Medium account** (1,000-5,000 tweets): 5-15 minutes
- **Large account** (10,000+ tweets): 20+ minutes

### **Rate Limit Errors**
- The app automatically handles rate limits
- Twitter allows 300 deletions per 15-minute window
- Large deletion jobs may take several hours

### **Connection Issues**
- Check your internet connection
- Verify Twitter API is not experiencing outages
- Try again later if Twitter's servers are slow

## 📁 File Structure

```
twitter-tweet-deleter/
│
├── simple_tweet_deleter_gui.py    # Main GUI application
├── tweet_deleter.py               # Full-featured version
├── twitter_config.json            # API credentials (auto-generated)
├── README.md                      # This file
└── presets/                       # Saved filter presets (optional)
```

## ⚡ Performance Tips

- **Start small**: Test with a small date range first
- **Use specific filters**: More specific filters = faster processing
- **Run during off-peak hours**: API is faster at night/early morning
- **Close other apps**: Free up system resources for better performance

## 🔒 Security & Privacy

- **Local Storage**: All credentials stored locally on your computer
- **No Data Collection**: App doesn't send your data anywhere
- **Open Source**: Code is fully transparent and auditable
- **API Only**: Uses official Twitter API with your own credentials

## ⚖️ Legal & Ethical Use

- **Personal Use Only**: Designed for managing your own tweets
- **Respect Twitter's ToS**: Don't violate Twitter's Terms of Service
- **Rate Limit Compliance**: App automatically respects API limits
- **Backup Important Tweets**: Consider downloading your Twitter archive first

## 🐛 Known Issues

- **Large accounts may timeout**: For 50,000+ tweets, consider running in smaller batches
- **Retweets with comments**: May not be detected as retweets in some cases
- **Very old tweets**: Tweets older than ~3,200 may not be accessible via API

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Bug fixes
- New filter options
- UI improvements
- Performance optimizations

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This tool is provided as-is for educational and personal use. Users are responsible for:
- Complying with Twitter's Terms of Service
- Using the tool responsibly
- Backing up important data before deletion
- Understanding that deleted tweets cannot be recovered

**Use at your own risk. Always test with dry run mode first!**

## 🆘 Support

Having issues? Try these resources:

1. **Check the troubleshooting section** above
2. **Test with dry run mode** to isolate issues  
3. **Verify API credentials** in Twitter Developer Portal
4. **Open an issue** on GitHub with error details

---

**Made with ❤️ for the Twitter community**

*Happy cleaning! 🧹*
