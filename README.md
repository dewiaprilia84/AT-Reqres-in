# API Test Automation — Postman with Scripting (ReqRes)

This mini-project covers three scenarios using the free [ReqRes](https://reqres.in) API:

1) **Create User** — `POST /api/users`  
2) **Get Single User (Positive)** — `GET /api/users/2`  
3) **Get Single User (Negative)** — `GET /api/users/23`  

## Files
- `API Test Automation - reqres.in.postman_collection` — Postman collection with requests, pre-request scripts, and test assertions.
- `reqres.in env.postman_environment` — Environment holding `base_url`, `user_id_positive`, `user_id_negative`.

## Assertions (good detail)
- Status codes: `201` for POST create, `200` for positive GET, `404` for negative GET.
- Body fields:
  - POST: `id`, `createdAt`, and the response echoes `name` and `job` from request.
  - GET positive: validates presence of `data`/`support`, correct `id`, valid email regex.
  - GET positive: **JSON Schema** validation to ensure response structure.
  - GET negative: confirms empty `{}` body and `404` status.
- Variables: Saves `created_user_id` to the environment from the POST response.

## How to Use in Postman GUI
1. Open Postman → **Import** both JSON files.
2. Select **ReqRes Local** environment.
3. Run each request manually or use **Collection Runner** to run all at once.
