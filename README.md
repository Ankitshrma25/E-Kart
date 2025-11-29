# E-Commerce Platform

A full-stack e-commerce web application built with React, Redux, Node.js, Express, and MongoDB. This platform includes user authentication, product management, shopping cart, order processing, and payment integration.

## 🚀 Features

- **User Authentication**: Sign up, login, and password reset with JWT-based authentication
- **Product Catalog**: Browse products with filtering by categories and brands
- **Shopping Cart**: Add/remove items, manage quantities, and persistent cart state
- **Checkout & Orders**: Complete checkout process with order tracking
- **Payment Integration**: Razorpay payment gateway integration
- **User Profile**: View and manage user profile and order history
- **Admin Dashboard**: Product management (CRUD operations), order management, and admin controls
- **Responsive Design**: Tailwind CSS for mobile-friendly UI
- **Email Notifications**: Automated emails for confirmations and password resets

## 📋 Tech Stack

### Frontend
- **React** 18.2.0 - UI library
- **Redux Toolkit** - State management
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **React Hook Form** - Form management
- **React Toastify** - Toast notifications
- **Axios** - HTTP client (via API layer)

### Backend
- **Node.js** - Runtime environment
- **Express** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **Passport.js** - Authentication middleware
- **JWT** - Token-based authentication
- **Nodemailer** - Email service
- **Razorpay** - Payment gateway
- **Express Session** - Session management

## 📁 Project Structure

```
e-commerce/
├── client/                    # React frontend application
│   ├── public/               # Static assets
│   ├── src/
│   │   ├── app/             # Redux store configuration
│   │   ├── features/        # Feature modules (Redux slices, APIs, components)
│   │   │   ├── admin/       # Admin management features
│   │   │   ├── auth/        # Authentication features
│   │   │   ├── cart/        # Shopping cart features
│   │   │   ├── order/       # Order management
│   │   │   ├── payment/     # Payment processing
│   │   │   ├── product/     # Product catalog
│   │   │   ├── user/        # User profile features
│   │   │   └── ...          # Other features
│   │   ├── pages/           # Page components
│   │   ├── App.js           # Main app component
│   │   └── index.js         # Entry point
│   └── package.json
│
├── server/                    # Node.js backend application
│   ├── controllers/          # Route handlers for each feature
│   ├── models/               # Mongoose schemas
│   ├── routes/               # API route definitions
│   ├── services/             # Business logic and utilities
│   │   ├── Mails/           # Email templates and sender
│   │   └── Common.js        # Common utilities
│   ├── utils/                # Database connection and helpers
│   ├── index.js              # Server entry point
│   ├── .env.sample           # Environment variables template
│   └── package.json
│
└── LICENSE
```

## 🛠️ Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or pnpm

### Backend Setup

1. Navigate to the server directory:
```bash
cd server
```

2. Install dependencies:
```bash
pnpm install
# or
npm install
```

3. Create a `.env` file based on `.env.sample`:
```bash
cp .env.sample .env
```

4. Update `.env` with your configuration:
```dotenv
PORT=8080
MONGO_URL=mongodb://localhost:27017
DB_NAME=e-commerce
SESSION_SECRET=your_session_secret
JWT_SECRET=your_jwt_secret
NODE_ENV=production
CLIENT_URL=http://localhost:3000
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_SECRET=your_razorpay_secret
EMAIL_ID=your_email@gmail.com
EMAIL_PASSWORD=your_email_password
```

5. Start the server:
```bash
# Development (with hot reload using nodemon)
pnpm dev

# Production
pnpm start
```

The server will run on `http://localhost:8080`

### Frontend Setup

1. Navigate to the client directory:
```bash
cd client
```

2. Install dependencies:
```bash
pnpm install
# or
npm install
```

3. Start the development server:
```bash
pnpm start
```

The client will run on `http://localhost:3000`

## 📚 API Endpoints

### Authentication
- `POST /auth/signup` - Register new user
- `POST /auth/login` - User login
- `GET /auth/logout` - User logout
- `POST /auth/reset-password` - Reset password

