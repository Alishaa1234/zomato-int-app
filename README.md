# Zomato-Int

A full-stack food delivery application inspired by Zomato, featuring user and food partner authentication, food listings, reel feeds, and more.

## Features

- User registration and login
- Food partner registration and login
- Food creation and management by partners (with image uploads)
- Reel feed for food content
- Saved items functionality
- Responsive UI with React

## Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for authentication
- bcrypt for password hashing
- ImageKit for image handling
- Multer for file uploads
- CORS for cross-origin requests

### Frontend
- React 19
- Vite for build tool
- React Router DOM for routing
- Axios for API calls
- ESLint for linting

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd zomato-int
   ```

2. Install backend dependencies:
   ```bash
   cd backend
   npm install
   ```

3. Install frontend dependencies:
   ```bash
   cd ../frontend
   npm install
   ```

4. Set up environment variables:
   Create a `.env` file in the `backend` directory with the following variables:
   ```
   MONGO_URI=<your-mongodb-connection-string>
   JWT_SECRET=<your-jwt-secret-key>
   IMAGEKIT_PUBLIC_KEY=<your-imagekit-public-key>
   IMAGEKIT_PRIVATE_KEY=<your-imagekit-private-key>
   IMAGEKIT_URL_ENDPOINT=<your-imagekit-url-endpoint>
   ```

5. Start the backend server:
   ```bash
   cd backend
   npm start
   ```
   The backend will run on `http://localhost:3000`.

6. Start the frontend development server:
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on `http://localhost:5173` (or 5174 if 5173 is occupied).

## Usage

- Open your browser and navigate to `http://localhost:5173`.
- Register as a user or food partner.
- Login to access the dashboard.
- Food partners can create and manage food items.
- Users can browse food listings, view reel feeds, and save items.

## API Endpoints

### Authentication
- `POST /api/auth/user/register` - Register a new user
- `POST /api/auth/user/login` - Login user
- `GET /api/auth/user/logout` - Logout user
- `POST /api/auth/food-partner/register` - Register a new food partner
- `POST /api/auth/food-partner/login` - Login food partner
- `GET /api/auth/food-partner/logout` - Logout food partner

### Food
- `POST /api/food/` - Create a new food item (Food partner only, requires authentication)
- `GET /api/food/` - Get food listings (Requires authentication)

### Food Partner
- `GET /api/food-partner/:id` - Get food partner details by ID (User authentication required)

## Project Structure

```
zomato-int/
├── backend/
│   ├── package.json
│   ├── server.js
│   └── src/
│       ├── app.js
│       ├── controllers/
│       ├── db/
│       ├── middlewares/
│       ├── models/
│       ├── routes/
│       └── services/
└── frontend/
    ├── package.json
    ├── vite.config.js
    └── src/
        ├── components/
        ├── pages/
        ├── routes/
        └── styles/
```

## Contributing

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

## License

This project is licensed under the ISC License.
