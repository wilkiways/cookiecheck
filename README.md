# Cookie Attribution Monitor

A tool for verifying and monitoring attribution cookies and URL parameters for affiliate marketing and tracking.

## Overview

This tool helps verify if your bridge or landing pages are correctly setting cookies for attribution tracking. It shows:

1. **URL Parameters** - Attribution data passed through the URL
2. **Cookies** - All cookies accessible to the cookie monitor
3. **Attribution Cookies** - Highlighted cookies related to tracking/attribution
4. **Cookie History** - Changes to cookies during the session

## Usage

### Direct Usage

Simply access the tool at: [https://cookiecheck.pages.dev](https://cookiecheck.pages.dev)

### Cross-Domain Integration

Due to browser security restrictions, cookies from other domains aren't directly visible to the cookie monitor. To check cross-domain cookies, use one of these methods:

#### Method 1: URL Parameter Passing (Recommended)

On your bridge page, add the following code before redirecting to the cookie monitor:

```javascript
// Collect all your cookies and URL parameters
const cookieData = encodeURIComponent(document.cookie);

// Redirect to the cookie monitor with cookie data in URL
window.location.href = "https://cookiecheck.pages.dev/?cookieData=" + cookieData + "&source=" + source + "&campaign=" + campaign;
```

This will pass your cookies as a URL parameter that the cookie monitor can display.

#### Method 2: Pass Individual Parameters

Pass attribution data directly in the URL:

```javascript
window.location.href = "https://cookiecheck.pages.dev/?clickid=" + clickId + 
                       "&source=" + source + 
                       "&campaign=" + campaign +
                       "&offer_id=" + offerId;
```

### Making Cookies Cross-Domain Accessible

If you need cookies to be directly accessible:

```javascript
// Set cookies with proper attributes for cross-domain access
document.cookie = "attribution=value; SameSite=None; Secure; domain=.yourdomain.com";
```

Note: Many browsers restrict third-party cookies, so URL parameter passing is more reliable.

## Self-Hosting

1. Clone this repository
2. Deploy the files to any static web hosting (Cloudflare Pages, Netlify, Vercel, etc.)
3. No build step or dependencies needed

## Features

- Real-time cookie monitoring
- URL parameter display
- Categorization of cookies by purpose
- Cookie change history
- Mobile-friendly responsive design
- Dark mode support

## License

MIT 