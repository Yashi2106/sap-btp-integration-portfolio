# Weather API Proxy - SAP API Management

## Project Overview
Designed and deployed an API Management proxy for RapidAPI weather service. Added security policies, dynamic request handling, and monitoring capabilities.

## What I Built
- API proxy that sits between client and RapidAPI weather service
- Dynamic headers and query parameters support
- API key validation before request reaches backend
- Request/response logging for debugging

## Technical Details

### Policies Implemented
| Policy | Purpose |
|:---|:---|
| Verify API Key | Validates API key in request header before processing |
| Extract Variables | Pulls dynamic values (city, units) from request |
| Assign Message | Modifies request payload and headers before sending to backend |
| Pre-flow | All policies executed before request hits RapidAPI |

### Components Used
- **SAP API Management**
- **RapidAPI Weather Service** (external endpoint)
- **Postman** for testing

### Flow
## Testing
- End-to-end testing done via Postman
- Status: 200 OK response with weather data
- API key validation blocks unauthorized requests

## What I Learned
- How to secure APIs using key-based authentication
- Dynamic header/query modification based on client input
- Pre-flow vs post-flow execution in API Management

## Related Skills
- SAP API Management
- REST API design
- API security patterns
