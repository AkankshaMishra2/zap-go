# Google Maps API Setup Guide

## Why You Need This
Your ZapGo application uses Google Maps for:
- Displaying charging stations on an interactive map
- Route planning with directions
- Location search and autocomplete
- Geocoding addresses

## Step-by-Step Setup

### 1. Create Google Cloud Project
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Click "Select a project" → "New Project"
3. Name your project (e.g., "ZapGo Maps")
4. Click "Create"

### 2. Enable Required APIs
In your Google Cloud project, enable these APIs:
- **Maps JavaScript API** - For interactive maps
- **Places API** - For location search and autocomplete
- **Geocoding API** - For converting addresses to coordinates
- **Directions API** - For route planning

### 3. Create API Key
1. Go to "APIs & Services" → "Credentials"
2. Click "Create Credentials" → "API Key"
3. Copy the generated API key

### 4. Configure API Key Restrictions (Recommended)
1. Click on your API key to edit it
2. Under "Application restrictions", select "HTTP referrers"
3. Add your domain (for production) or leave unrestricted for development
4. Under "API restrictions", select "Restrict key"
5. Select the APIs you enabled in step 2

### 5. Set Up Environment Variables
1. Create a `.env` file in your project root (same level as `package.json`)
2. Add your API key:
```
REACT_APP_GOOGLE_MAPS_API_KEY=your_actual_api_key_here
```

### 6. Restart Development Server
```bash
npm start
```

## Troubleshooting

### Common Issues:
1. **"Maps API not configured" error**
   - Check that your `.env` file exists and has the correct variable name
   - Ensure the API key is valid and not restricted

2. **"This API project is not authorized"**
   - Enable billing for your Google Cloud project
   - Check that all required APIs are enabled

3. **"Quota exceeded" error**
   - Check your API usage in Google Cloud Console
   - Consider setting up billing for higher quotas

### Cost Information:
- Google Maps APIs have a generous free tier
- Most small to medium applications stay within free limits
- Monitor usage in Google Cloud Console

## Security Notes:
- Never commit your `.env` file to version control
- Use API key restrictions in production
- Monitor API usage regularly

## Testing:
After setup, you should see:
- Interactive map on the home page
- Working location search in route planner
- Station markers on the map
- Route directions when planning trips 