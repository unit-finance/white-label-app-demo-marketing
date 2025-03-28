# Unit White Label Demo Widget

A Next.js-based embeddable widget for Unit's White Label Banking solution demo.

## Prerequisites

- Node.js 16.x or later
- npm or yarn
- Unit API credentials
- Retool workflow configuration

## Setup

1. Clone the repository:

```bash
git clone <repository-url>
cd unit-wl-demo-proxy
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Create environment file:

```bash
cp example.env .env
```

4. Update the `.env` file with your credentials:

```env
# Unit API Configuration
NEXT_PUBLIC_UNIT_URL="https://ui.s.unit.sh"
UNIT_TOKEN="your_unit_token_here"

# Retool Configuration
RETOOL_WORKFLOW_API_KEY="your_retool_workflow_api_key_here"
RETOOL_START_TRIGGER_URL="your_retool_workflow_url_here"
```

5. Start the development server:

```bash
npm run dev
# or
yarn dev
```

The widget will be available at `http://localhost:3000`

## API Endpoints

### Health Check

- **Endpoint**: `/api/ping`
- **Method**: Any
- **Response**:
  ```json
  {
    "status": "ok"
  }
  ```
- **Status Code**: 200
- **Use Case**: Health monitoring and availability checks

## Embedding the Widget

### Basic Embedding

Add the following iframe code to your website:

```html
<iframe
  src="http://localhost:3000?width=100%&height=600px"
  width="100%"
  height="600px"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
>
</iframe>
```

### Customizable Parameters

The widget accepts the following URL parameters:

- `width`: Width of the widget (default: "100%")
- `height`: Height of the widget (default: "600px")

Example with custom dimensions:

```html
<iframe
  src="http://localhost:3000?width=800px&height=800px"
  width="800"
  height="800"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
>
</iframe>
```

## Development

### Project Structure

```
unit-wl-demo-proxy/
├── src/
│   ├── components/     # React components
│   ├── pages/         # Next.js pages
│   ├── styles/        # Global styles
│   └── types/         # TypeScript types
├── public/            # Static files
├── .env              # Environment variables
└── next.config.js    # Next.js configuration
```

### Key Components

- `UnitTriggerDemoWidget`: Main widget component
- `start-trigger.ts`: API route for token generation
- `index.tsx`: Widget page with iframe support

## Security Considerations

1. The widget is configured with secure CORS and security headers
2. Keep your API keys and tokens secure
3. In production, consider restricting CORS to specific domains

## Production Deployment

1. Build the application:

```bash
npm run build
# or
yarn build
```

2. Start the production server:

```bash
npm start
# or
yarn start
```

## Troubleshooting

1. If the widget doesn't load:

   - Check browser console for errors
   - Verify CORS settings
   - Ensure all environment variables are set correctly

2. If the token isn't persisting:
   - Check browser localStorage
   - Verify token expiration settings

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

[Your License Here]
