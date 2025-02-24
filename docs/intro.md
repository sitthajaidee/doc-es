# DRM Entitlement Service

## Project Overview
This is a Node.js-based entitlement service that acts as a proxy between video players and Axinom's DRM licensing server. It handles Widevine DRM license requests, manages user authentication, and implements rate limiting for device access control.

## Key Features
- **DRM License Acquisition**: Handles Widevine DRM license requests and communicates with Axinom's DRM server
- **JWT Authentication**: Implements JSON Web Token (JWT) based authentication for secure access
- **Rate Limiting**: Redis-based rate limiting system to control license requests per device
- **Performance Monitoring**: Built-in middleware to track execution time and resource usage
- **CORS Support**: Configured for cross-origin resource sharing to work with web players
- **Error Handling**: Comprehensive error handling and logging system

## Architecture Components
1. **Frontend Player**
   - HTML5 video player with Shaka Player integration
   - Handles DRM license acquisition workflow
   - Supports Widevine DRM

2. **Backend Services**
   - Express.js server with RESTful API endpoints
   - Redis for rate limiting and caching
   - JWT-based authentication middleware
   - Performance monitoring middleware

3. **External Integration**
   - Axinom DRM license server integration
   - Custom JWT signing for Axinom communication

## Technology Stack
- Node.js & Express.js
- Redis
- Shaka Player (Client-side)
- JWT for authentication
- Axios for HTTP requests

## Usage
The service primarily handles DRM license requests through the `/api/acquire-license` endpoint, which:
1. Validates the access token
2. Processes the license request
3. Communicates with Axinom's DRM server
4. Enforces rate limiting per device
5. Returns the license response to the video player