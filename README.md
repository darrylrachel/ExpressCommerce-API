# ExpressCommerce API: A Dynamic Shopping Cart Application

## Overview
**ExpressCommerce API** is a dynamic shopping cart application built using Node.js and Express.js. This project demonstrates how to create a RESTful API to manage user shopping carts and perform basic e-commerce operations. Designed as a Junior-level challenge, it showcases full-stack development using JavaScript, Node.js, and Express.

## Features
- **User Management:** Dynamically create and manage users.
- **Shopping Cart Operations:** Add, view, and manage shopping cart items.
- **RESTful API Endpoints:** Clear and structured endpoints for seamless front-end integration.
- **Robust Error Handling:** Gracefully handles missing data and invalid requests.
- **JSON Responses:** Uses JSON to facilitate easy integration with modern front-end frameworks.

## Technologies Used
- **Node.js:** JavaScript runtime environment.
- **Express.js:** Fast, unopinionated, minimalist web framework.
- **Nodemon:** Tool for automatically restarting the server during development.
- **JavaScript (ES6+):** Modern JavaScript syntax and features.
- **JSON:** For structured data exchange.

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/en/download/) installed
- [npm](https://www.npmjs.com/get-npm) (Node Package Manager)

### Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/ExpressCommerce-API.git
   ```
2. **Navigate to the project directory:**
   ```bash
   cd ExpressCommerce-API
   ```
3. **Install dependencies:**
   ```bash
   npm install
   ```

### Running the Application
1. **Start the server:**
   ```bash
   npm start
   ```
2. The server will run on port `8080` (or the port specified in your environment variables).
3. **Interact with the API:** Use a tool like [Postman](https://www.postman.com/) or your browser to test the endpoints.

## API Endpoints

- **GET /**  
  Returns a welcome message.
  ```json
  "Welcome to Blackheart Labs API"
  ```

- **POST /api/users**  
  Create a new user.
  - **Request Body:**
    ```json
    { "username": "john_doe" }
    ```
  - **Response:**
    ```json
    {
      "message": "User john_doe created",
      "user": { "cart": [] }
    }
    ```

- **POST /api/users/:username/cart**  
  Add an item to the user's cart.
  - **Request Body:**
    ```json
    { "item": "Skateboard Deck", "quantity": 1 }
    ```
  - **Response:**
    ```json
    {
      "message": "Added 1 Skateboard Deck(s) to john_doe's cart",
      "cart": [
        { "item": "Skateboard Deck", "quantity": 1 }
      ]
    }
    ```

- **GET /api/users/:username/cart**  
  View the user's shopping cart.
  - **Response:**
    ```json
    {
      "cart": [
        { "item": "Skateboard Deck", "quantity": 1 }
      ]
    }
    ```

## Example API Requests

### Create a New User
```bash
curl -X POST http://localhost:8080/api/users \
  -H "Content-Type: application/json" \
  -d '{"username": "john_doe"}'
```

### Add an Item to the Cart
```bash
curl -X POST http://localhost:8080/api/users/john_doe/cart \
  -H "Content-Type: application/json" \
  -d '{"item": "Skateboard Deck", "quantity": 1}'
```

### View the Shopping Cart
```bash
curl http://localhost:8080/api/users/john_doe/cart
```

## Future Enhancements
- Integrate a database for persistent data storage.
- Add endpoints for updating and removing cart items.
- Implement user authentication.
- Expand the product catalog and incorporate payment integration.

## Contributing
Contributions are welcome! Please fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you'd like to change.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
Created by [Your Name](https://yourwebsite.com) – feel free to reach out for questions or collaborations!
