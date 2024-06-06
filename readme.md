
# User Authentication API

This API allows users to register and authenticate with a simple username and password system. It uses `bcrypt` for hashing passwords to ensure security.

## Getting Started

### Prerequisites

- Node.js
- npm (Node Package Manager)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME.git
   ```
2. Navigate to the project directory:
   ```bash
   cd YOUR_REPOSITORY_NAME
   ```
3. Install dependencies:
   ```bash
   npm install
   ```

### Running the Application

To start the server, run:
```bash
node index.js
```

The server will start on port 5000.

## API Endpoints

### Get All Users

#### Request
- **Method:** GET
- **URL:** `/users`

#### Response
- **Status:** 200 OK
- **Body:** JSON array of users

#### Example
```bash
curl -X GET http://localhost:5000/users
```

Response:
```json
[
  {
    "name": "user1",
    "password": "$2b$10$..."
  },
  {
    "name": "user2",
    "password": "$2b$10$..."
  }
]
```

### Register a New User

#### Request
- **Method:** POST
- **URL:** `/users`
- **Headers:** 
  - `Content-Type: application/json`
- **Body:**
  ```json
  {
    "name": "username",
    "password": "password"
  }
  ```

#### Response
- **Status:** 201 Created (if successful)
- **Status:** 500 Internal Server Error (if there was an error)

#### Example
```bash
curl -X POST http://localhost:5000/users -H "Content-Type: application/json" -d '{"name":"user1", "password":"password1"}'
```

### User Login

#### Request
- **Method:** POST
- **URL:** `/users/login`
- **Headers:** 
  - `Content-Type: application/json`
- **Body:**
  ```json
  {
    "name": "username",
    "password": "password"
  }
  ```

#### Response
- **Status:** 200 OK (if login is successful)
- **Body:** `Login Successful`
- **Status:** 400 Bad Request (if user not found)
- **Body:** `Cannot find user`
- **Status:** 200 OK (if password is incorrect)
- **Body:** `Wrong password or email`
- **Status:** 500 Internal Server Error (if there was an error)

#### Example
```bash
curl -X POST http://localhost:5000/users/login -H "Content-Type: application/json" -d '{"name":"user1", "password":"password1"}'
```

## Notes

- Passwords are hashed using `bcrypt` before being stored.
- Ensure to handle sensitive data securely and follow best practices for security.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Express.js](https://expressjs.com/)
- [bcrypt](https://github.com/kelektiv/node.bcrypt.js)

For any issues or contributions, feel free to open an issue or create a pull request.
```

### 8. Push the README to GitHub

Add the `README.md` file to the repository:
```bash
git add README.md
```

Commit the changes:
```bash
git commit -m "Add documentation"
```

Push the changes to GitHub:
```bash
git push
```

