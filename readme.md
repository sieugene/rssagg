
# Go RSSAGG

This is a backend service built in Go. It provides RESTful API endpoints for user management, feed handling, and post interaction. The application also includes periodic web scraping functionality and uses PostgreSQL as the database.

[Based on bootdotdev](https://github.com/bootdotdev/fcc-learn-golang-assets)

## Features

- User registration and authentication
- Feed creation and management
- Follow and unfollow feeds
- Post management for users
- Periodic web scraping
- CORS handling for cross-origin requests

## Installation

1. Clone the repository:

```bash
git clone https://github.com/sieugene/rssagg
```

2. Create a .env file based on .env.example
```bash
cp .env.example .env
```

3. Install dependencies:
```bash
go mod tidy
```

4. Run the application using Docker Compose:
```bash
docker-compose up -d
```

5. Run migrations using goose:
```bash
cd ./scl/schema
goose postgres DB_URL up
```

6. Generate SQL code with sqlc
```bash
# From the root of the application
sqlc generate
```

7. Run the application:
```bash
go run main.go
```


## API Endpoints

### Health Check
- **GET** `/v1/healthz`: Checks the service health.

### Users
- **GET** `/v1/users`: Get the current user (requires authentication).
- **POST** `/v1/users`: Create a new user.

### Feeds
- **GET** `/v1/feeds`: Get all feeds.
- **POST** `/v1/feeds`: Create a new feed (requires authentication).

### Feed Follows
- **GET** `/v1/feed_follows`: Get all followed feeds (requires authentication).
- **POST** `/v1/feed_follows`: Follow a new feed (requires authentication).
- **DELETE** `/v1/feed_follows/{feedFollowId}`: Unfollow a feed (requires authentication).

### Posts
- **GET** `/v1/posts`: Get posts for the current user (requires authentication).
