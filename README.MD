OrbitScraper

OrbitScraper is a developer-focused Search Data (SERP) API that returns structured search engine results and publicly available web discovery data in clean JSON format.

Stop managing proxies, captchas, headless browsers, and blocking issues — OrbitScraper handles the data collection infrastructure so you can focus on building your product.

Website: https://orbitscraper.com

---

What OrbitScraper Provides

OrbitScraper allows applications to programmatically retrieve:

- Search engine results pages (SERP)
- Organic search listings
- Titles, links and descriptions
- Publicly available website discovery data
- Keyword research data workflows
- Automated data collection jobs

All responses are returned as structured JSON via a REST API.

«OrbitScraper only retrieves publicly available data. It does not access private, authenticated, or paywalled content.»

---

Typical Use Cases

- SEO tools
- Rank tracking systems
- Market research platforms
- Lead generation tools
- Competitor monitoring
- Content research automation
- AI data pipelines
- Analytics dashboards

---

Quick Start

1) Create Account

Sign up at:

https://orbitscraper.com

2) Get API Key

After login:

Dashboard → API Keys → Copy your key

---

3) Make Your First Request

curl -X POST https://api.orbitscraper.com/v1/search \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "query": "best wireless headphones",
    "location": "India",
    "language": "en",
    "device": "desktop"
  }'

---

4) Job Response

OrbitScraper uses an asynchronous job system.

You will receive:

{
  "success": true,
  "job_id": "job_8f21ac21d7",
  "status": "queued"
}

---

5) Fetch Results

curl https://api.orbitscraper.com/v1/results/job_8f21ac21d7 \
  -H "Authorization: Bearer YOUR_API_KEY"

---

Example Response

{
  "success": true,
  "query": "best wireless headphones",
  "location": "India",
  "results": [
    {
      "position": 1,
      "title": "Top 10 Wireless Headphones (2026)",
      "link": "https://example.com/headphones",
      "domain": "example.com",
      "snippet": "A curated list of the best wireless headphones..."
    },
    {
      "position": 2,
      "title": "Best Bluetooth Headphones Buying Guide",
      "link": "https://example2.com/guide",
      "domain": "example2.com",
      "snippet": "Everything you need to know before buying..."
    }
  ]
}

---

API Endpoints

Create Search Job

"POST /v1/search"

Get Job Result

"GET /v1/results/{job_id}"

---

Request Parameters

Parameter| Type| Description
query| string| Search keyword
location| string| Geographic location
language| string| Result language (en, hi, etc.)
device| string| desktop or mobile

---

Rate Limits

OrbitScraper uses a credit-based billing system.

- Each search request consumes credits
- Credits depend on request complexity
- Limits vary by plan
- Requests beyond quota return "402 Payment Required"

---

Error Handling

Code| Meaning
400| Invalid parameters
401| Invalid API key
402| Out of credits
404| Job not found
429| Rate limit exceeded
500| Temporary server error

Example error:

{
  "success": false,
  "error": "Invalid API key"
}

---

Best Practices

We recommend:

- Poll results every 3–5 seconds
- Implement retry logic (max 3 retries)
- Cache results when possible
- Avoid duplicate requests for same keyword

---

Data Policy

OrbitScraper:

- collects only publicly accessible information
- does not bypass logins
- does not access private accounts
- does not store personal user data

---

Security

- HTTPS encrypted requests
- API key authentication
- No IP whitelisting required
- Keys can be rotated anytime from dashboard

---

Support

Email: support@orbitscraper.com
Website: https://orbitscraper.com

---

Roadmap

Planned features:

- More search engines
- Batch requests
- Webhook delivery
- Keyword tracking
- Historical SERP data
- Analytics API

---

License

This repository contains documentation and examples for the OrbitScraper API service.

All platform infrastructure and backend services are proprietary.

---

Disclaimer

OrbitScraper is an API service that retrieves publicly available search engine data for software applications.
Users are responsible for ensuring their usage complies with applicable laws and the terms of service of the websites they interact with.

---
