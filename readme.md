# Notification System Frontend

A simple frontend client for testing Socket.IO notifications. This HTML-based application connects to a notification server and displays real-time updates for various events.

## Features

- Real-time notification display via Socket.IO
- Visual status indicators (pending, processing, success, etc.)
- Responsive design
- Simple token-based authentication

## Setup

1. **Clone or download this repository**
2. **Update the configuration** in the HTML file:

   - Replace the Socket.IO server URL (`http://localhost:4000`)
   - Update the authentication token with a valid JWT
   - Modify the user ID in the `join-user` event if needed

3. **Open the HTML file** in a browser or serve it through a local web server

## Configuration

Before using, make sure to update these values in the HTML file:

```javascript
const socket = io("http://your-server-url:port", {
  auth: {
    token: `Bearer YOUR_VALID_JWT_TOKEN_HERE`,
  },
});

socket.emit("join-user", "YOUR_USER_ID_HERE");
```

## Event Types Supported

The client listens for these notification events:

- INVOICE_TOUR_PROCESSING, PENDING, SUCCESS, FAILED
- CREATE_RECEIVE_VOUCHER_PENDING, SUCCESS, FAILED
- DELETE_RECEIVE_VOUCHER_PENDING, SUCCESS, FAILED
- UPDATE_RECEIVE_VOUCHER_PENDING, SUCCESS, FAILED
- CREATE_PAYMENT_VOUCHER_PENDING, SUCCESS, FAILED
- PAYMENT_PROCESSING_PENDING, SUCCESS, FAILED

## Usage

This is a development/testing tool only. It requires:

1. A running Socket.IO server
2. Valid authentication credentials
3. Appropriate CORS configuration on the server

## Security Note

This is for development purposes only. Do not use in production without proper security measures. The token is hardcoded in the HTML file, which is not secure for production use.

## License

For development use only.
