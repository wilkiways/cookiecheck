# Cookie Attribution Monitor

A specialized tool to monitor and track cookies that have been set by your affiliate bridge page, making it easy to verify attribution is working correctly.

## Overview

This tool provides a visual interface to:

1. See all cookies currently set in the browser
2. Identify and highlight cookies related to affiliate attribution 
3. Track changes to cookies over time (additions, modifications, deletions)

The system is particularly designed to detect cookies used for:
- Visitor tracking
- Session management
- Fingerprinting 
- Verification systems
- Analytics
- Affiliate attribution

## How It Works

1. Your bridge page sets tracking cookies and other attribution identifiers
2. The bridge page redirects to this cookie monitor (set as final destination)
3. This monitor displays all cookies, highlighting attribution-related ones
4. You can verify if your attribution system is correctly maintaining cookies

## Files Included

- `index.html` - The cookie monitoring interface (final destination page)
- `cookie-monitor.min.js` - JavaScript logic for cookie monitoring (minified)
- `styles.css` - Styling for the monitor interface

## Installation

1. Upload all files to your web server
2. Configure your bridge page to redirect to the index.html page after setting cookies
3. Access the page through your bridge page to see if attribution is carried over

## How to Use

### Basic Usage

1. Access your bridge page which should set cookies and redirect to this monitor
2. The monitor automatically shows all cookies that have been set
3. The "Attribution Cookies" section highlights cookies specifically related to attribution
4. You can manually refresh by clicking the "Refresh Cookie Data" button
5. Cookie changes will be recorded in the "Cookie History" section

### Cross-Origin Detection

Cookies that are identified as potentially related to affiliate attribution will be highlighted in the "Attribution Cookies" section. This helps identify cookies that:

- Contain specific patterns matching known tracking mechanisms
- Are related to verification, analytics, or fingerprinting systems
- Maintain user attribution across sessions

## Technical Details

The cookie monitor uses the standard `document.cookie` API to track cookies. For advanced tracking mechanisms like those using WebAssembly or SharedArrayBuffer, additional monitoring tools may be required.

## Prerequisites

- A modern web browser
- JavaScript enabled

## Security Note

This tool is meant for testing and verification purposes. It does not access or transmit any cookie data outside your browser. 