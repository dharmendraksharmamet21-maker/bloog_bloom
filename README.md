# Bloog

A full-stack blog application built with Node.js, Express, MongoDB, and React. Users can register, log in, create and edit posts with rich text editing, and view posts in a clean, responsive interface.

## Features

- **User Authentication**: Register and login with JWT-based sessions.
- **Post Management**: Create, edit, and view blog posts.
- **Rich Text Editor**: Integrated Quill editor for post content.
- **File Uploads**: Optional image uploads for post covers.
- **Responsive Design**: Mobile-friendly UI with React.
- **RESTful API**: Backend endpoints for CRUD operations on users and posts.
- **MongoDB Integration**: NoSQL database for data persistence.

## Tech Stack

- **Backend**: Node.js, Express.js, MongoDB, Mongoose, JWT, bcryptjs, Multer
- **Frontend**: React 19, React Router, React Quill (for rich text), Axios (for API calls)
- **Database**: MongoDB (local or Atlas)
- **Other**: HTML, CSS, JavaScript

## Folder Structure

```
bloog/
├── backend/                 # Express server
│   ├── index.js            # Main server file
│   ├── models/             # Mongoose schemas (User, Post)
│   └── package.json        # Backend dependencies
├── frontend/
│   └── client/             # React app
│       ├── src/
│       │   ├── components/ # Reusable components (Editor, Header, etc.)
│       │   ├── pages/     # Page components (IndexPage, LoginPage, etc.)
│       │   └── App.js     # Main app component with routing
│       └── package.json    # Frontend dependencies
└── README.md               # This file
```

## Getting Started

### Prerequisites

- Node.js (v16 or higher recommended)
- MongoDB (local installation or MongoDB Atlas account)
- npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd bloog
   ```

2. Install backend dependencies:
   ```bash
   cd backend
   npm install
   ```

3. Install frontend dependencies:
   ```bash
   cd ../frontend/client
   npm install
   ```

### Running Locally

1. Start MongoDB (if using local):
   ```bash
   brew services start mongodb-community  # macOS with Homebrew
   # Or use MongoDB Atlas for cloud DB
   ```

2. Start the backend server:
   ```bash
   cd backend
   npm start  # Runs on http://localhost:4000
   ```

3. Start the frontend development server:
   ```bash
   cd ../frontend/client
   npm start  # Runs on http://localhost:3000
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Environment Variables

No environment variables are configured. The app uses hardcoded values for MongoDB connection and JWT secret. For production, consider adding:

| Key          | Description              | Example                          |
|--------------|--------------------------|----------------------------------|
| MONGODB_URI | MongoDB connection URL  | mongodb://localhost:27017/bloog |
| JWT_SECRET  | Secret for JWT signing  | your-secret-key                  |

## Available Scripts

### Backend (in `backend/` directory)
- `npm start`: Start the production server
- `npm run dev`: Start with nodemon for development

### Frontend (in `frontend/client/` directory)
- `npm start`: Start the development server
- `npm run build`: Build the app for production
- `npm test`: Run tests (currently no tests configured)
- `npm run eject`: Eject from Create React App

## API Routes

### Authentication
- `POST /register`: Register a new user
- `POST /login`: Login user
- `POST /logout`: Logout user
- `GET /profile`: Get user profile (requires auth)

### Posts
- `GET /post`: Get all posts
- `GET /post/:id`: Get a specific post
- `POST /post`: Create a new post (requires auth, optional file upload)
- `PUT /post`: Update an existing post (requires auth, optional file upload)

## Testing

No tests are currently implemented. To add tests:
- Backend: Use Jest or Mocha for API testing.
- Frontend: Use React Testing Library for component tests.

## Troubleshooting

- **"Failed to fetch" errors**: Ensure both backend (port 4000) and frontend (port 3000) are running. Check MongoDB connection.
- **MongoDB connection issues**: Verify MongoDB is running locally or update the connection string in `backend/index.js`.
- **File upload errors**: Ensure the `uploads/` directory exists in the backend root.
- **React Quill issues**: If the editor doesn't load, check for console errors related to React 19 compatibility.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature-name`.
3. Commit changes: `git commit -m 'Add feature'`.
4. Push to branch: `git push origin feature-name`.
5. Open a pull request.

## License

Not specified.