### Products
- `GET /product` - Get all products
- `GET /product/:id` - Get product details
- `POST /product` - Create product (Admin)
- `PATCH /product/:id` - Update product (Admin)
- `DELETE /product/:id` - Delete product (Admin)

### Cart
- `GET /cart` - Get user's cart
- `POST /cart` - Add item to cart
- `PATCH /cart/:id` - Update cart item
- `DELETE /cart/:id` - Remove from cart

### Orders
- `POST /order` - Create order
- `GET /order` - Get user's orders
- `GET /order/:id` - Get order details
- `GET /admin/orders` - Get all orders (Admin)

### Payment
- `POST /payment` - Process payment

### Users
- `GET /user/:id` - Get user profile
- `PATCH /user/:id` - Update user profile

### Categories
- `GET /category` - Get all categories
- `POST /category` - Create category (Admin)

### Brands
- `GET /brands` - Get all brands
- `POST /brands` - Create brand (Admin)

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication:
- Tokens are issued upon login and stored in cookies/localStorage
- Protected routes require valid JWT tokens
- Passport.js is configured for local and JWT strategies
- Admin routes have additional authorization checks

## 🛒 Key Features Details

### Shopping Cart
- Real-time cart updates with Redux state management
- Persistent cart storage
- Quantity management
- Price calculations with discounts

### Checkout Process
1. Review cart items
2. Enter shipping address
3. Select payment method
4. Process payment via Razorpay
5. Order confirmation

### Admin Dashboard
- Product management (create, read, update, delete)
- Order management and tracking
- User management capabilities
- Sales analytics

### Email Notifications
- Welcome email on signup
- Order confirmation email
- Password reset link
- Order status updates

## 🧪 Testing

### Frontend
```bash
cd client
pnpm test
```

### Backend
```bash
cd server
pnpm test
```

## 📦 Build & Deployment

### Frontend Build
```bash
cd client
pnpm build
```

The build artifacts will be stored in the `build/` directory.

### Backend Deployment
Ensure all environment variables are configured, then:
```bash
cd server
pnpm start
```

## 📝 Environment Variables

### Server `.env` Configuration
| Variable | Description |
|----------|-------------|
| `PORT` | Server port (default: 8080) |
| `MONGO_URL` | MongoDB connection string |
| `DB_NAME` | Database name |
| `SESSION_SECRET` | Express session secret |
| `JWT_SECRET` | JWT signing secret |
| `NODE_ENV` | Environment (production/development) |
| `CLIENT_URL` | Frontend URL for CORS |
| `RAZORPAY_KEY_ID` | Razorpay merchant key ID |
| `RAZORPAY_SECRET` | Razorpay secret key |
| `EMAIL_ID` | Gmail account for sending emails |
| `EMAIL_PASSWORD` | Gmail app password |

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

Aryan Baadlas

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB is running locally or cloud connection is accessible
- Verify `MONGO_URL` in `.env` is correct

### Payment Gateway Not Working
- Confirm Razorpay credentials are correct
- Ensure `RAZORPAY_KEY_ID` and `RAZORPAY_SECRET` are valid

### Email Issues
- Use Gmail app password (not regular password)
- Enable "Less secure app access" if using regular Gmail password
- Verify `EMAIL_ID` and `EMAIL_PASSWORD` are correct

### CORS Errors
- Ensure `CLIENT_URL` in backend `.env` matches your frontend URL
- Check frontend API endpoints are pointing to correct backend URL

## 📖 Additional Resources

- [React Documentation](https://react.dev)
- [Redux Toolkit Documentation](https://redux-toolkit.js.org)
- [Express.js Documentation](https://expressjs.com)
- [MongoDB Documentation](https://docs.mongodb.com)
- [Tailwind CSS Documentation](https://tailwindcss.com)
- [Razorpay Documentation](https://razorpay.com/docs)

---

For questions or issues, please open an issue in the repository or contact the author.
