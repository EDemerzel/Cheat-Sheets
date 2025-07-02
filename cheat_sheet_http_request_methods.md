# Top 9 HTTP Request Methods

| Method      | Typical Endpoint       | Body                          | Success Status                | Purpose                         |
|-------------|------------------------|-------------------------------|-------------------------------|---------------------------------|
| **GET**     | `/v1/products/iphone`  | N/A                           | `200 OK`                      | Retrieve single item or list    |
| **POST**    | `/v1/users`            | JSON e.g. `{ "first":"Bob" }` | `201 Created`                 | Create new resource             |
| **PUT**     | `/v1/users/123`        | Full JSON doc                 | `200 OK`                      | Replace entire resource         |
| **PATCH**   | `/v1/users/123`        | Partial JSON                  | `200 OK`                      | Partially update resource       |
| **DELETE**  | `/v1/users/123`        | N/A                           | `200 OK` or `204 No Content`  | Remove resource                 |
| **HEAD**    | `/v1/products/iphone`  | N/A                           | `200 OK`                      | Same as GET but *no body*       |
| **OPTIONS** | `/v1/users`            | N/A                           | `200 OK` w/ `Allow:`          | List supported methods          |
| **CONNECT** | `xxx.com:80`           | Proxy headers                 | `200 OK`                      | Tunnel two‑way TCP (proxy)      |
| **TRACE**   | `/index.html`          | N/A                           | `200 OK`                      | Echo request for diagnostics    |

> **Notes**
>
> - `GET` + `HEAD` **must not** change server state.
> - `PUT` is idempotent; `POST` is not.
> - Use `PATCH` for partial updates to avoid sending full payloads.
