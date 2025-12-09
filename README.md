# BuildDocs API Gateway

This project acts as a proxy/gateway to expose Supabase Edge Functions under a custom domain.

## Endpoints

| Endpoint | Description |
|----------|-------------|
| `POST /v1/generate-document` | Generate a document from template |
| `GET /v1/document-status/{job_id}` | Check document generation status |

## Setup

1. Deploy to Vercel
2. Configure custom domain (e.g., `api.builddocs.io`)
3. All requests to `/v1/*` are proxied to Supabase Edge Functions

## Usage

```bash
# Generate document
curl -X POST "https://api.builddocs.io/v1/generate-document" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"template_id": "xxx", "data": {...}}'

# Check status
curl "https://api.builddocs.io/v1/document-status/job_abc123" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

