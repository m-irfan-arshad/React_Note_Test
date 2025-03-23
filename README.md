# React & Node.js CRM Application

## Project Description
This is a full-stack Customer Relationship Management (CRM) application built with React.js for the frontend and Node.js for the backend. The application allows users to manage contacts, leads, meetings, tasks, and other business operations efficiently. It features a responsive UI built with Chakra UI and implements RESTful API architecture for seamless client-server communication.

## Tech Stack

### Backend
- **Node.js**: JavaScript runtime environment
- **Express.js**: Web application framework
- **MongoDB**: NoSQL database for data storage
- **Mongoose**: MongoDB object modeling for Node.js
- **JWT**: JSON Web Tokens for authentication
- **Bcrypt**: Password hashing library
- **Nodemailer**: Email sending functionality
- **Multer**: File upload handling
- **Cors**: Cross-Origin Resource Sharing middleware
- **Dotenv**: Environment variable management

### Frontend
- **React**: JavaScript library for building user interfaces
- **Redux**: State management
- **Redux Toolkit**: Toolset for efficient Redux development
- **Redux Persist**: Local storage persistence for Redux
- **Chakra UI**: Component library for building UI
- **Formik & Yup**: Form handling and validation
- **Axios**: HTTP client for API requests
- **React Router Dom**: Navigation and routing
- **React Toastify**: Toast notifications
- **FullCalendar**: Calendar component for scheduling
- **Chart.js/ApexCharts**: Data visualization
- **Moment.js/Dayjs**: Date manipulation

## Installation & Setup

### Prerequisites
- Node.js (v14.x or later)
- MongoDB (local installation or MongoDB Atlas account)
- npm or yarn package manager

### MongoDB Setup
1. **Local MongoDB Setup**
   - Download and install MongoDB Community Server from the [official website](https://www.mongodb.com/try/download/community)
   - Follow the installation wizard instructions for your operating system
   - Start MongoDB service:
     - Windows: `net start MongoDB`
     - macOS: `brew services start mongodb-community`
     - Linux: `sudo systemctl start mongod`
   - Verify installation by connecting to MongoDB shell:
     ```bash
     mongosh
     ```

2. **MongoDB Atlas Setup (Cloud Alternative)**
   - Create a free account on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/register)
   - Create a new cluster (the free tier is sufficient for development)
   - Configure network access: Add your IP address to the IP Access List
   - Create a database user with read/write privileges
   - Get your connection string from the "Connect" button on your cluster
   - Replace the `DB_URL` in your `.env` file with the Atlas connection string:
     ```
     DB_URL=mongodb+srv://<username>:<password>@<cluster-url>/<database-name>?retryWrites=true&w=majority
     ```

3. **Database Initialization**
   - The application will automatically create the necessary collections when it first runs
   - No additional setup is required for schema creation

### Installing Dependencies
1. Clone the repository
   ```bash
   git clone [repository-url]
   cd [project-folder]
   ```

2. Install server dependencies
   ```bash
   cd server
   npm install
   ```

3. Install client dependencies
   ```bash
   cd ../Client
   npm install
   ```

4. Verify installation
   - Both installations should complete without errors
   - Check for the node_modules directory in both server and Client folders
   - If you encounter any errors, make sure your Node.js and npm versions are compatible with the project

### Backend Setup
1. Navigate to the server directory (if not already there)
   ```bash
   cd server
   ```

2. Create a `.env` file in the server directory with the following variables:
   ```
   PORT=5001
   DB_URL=mongodb://127.0.0.1:27017/?directConnection=true
   DB=Prolink
   JWT_SECRET=your-secret-key
   NODE_ENV=development
   ```

3. Start the server
   ```bash
   npm start
   ```
   The server will run on http://localhost:5001

### Frontend Setup
1. Navigate to the Client directory (if not already there)
   ```bash
   cd Client
   ```

2. Create a `.env` file in the Client directory with the following variables:
   ```
   REACT_APP_BASE_URL=http://localhost:5001/
   REACT_APP_ENV=development
   REACT_APP_NAME="React Node Test"
   ```

