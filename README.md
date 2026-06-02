# Event Registration Portal

A complete web application for managing event registrations with user and admin functionalities.

## 🎯 Project Overview

The Event Registration Portal is a platform where users can browse events, register for events, and manage their registrations. Event organizers and administrators can create, edit, and manage events with a comprehensive admin dashboard.

## 🛠️ Technology Stack

- **Frontend**: React.js, HTML, CSS, Bootstrap 5
- **Backend**: Node.js with Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Token)
- **Version Control**: Git & GitHub

## 📋 Features

### User Features
- ✅ User Registration & Login
- ✅ Browse all events
- ✅ Search and filter events
- ✅ Register for events
- ✅ View registered events
- ✅ Download registration confirmation
- ✅ Update user profile
- ✅ Forgot password functionality

### Admin Features
- ✅ Secure admin login
- ✅ Create, edit, and delete events
- ✅ View all registered users
- ✅ Manage user registrations
- ✅ Dashboard with statistics
- ✅ Event-wise registration reports

### Core Modules
1. **Authentication Module** - JWT-based auth with role-based access control
2. **Event Management** - Create, read, update, delete events
3. **Registration Module** - User event registration and seat tracking
4. **Dashboard Module** - Analytics and reports
5. **Notification Module** - Email confirmations

## 📁 Project Structure

```
event-registration-portal/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   └── .env
│
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── models/
│   ├── middleware/
│   ├── config/
│   ├── server.js
│   ├── package.json
│   └── .env
│
├── README.md
├── .gitignore
└── SETUP.md
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Backend Setup

```bash
cd backend
npm install
npm start
```

Create `.env` file in backend folder:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/event-portal
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
```

### Frontend Setup

```bash
cd frontend
npm install
npm start
```

Create `.env` file in frontend folder:
```
REACT_APP_API_URL=http://localhost:5000/api
```

## 📊 Database Collections

### Users
```
{
  _id: ObjectId,
  name: String,
  email: String,
  password: String (hashed),
  role: String (user/admin),
  createdAt: Date,
  updatedAt: Date
}
```

### Events
```
{
  _id: ObjectId,
  eventName: String,
  description: String,
  date: Date,
  venue: String,
  category: String,
  availableSeats: Number,
  totalSeats: Number,
  organizer: ObjectId (reference to Users),
  image: String,
  createdAt: Date,
  updatedAt: Date
}
```

### Registrations
```
{
  _id: ObjectId,
  userId: ObjectId (reference to Users),
  eventId: ObjectId (reference to Events),
  registrationDate: Date,
  status: String (confirmed/cancelled),
  seatsBooked: Number,
  createdAt: Date,
  updatedAt: Date
}
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/forgot-password` - Forgot password
- `POST /api/auth/reset-password` - Reset password

### Events
- `GET /api/events` - Get all events
- `GET /api/events/:id` - Get event details
- `POST /api/events` - Create event (Admin)
- `PUT /api/events/:id` - Update event (Admin)
- `DELETE /api/events/:id` - Delete event (Admin)
- `GET /api/events/search?query=` - Search events

### Registrations
- `POST /api/registrations` - Register for event
- `GET /api/registrations/user/:userId` - Get user registrations
- `GET /api/registrations` - Get all registrations (Admin)
- `DELETE /api/registrations/:id` - Cancel registration
- `GET /api/registrations/event/:eventId` - Get event registrations (Admin)

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `GET /api/users` - Get all users (Admin)
- `DELETE /api/users/:id` - Delete user (Admin)

### Dashboard
- `GET /api/dashboard/stats` - Get dashboard statistics (Admin)
- `GET /api/dashboard/reports` - Get registration reports (Admin)

## 🔐 Authentication

The application uses JWT for authentication:
1. User registers/logs in
2. Server returns JWT token
3. Token stored in localStorage
4. Token sent in every API request header
5. Server validates token for protected routes

## 📱 Pages

### Public Pages
- Home Page
- About Page
- Contact Page
- Event Listing Page
- Event Details Page

### User Pages
- Login
- Register
- Profile
- My Registrations

### Admin Pages
- Dashboard
- Manage Events
- Manage Users
- Registration Reports

## 🎨 UI/UX Features

- Responsive design (Mobile, Tablet, Desktop)
- Modern dashboard with Bootstrap 5
- Professional color theme
- Loading indicators
- Form validation
- Error handling
- Pagination for lists

## 📧 Email Notifications

- Registration confirmation emails
- Password reset emails
- Event reminder emails (optional)

## 🚢 Deployment

### Frontend Deployment (Vercel/Netlify)
```bash
cd frontend
npm run build
# Deploy build folder to Vercel/Netlify
```

### Backend Deployment (Heroku/Railway)
```bash
cd backend
git push heroku main
```

## 📖 Documentation

- API Documentation: See `backend/API_DOCS.md`
- Setup Guide: See `SETUP.md`
- Development Guide: See `DEVELOPMENT.md`

## 🤝 Contributing

1. Create a feature branch
2. Make your changes
3. Create a pull request
4. Get review approval
5. Merge to main

## 📝 License

MIT License - feel free to use this project

## 👥 Author

Created by Event Registration Portal Team

## 📞 Support

For issues and questions, please create an issue on GitHub.

---

**Happy Coding! 🎉**
