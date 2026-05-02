# Frontend Setup Guide

## Prerequisites
- Node.js v18+
- npm atau yarn

## Installation

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Setup environment variables:**
   ```bash
   cp .env.example .env
   # Edit .env dengan API URL yang sesuai
   ```

4. **Start development server:**
   ```bash
   npm run dev
   ```

Application akan berjalan di `http://localhost:3000`

## Project Structure

```
frontend/
├── src/
│   ├── App.jsx                # Main app component
│   ├── main.jsx               # React entry point
│   ├── index.css              # Global styles
│   ├── components/            # Reusable components
│   │   ├── Navbar.jsx
│   │   └── ProtectedRoute.jsx
│   ├── pages/                 # Page components
│   │   ├── Login.jsx
│   │   ├── Dashboard.jsx
│   │   ├── QRScanner.jsx
│   │   ├── Classes.jsx
│   │   ├── Students.jsx
│   │   └── Reports.jsx
│   ├── hooks/                 # Custom hooks
│   │   └── useApi.js
│   └── stores/                # Zustand stores
│       ├── authStore.js
│       └── attendanceStore.js
├── index.html
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
├── package.json
└── README.md
```

## Features

### Pages
- **Login** - User authentication
- **Dashboard** - Overview dan quick actions
- **QR Scanner** - Scan attendance QR codes
- **Classes** - Manage classes
- **Students** - Manage students
- **Reports** - View attendance reports with charts

### Components
- **Navbar** - Navigation bar with user menu
- **ProtectedRoute** - Protected route wrapper for authentication

### State Management
- **authStore** - Authentication state (Zustand)
- **attendanceStore** - Attendance state (Zustand)

### Styling
- **Tailwind CSS** - Utility-first CSS framework
- **Responsive Design** - Mobile-friendly layouts

## Building

```bash
npm run build
```

Build output akan tersimpan di direktori `dist/`

## Preview Production Build

```bash
npm run preview
```

## Linting

```bash
npm run lint
```

## Environment Variables

```env
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=QR Attendance System
VITE_SOCKET_URL=http://localhost:5000
```

## Deployment

See main project `DEPLOYMENT.md` for deployment instructions.
