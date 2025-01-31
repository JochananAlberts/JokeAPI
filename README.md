# Jokes API

A RESTful API for managing and retrieving jokes. Built with Express.js.

## Setup

1. Clone the repository
2. Install dependencies:
```bash
npm install
```
3. Start the server:
```bash
node index.js
```
The server will run on `http://localhost:3000`

## API Endpoints

### GET Endpoints
- `GET /random` - Get a random joke
- `GET /jokes/:id` - Get a specific joke by ID
- `GET /jokes?type=<type>` - Get all jokes of a specific type

### POST Endpoint
- `POST /jokes` - Create a new joke
  - Body parameters:
    - `text`: The joke text
    - `type`: The joke category

### PUT Endpoint
- `PUT /jokes/:id` - Update an entire joke
  - Body parameters:
    - `text`: The new joke text
    - `type`: The new joke category

### PATCH Endpoint
- `PATCH /jokes/:id` - Update part of a joke
  - Body parameters (all optional):
    - `text`: The new joke text
    - `type`: The new joke category

### DELETE Endpoints
- `DELETE /jokes/:id?key=<api_key>` - Delete a specific joke
- `DELETE /all?key=<api_key>` - Delete all jokes

Note: DELETE operations require an API key for authorization.

## Joke Types
Available joke categories:
- Science
- Puns
- Wordplay
- Math
- Food
- Sports
- Movies

## Security
Protected endpoints require an API key. Include it as a query parameter `key`.

## Example Usage
```bash
# Get a random joke
curl http://localhost:3000/random

# Get all science jokes
curl http://localhost:3000/jokes?type=Science

# Create a new joke
curl -X POST http://localhost:3000/jokes \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "text=Why did the programmer quit his job? Because he didn't get arrays" \
  -d "type=Programming"