3. Start the client application
   ```bash
   npm start
   ```
   The application will run on http://localhost:3000

## Usage & Features

### Authentication
- Login with email and password
- Default admin credentials:
  - Email: admin@gmail.com
  - Password: admin123

### Core Functionalities
- **Dashboard**: Overview of key metrics and activities
- **Contacts Management**: Create, view, edit, and delete contacts
- **Lead Management**: Track and manage leads through the sales pipeline
- **Meeting Management**: Schedule and manage meetings with contacts and leads
- **Task Management**: Create and track tasks with deadlines
- **Email Templates**: Create and manage reusable email templates
- **Documents**: Upload and manage documents
- **Calendar**: View scheduled activities in calendar format
- **User Management**: Create and manage user accounts with role-based access control

## Architecture & Design

### System Architecture
The application follows a client-server architecture:

1. **Frontend (React.js)**
   - Component-based UI architecture
   - State management with Redux
   - API communication via Axios

2. **Backend (Node.js/Express)**
   - RESTful API endpoints
   - MVC (Model-View-Controller) pattern
   - Middleware for authentication and validation
   - MongoDB database for data persistence

### Data Flow
1. Client makes API requests to the server
2. Server processes requests through appropriate controllers
3. Controllers interact with models to fetch/store data
4. Server responds with data or status messages
5. Client updates UI based on response

## API Documentation

### Authentication
- **POST /api/user/login**: User login

### Contacts
- **GET /api/contact**: Get all contacts
- **GET /api/contact/:id**: Get contact by ID
- **POST /api/contact/add**: Create new contact
- **PUT /api/contact/edit/:id**: Update contact
- **DELETE /api/contact/delete/:id**: Delete contact

### Leads
- **GET /api/lead**: Get all leads
- **GET /api/lead/:id**: Get lead by ID
- **POST /api/lead/add**: Create new lead
- **PUT /api/lead/edit/:id**: Update lead
- **DELETE /api/lead/delete/:id**: Delete lead

### Meetings
- **GET /api/meeting**: Get all meetings
- **GET /api/meeting/view/:id**: Get meeting by ID
- **POST /api/meeting/add**: Create new meeting
- **PUT /api/meeting/edit/:id**: Update meeting
- **DELETE /api/meeting/delete/:id**: Delete meeting

### Tasks
- **GET /api/task**: Get all tasks
- **GET /api/task/:id**: Get task by ID
- **POST /api/task/add**: Create new task
- **PUT /api/task/edit/:id**: Update task
- **DELETE /api/task/delete/:id**: Delete task

## Deployment Guide

### Development Environment
Follow the installation and setup instructions above for local development.

### Production Environment
1. **Backend Deployment**
   - Set NODE_ENV=production in .env
   - Configure production MongoDB connection
   - Deploy to hosting service (AWS, Heroku, DigitalOcean, etc.)

2. **Frontend Deployment**
   - Create production build: `npm run build`
   - Deploy static files to hosting service (Netlify, Vercel, AWS S3, etc.)
   - Set REACT_APP_ENV=production and update REACT_APP_BASE_URL to point to production backend URL

## Testing & Debugging

### Running Tests
```bash
# Server tests
cd server
npm test

# Client tests
cd Client
npm test
```

### Debugging
- Check server logs for backend issues
- Use browser developer tools for frontend debugging
- Check network requests to identify API issues

## Contributing Guide

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes following the code style of the project
4. Write tests for your changes if applicable
5. Commit your changes: `git commit -m 'Add some feature'`
6. Push to the branch: `git push origin feature/your-feature-name`
7. Submit a pull request

### Coding Standards
- Follow existing code style and conventions
- Use meaningful variable and function names
- Write clear comments when necessary
- Keep components and functions focused and small

## License & Credits

### License
This project is licensed under the ISC License

### Credits
- React.js team and contributors
- Node.js and Express.js teams and contributors
- Chakra UI team and contributors
- All open-source libraries used in this project