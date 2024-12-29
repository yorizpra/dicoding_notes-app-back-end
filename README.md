# Dicoding Notes App Back-End

![Node.js](https://img.shields.io/badge/Node.js-v14.17.0-green) ![Hapi.js](https://img.shields.io/badge/Hapi.js-v20.1.5-blue) ![License](https://img.shields.io/badge/license-MIT-brightgreen)

This project is a Notes App back-end API built with Node.js and Hapi.js. It provides a robust API to manage user notes, including features for creating, retrieving, updating, and deleting notes. This project is part of the Dicoding "Belajar Membuat Aplikasi Back-End untuk Pemula" course.

---

## Features

- User authentication with token-based authentication
- Create, read, update, and delete notes
- Retrieve notes by user ID

---

## Prerequisites

Ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14.x or later)
- [npm](https://www.npmjs.com/) (v6.x or later)

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yorizpra/dicoding_notes-app-back-end.git
   ```

2. Navigate to the project directory:
   ```bash
   cd dicoding_notes-app-back-end
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

---

## Running the Application

1. Start the server:
   ```bash
   npm start
   ```

2. The server will run at:
   ```
   http://localhost:5000
   ```

---

## API Endpoints

### 1. Register a User
- **URL**: `/users`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "username": "string",
    "password": "string",
    "fullname": "string"
  }
  ```
- **Response**:
  - `201 Created`: User successfully registered.

### 2. User Login
- **URL**: `/authentications`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Response**:
  - `200 OK`: Token provided.

### 3. Add a Note
- **URL**: `/notes`
- **Method**: `POST`
- **Request Headers**:
  - `Authorization: Bearer <token>`
- **Request Body**:
  ```json
  {
    "title": "string",
    "body": "string"
  }
  ```
- **Response**:
  - `201 Created`: Note successfully added.

### 4. Get All Notes
- **URL**: `/notes`
- **Method**: `GET`
- **Request Headers**:
  - `Authorization: Bearer <token>`
- **Response**:
  - `200 OK`: List of notes.

### 5. Get Note Details
- **URL**: `/notes/{id}`
- **Method**: `GET`
- **Request Headers**:
  - `Authorization: Bearer <token>`
- **Response**:
  - `200 OK`: Note details.
  - `404 Not Found`: Note ID not found.

### 6. Update a Note
- **URL**: `/notes/{id}`
- **Method**: `PUT`
- **Request Headers**:
  - `Authorization: Bearer <token>`
- **Request Body**: Same as Add a Note.
- **Response**:
  - `200 OK`: Note successfully updated.
  - `404 Not Found`: Note ID not found.

### 7. Delete a Note
- **URL**: `/notes/{id}`
- **Method**: `DELETE`
- **Request Headers**:
  - `Authorization: Bearer <token>`
- **Response**:
  - `200 OK`: Note successfully deleted.
  - `404 Not Found`: Note ID not found.

---

## Project Structure

```
├── src
│   ├── api                # API handlers and routes
│   ├── services           # Business logic and data handling
│   ├── utils              # Utility functions
│   ├── server.js          # Hapi.js server setup
├── package.json           # Project metadata and dependencies
└── README.md              # Project documentation
```

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- [Dicoding](https://www.dicoding.com/) for providing the learning platform.
- [Hapi.js](https://hapi.dev/) for the web framework.

---

Feel free to contribute to this project by submitting issues or pull requests!
