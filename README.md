# Transit Ticker - J Church Line at 20th Street

A real-time transit arrival display for the J Church Muni line at the 20th Street station in San Francisco. Shows live arrival times for both inbound (to Downtown) and outbound (to Noe) trains.

## Features

- Real-time arrival predictions for both directions
- Auto-refreshes every 30 seconds
- Clean, mobile-friendly interface
- Countdown timers showing minutes until arrival
- Highlights trains arriving in 2 minutes or less
- Data from 511.org API

## Live Site

Once deployed, your site will be available at:
`https://[your-username].github.io/transit-ticker/`

## Local Development

To run locally, simply open `index.html` in a web browser. The page will automatically fetch and display real-time arrival data.

Since this is a static site using only client-side JavaScript, no build process or server is required.

## Deployment to GitHub Pages

This repository is configured to automatically deploy to GitHub Pages when you push to the main branch.

### Setup Steps:

1. Push this repository to GitHub
2. Go to your repository Settings
3. Navigate to Pages (in the left sidebar)
4. Under "Build and deployment", set:
   - Source: **GitHub Actions**
5. Push a commit to the main branch to trigger deployment

The GitHub Actions workflow will automatically deploy your site.

## API Configuration

The site uses the 511.org API to fetch real-time transit data. The API key is currently embedded in `app.js`.

**Stop Codes:**
- Inbound (to Downtown): `16215`
- Outbound (to Noe): `16214`
- Agency: `SF` (SF Muni)

If you want to modify this for a different stop or line, you can:

1. Get a free API key from [511.org](https://511.org/open-data/token)
2. Find your stop codes using the [511 Stops API](https://511.org/open-data/transit)
3. Update the constants in `app.js`:
   ```javascript
   const API_KEY = 'your-api-key';
   const INBOUND_STOP = 'your-stop-code';
   const OUTBOUND_STOP = 'your-stop-code';
   ```

## Files

- `index.html` - Main page structure
- `style.css` - Styling and responsive design
- `app.js` - JavaScript for fetching and displaying real-time data
- `.github/workflows/pages.yml` - GitHub Pages deployment configuration

## API Rate Limits

The 511.org API has a rate limit of 60 requests per hour per API key. With the default 30-second refresh interval, this application makes 120 requests per hour (2 per refresh). This is within the free tier limits.

## Browser Compatibility

Works in all modern browsers that support ES6+ JavaScript and the Fetch API:
- Chrome/Edge 42+
- Firefox 39+
- Safari 10.1+
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

See LICENSE file for details.