# Magazine CMS - API Reference

## Authentication
All protected routes require a Bearer token:
```
Authorization: Bearer <jwt_token>
```

## Endpoints

### Articles
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/api/articles` | List all articles (paginated) | No |
| GET | `/api/articles/:id` | Get single article | No |
| POST | `/api/articles` | Create article | Yes |
| PUT | `/api/articles/:id` | Update article | Yes |
| DELETE | `/api/articles/:id` | Delete article | Yes |

### Comments
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/api/articles/:id/comments` | List comments | No |
| POST | `/api/articles/:id/comments` | Add comment | Yes |
| DELETE | `/api/comments/:id` | Delete comment | Yes |

### Users
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/api/auth/register` | Register user | No |
| POST | `/api/auth/login` | Login | No |
| GET | `/api/users/me` | Current user profile | Yes |

## Query Parameters
| Param | Type | Description |
|-------|------|-------------|
| `page` | number | Page number (default: 1) |
| `limit` | number | Items per page (default: 10) |
| `sort` | string | Sort by field (e.g. `-createdAt`) |
| `search` | string | Full-text search |
| `category` | string | Filter by category |

## Error Responses
```json
{ "error": "Not found", "status": 404 }
{ "error": "Unauthorized", "status": 401 }
{ "error": "Validation failed", "status": 422, "details": [...] }
```
