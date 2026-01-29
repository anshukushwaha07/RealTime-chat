# RealTime Chat Application

A modern, full-featured real-time chat application built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring WebSocket communication for instant messaging, beautiful UI components with DaisyUI, and message persistence.

[![Live Demo](https://img.shields.io/badge/demo-online-green.svg)](https://realtime-chat-hztu.onrender.com)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-v14+-green.svg)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-v18+-blue.svg)](https://reactjs.org)

## 🌟 Features

- **Real-Time Messaging**: Instant message delivery using WebSocket technology
- **User Authentication**: Secure user registration and login system
- **Message Persistence**: All conversations are saved to MongoDB
- **Responsive Design**: Mobile-friendly interface built with DaisyUI and Tailwind CSS
- **Online Status**: See which users are currently active
- **Message History**: Access previous conversations anytime
- **Modern UI/UX**: Beautiful, intuitive interface with smooth animations
- **Typing Indicators**: Know when someone is typing a message
- **User Profiles**: Customizable user profiles with avatars
- **Private Messaging**: One-on-one conversations

## 🚀 Demo

Check out the live demo: [https://realtime-chat-hztu.onrender.com](https://realtime-chat-hztu.onrender.com)

## 📸 Screenshots

*Add your application screenshots here*

## 🛠️ Tech Stack

### Frontend
- **React** - UI library for building interactive interfaces
- **DaisyUI** - Component library built on Tailwind CSS
- **Tailwind CSS** - Utility-first CSS framework
- **Socket.IO Client** - Real-time bidirectional communication
- **React Router** - Client-side routing
- **Axios** - HTTP client for API requests

### Backend
- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database for data persistence
- **Mongoose** - MongoDB object modeling
- **Socket.IO** - WebSocket library for real-time communication
- **JWT** - JSON Web Tokens for authentication
- **bcrypt** - Password hashing

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- npm or yarn
- MongoDB (local or Atlas account)
- Git

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/anshukushwaha07/RealTime-chat.git
cd RealTime-chat
```

### 2. Install dependencies

Install root dependencies:
```bash
npm install
```

Install backend dependencies:
```bash
cd backend
npm install
```

Install frontend dependencies:
```bash
cd ../frontend
npm install
```

### 3. Environment Variables

Create a `.env` file in the `backend` directory with the following variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=your_mongodb_connection_string

# JWT Secret
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d

# Client URL (for CORS)
CLIENT_URL=http://localhost:3000

# Socket.IO Configuration
SOCKET_PORT=5000
```

Create a `.env` file in the `frontend` directory:

```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_SOCKET_URL=http://localhost:5000
```

### 4. MongoDB Setup

You can use either:
- **MongoDB Atlas** (Cloud): Create a free cluster at [mongodb.com](https://www.mongodb.com/cloud/atlas)
- **Local MongoDB**: Install MongoDB locally

Update your `MONGODB_URI` in the backend `.env` file accordingly.

## 🚀 Running the Application

### Development Mode

Run both frontend and backend concurrently from the root directory:

```bash
npm run dev
```

Or run them separately:

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend:**
```bash
cd frontend
npm start
```

The application will be available at:
- Frontend: `http://localhost:3000`
- Backend: `http://localhost:5000`

### Production Mode

Build the frontend:
```bash
cd frontend
npm run build
```

Start the backend server:
```bash
cd backend
npm start
```

## 📁 Project Structure

```
RealTime-chat/
├── backend/
│   ├── config/
│   │   └── db.js              # Database configuration
│   ├── controllers/
│   │   ├── authController.js  # Authentication logic
│   │   └── messageController.js # Message handling
│   ├── models/
│   │   ├── User.js            # User model
│   │   └── Message.js         # Message model
│   ├── routes/
│   │   ├── auth.js            # Authentication routes
│   │   └── messages.js        # Message routes
│   ├── middleware/
│   │   └── auth.js            # Authentication middleware
│   ├── socket/
│   │   └── socket.js          # Socket.IO configuration
│   ├── utils/
│   │   └── generateToken.js   # JWT token generation
│   └── server.js              # Main server file
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Chat/
│   │   │   ├── Sidebar/
│   │   │   └── Auth/
│   │   ├── context/
│   │   │   ├── AuthContext.js
│   │   │   └── SocketContext.js
│   │   ├── hooks/
│   │   ├── pages/
│   │   │   ├── Home.js
│   │   │   ├── Login.js
│   │   │   └── Register.js
│   │   ├── utils/
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   └── tailwind.config.js
├── package.json
└── README.md
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/logout` - Logout user
- `GET /api/auth/me` - Get current user

### Messages
- `GET /api/messages/:userId` - Get messages with a specific user
- `POST /api/messages/send/:userId` - Send a message to a user
- `GET /api/messages/conversations` - Get all conversations

### Users
- `GET /api/users` - Get all users
- `GET /api/users/:id` - Get user by ID

## 🔐 WebSocket Events

### Client → Server
- `join` - User joins the chat
- `sendMessage` - Send a new message
- `typing` - User is typing
- `stopTyping` - User stopped typing

### Server → Client
- `message` - New message received
- `userOnline` - User came online
- `userOffline` - User went offline
- `typing` - Someone is typing
- `stopTyping` - Typing stopped

## 🎨 Customization

### Changing Theme

The application uses DaisyUI themes. You can customize the theme in `frontend/tailwind.config.js`:

```javascript
module.exports = {
  daisyui: {
    themes: ["light", "dark", "cupcake", "cyberpunk"],
  },
}
```

### Styling Components

All components are styled using Tailwind CSS utility classes and DaisyUI components. Modify component files in `frontend/src/components/` to customize the UI.

## 🧪 Testing

Run tests (if implemented):

```bash
# Backend tests
cd backend
npm test

# Frontend tests
cd frontend
npm test
```

## 🚢 Deployment

### Backend Deployment (Render/Heroku)

1. Create a new web service on Render or Heroku
2. Connect your GitHub repository
3. Set environment variables
4. Deploy

### Frontend Deployment (Vercel/Netlify)

1. Build the frontend: `npm run build`
2. Deploy the `build` folder to Vercel or Netlify
3. Set environment variables

### Full Stack Deployment (Render)

The repository is configured for deployment on Render. The live demo is hosted at:
[https://realtime-chat-hztu.onrender.com](https://realtime-chat-hztu.onrender.com)

## 🐛 Troubleshooting

### WebSocket Connection Issues
- Ensure CORS is properly configured
- Check if Socket.IO ports are correct
- Verify that the backend server is running

### Database Connection Problems
- Verify MongoDB URI is correct
- Check network access in MongoDB Atlas
- Ensure IP whitelist includes your current IP

### Build Errors
- Clear node_modules and reinstall: `rm -rf node_modules && npm install`
- Check Node.js version compatibility
- Verify all environment variables are set

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Anshu Kushwaha**
- GitHub: [@anshukushwaha07](https://github.com/anshukushwaha07)

## 🙏 Acknowledgments

- [Socket.IO](https://socket.io/) for real-time communication
- [DaisyUI](https://daisyui.com/) for beautiful UI components
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [MongoDB](https://www.mongodb.com/) for database
- [React](https://reactjs.org/) for the frontend framework

## 📧 Contact

For questions or support, please open an issue on GitHub or contact the repository owner.

## 🗺️ Roadmap

- [ ] Group chat functionality
- [ ] File and image sharing
- [ ] Voice and video calls
- [ ] Message reactions and emojis
- [ ] Read receipts
- [ ] Message search functionality
- [ ] User blocking and reporting
- [ ] End-to-end encryption
- [ ] Mobile app (React Native)
- [ ] Desktop app (Electron)

## ⚡ Performance

- Optimized WebSocket connections
- Efficient database queries with indexing
- Lazy loading for message history
- Debounced typing indicators
- Compression for API responses

---

**Star ⭐ this repository if you found it helpful!**
