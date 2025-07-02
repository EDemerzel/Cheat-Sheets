# API Security Checklist

## Authentication

* ☐ **Use strong, standardized methods** (OAuth 2.1 + OpenID Connect 1.0, signed JWTs).
* ☐ **Never roll your own crypto / auth logic**—delegate to proven libraries or IdPs.
* ☐ Enforce **rate limiting / lockout (max‑retry)** on login endpoints.
* ☐ Encrypt all sensitive data **in transit (TLS 1.3)** and **at rest**.

## Access Control

* ☐ Implement **least‑privilege RBAC / ABAC** on every route/function.
* ☐ **Throttle requests** to prevent DDoS / brute‑force.
* ☐ Enforce **HSTS** and secure ciphers; disable TLS 1.0/1.1.
* ☐ Remove directory listings & server banners in prod.
* ☐ Restrict private APIs to **allow‑listed IPs / mTLS**.

## JWT (Token Handling)

* ☐ Generate tokens with **256‑bit secrets** (HS256) or **strong RSA/ECDSA keys**.
* ☐ **Never** trust the `alg` header—always validate server‑side.
* ☐ Keep **TTL / RTRT** short; rotate keys.
* ☐ Do not store secrets/P II in token payload.
* ☐ Use **compact claims** to reduce size.

## OAuth

* ☐ Always validate the **`redirect_uri`** on the server.
* ☐ Prefer **authorization code + PKCE** over implicit flows.
* ☐ Use `state` & `nonce` to prevent CSRF / replay.
* ☐ Apply **scoped** tokens per client / resource.

## Input & Processing

* ☐ Accept only **allowed HTTP verbs** (`GET`, `POST`, …).
* ☐ Validate `Content‑Type` and all user input (OWASP ASVS 4.0).
* ☐ Prefer **UUIDv7** over auto‑increment IDs in URLs.
* ☐ Disable XML entity expansion / XXE if parsing XML.
* ☐ Serve large file uploads via **signed‑URL + CDN**, not API gateway.
* ☐ Turn off debug/trace logging in production.

## Output

* ☐ `X‑Content‑Type‑Options: nosniff`
* ☐ `X‑Frame‑Options: DENY` or `SAMEORIGIN`
* ☐ `Content‑Security‑Policy` with least‑privilege directives
* ☐ Remove fingerprinting headers (`X‑Powered‑By`, etc.).
* ☐ Return **proper HTTP status codes** (2xx/3xx/4xx/5xx).

## CI / CD & Monitoring

* ☐ Enforce **unit/integration tests** in pipelines; fail on critical vulns.
* ☐ Require **peer code review**; no self‑approvals.
* ☐ Run **SCA/SAST/DAST** automatically; pin dependencies.
* ☐ Use **centralized log ingestion & alerting** (ELK, CloudWatch, etc.).
* ☐ IDS/IPS and anomaly detection on north‑south traffic.
