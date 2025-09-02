# 🏛️ Swachh Bharat Community App

[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://www.javascript.com/)

> A revolutionary mobile web application empowering citizens to actively participate in India's Swachh Bharat Mission through anonymous issue reporting, geotagged photos, and community-driven cleanliness initiatives.

## 🌟 Features

### 👥 For Citizens
- **Anonymous Reporting**: Report cleanliness issues without creating accounts
- **Photo Evidence**: Capture and upload photos with camera integration
- **GPS Geotagging**: Automatic location tracking for precise issue mapping
- **Real-time Feed**: Twitter-like social feed showcasing community updates
- **Progress Tracking**: View before/after photos of resolved issues

### 🏛️ For Authorities
- **Admin Dashboard**: Secure login-protected management interface
- **Issue Management**: Update status, add responses, and track progress
- **Photo Upload**: Upload "after" photos showing completed work
- **Analytics**: View statistics and monitor community engagement
- **Response System**: Communicate directly with citizens

### 📱 Technical Features
- **Progressive Web App**: Installable on mobile devices
- **Offline Support**: Basic functionality works without internet
- **Responsive Design**: Optimized for all screen sizes
- **Real-time Updates**: Live synchronization across devices

## 🚀 Live Demo

🌐 **[View Live Application](https://swachh-bharat-app-2f527.web.app)**

### Demo Credentials
- **Admin Email**: `admin@swachhbharat.com`
- **Admin Password**: `admin123`

## 🛠️ Technology Stack

### Frontend
- **React.js** - Modern JavaScript library for building user interfaces
- **React Router** - Declarative routing for React applications
- **CSS3** - Responsive styling with mobile-first approach

### Backend & Database
- **Firebase Firestore** - NoSQL cloud database for real-time data
- **Firebase Storage** - Cloud storage for photo uploads
- **Firebase Authentication** - Secure user authentication system
- **Firebase Hosting** - Fast, secure web hosting

### Development Tools
- **Create React App** - Build setup and development server
- **ESLint** - Code linting and formatting
- **Git** - Version control system

## 📋 Prerequisites

Before running this application, make sure you have:
- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **Firebase Account** with project created

## 🔧 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/swachh-bharat-app.git
cd swachh-bharat-app
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Firebase Configuration
1. Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable the following services:
   - **Authentication** (Email/Password)
   - **Firestore Database**
   - **Storage**
   - **Hosting**

3. Update `src/firebase.js` with your Firebase config:
```javascript
const firebaseConfig = {
  apiKey: "your-api-key",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "your-sender-id",
  appId: "your-app-id"
};
```

### 4. Firebase Security Rules

**Firestore Rules** (`firestore.rules`):
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Allow public read/write for reports (hackathon demo)
    match /reports/{document} {
      allow read, write: if true;
    }
  }
}
```

**Storage Rules** (`storage.rules`):
```javascript
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read, write: if true;
    }
  }
}
```

### 5. Create Admin User
1. Go to Firebase Console → Authentication → Users
2. Add user: `admin@swachhbharat.com` / `admin123`

### 6. Run the Application
```bash
npm start
```

The app will open at `http://localhost:3000`

## 🚀 Deployment

### Firebase Hosting (Recommended)
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize Firebase (select Hosting)
firebase init

# Build and deploy
npm run build
firebase deploy
```

### Alternative Platforms
- **Vercel**: `npm install -g vercel && vercel --prod`
- **Netlify**: `npm install -g netlify-cli && netlify deploy --prod --dir=build`

## 📱 Usage

### For Citizens
1. **Visit the Homepage**: View community updates and recent reports
2. **Report an Issue**:
   - Click "Report Issue" button
   - Fill in issue details and category
   - Take/select a photo
   - Allow location access for geotagging
   - Submit anonymously

### For Administrators
1. **Access Admin Panel**: Click "Admin Login"
2. **Login**: Use admin credentials
3. **Manage Reports**:
   - View all submitted reports
   - Update status (Pending → In Progress → Resolved)
   - Add responses to citizens
   - Upload "after" photos for completed work

## 🏗️ Project Structure

```
swachh-bharat-app/
├── public/
│   ├── index.html
│   ├── manifest.json
│   └── robots.txt
├── src/
│   ├── components/
│   │   ├── PhotoFeed.js      # Twitter-like social feed
│   │   ├── ReportForm.js     # Issue reporting interface
│   │   ├── AdminLogin.js     # Admin authentication
│   │   ├── AdminDashboard.js # Admin management panel
│   │   └── Home.js           # Landing page
│   ├── firebase.js           # Firebase configuration
│   ├── App.js               # Main application component
│   └── index.js             # Application entry point
├── package.json
└── README.md
```

## 🎯 Key Components

### PhotoFeed Component
- Displays community reports in a social media format
- Real-time updates from Firestore
- Filtering by status and category
- Before/after photo comparisons

### ReportForm Component
- Anonymous issue submission
- Camera integration for photo capture
- GPS location services
- Form validation and error handling

### AdminDashboard Component
- Secure admin interface
- Report management and status updates
- Response system for citizen communication
- Analytics and statistics

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature-name`
3. **Commit** your changes: `git commit -m 'Add feature'`
4. **Push** to the branch: `git push origin feature-name`
5. **Submit** a Pull Request

### Development Guidelines
- Follow React best practices
- Use meaningful commit messages
- Test on multiple devices/browsers
- Maintain responsive design principles

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Swachh Bharat Mission** - Inspiring the vision for cleaner communities
- **Firebase** - Providing robust backend services
- **React Community** - Building amazing user interfaces
- **Open Source Contributors** - Making technology accessible

## 📞 Support

For support or questions:
- Create an [Issue](https://github.com/your-username/swachh-bharat-app/issues)
- Contact the development team
- Check the [Documentation](https://github.com/your-username/swachh-bharat-app/wiki)

## 🎉 Impact

This application empowers citizens to actively participate in maintaining clean public spaces, fostering community engagement and supporting India's Swachh Bharat Mission. By providing an easy-to-use platform for reporting issues and tracking progress, we're building a cleaner, more connected India.

---

**Made with ❤️ for India's Swachh Bharat Mission**

⭐ **Star this repository** if you find it helpful!
