# QR Attendance App 📱

**Sistem absensi siswa berbasis QR Code dengan dashboard rekap per kelas**

Platform manajemen kehadiran siswa yang modern, efisien, dan mudah digunakan dengan teknologi QR Code scanning.

---

## ✨ Fitur Utama

### 👨‍🏫 Guru/Pendidik
- 📱 Scan QR Code siswa untuk absensi real-time
- 📊 Dashboard rekap kehadiran per kelas
- 📈 Laporan lengkap (harian, mingguan, bulanan)
- 🔔 Notifikasi siswa yang sering absen
- 📥 Ekspor data kehadiran (CSV, PDF)
- ⚙️ Kelola kelas dan daftar siswa

### 👨‍🎓 Siswa
- 📲 Dapatkan QR Code personal
- 👁️ Lihat riwayat kehadiran
- 🔔 Notifikasi absensi otomatis
- 📱 Interface mobile-friendly

### 🔐 Admin
- 👥 Manajemen pengguna (guru, siswa, admin)
- 🏫 Kelola sekolah/institusi
- 📋 Konfigurasi sistem
- 📊 Laporan keseluruhan

---

## 🛠 Tech Stack

### Backend
- **Runtime:** Node.js (v18+)
- **Framework:** Express.js atau Fastify
- **Database:** PostgreSQL atau MongoDB
- **Authentication:** JWT + Bcrypt
- **QR Code:** qrcode library
- **File Export:** PDFKit, ExcelJS
- **Notifications:** Socket.io, Nodemailer

### Frontend (Web)
- **Framework:** React 18+
- **Styling:** Tailwind CSS
- **State Management:** Redux atau Zustand
- **HTTP Client:** Axios
- **Charts:** Chart.js atau Recharts
- **QR Reader:** jsQR, html5-qrcode

### Mobile (Optional)
- **Framework:** React Native atau Flutter
- **QR Scanner:** react-native-camera atau Camera plugin
- **Database:** SQLite (offline support)

---

## 📁 Struktur Direktori

```
qr-attendance-app/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── models/
│   │   ├── middleware/
│   │   ├── utils/
│   │   ├── config/
│   │   └── app.js
│   ├── tests/
│   ├── .env.example
│   ├── package.json
│   └── README.md
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── utils/
│   │   ├── services/
│   │   ├── store/
│   │   └── App.jsx
│   ├── .env.example
│   ├── package.json
│   └── README.md
│
├── mobile/ (optional)
│   ├── src/
│   ├── assets/
│   └── package.json
│
├── docs/
│   ├── API.md
│   ├── DATABASE.md
│   └── DEPLOYMENT.md
│
├── .gitignore
├── README.md
└── LICENSE
```

---

## 🚀 Quick Start

### Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Setup environment
cp .env.example .env
# Edit .env dengan konfigurasi lokal Anda

# Setup database
npm run migrate

# Start development server
npm run dev
# Server berjalan di http://localhost:5000
```

**Environment Variables (.env):**
```env
NODE_ENV=development
PORT=5000
DB_HOST=localhost
DB_PORT=5432
DB_NAME=qr_attendance
DB_USER=postgres
DB_PASSWORD=yourpassword
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d
MAIL_SERVICE=gmail
MAIL_USER=your_email@gmail.com
MAIL_PASS=your_app_password
FRONTEND_URL=http://localhost:3000
```

### Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Setup environment
cp .env.example .env
# Edit .env dengan API URL

# Start development server
npm run dev
# Application berjalan di http://localhost:3000
```

**Environment Variables (.env):**
```env
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=QR Attendance
```

---

## 📊 API Endpoints Preview

### Authentication
- `POST /api/auth/register` - Daftar akun baru
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout
- `POST /api/auth/refresh` - Refresh token

### Kehadiran (Attendance)
- `POST /api/attendance/scan` - Scan QR Code
- `GET /api/attendance/history/:userId` - Riwayat kehadiran
- `GET /api/attendance/class/:classId` - Kehadiran per kelas
- `GET /api/attendance/report` - Export laporan

### Kelas (Classes)
- `GET /api/classes` - Daftar kelas
- `POST /api/classes` - Buat kelas baru
- `GET /api/classes/:classId` - Detail kelas
- `PUT /api/classes/:classId` - Update kelas
- `DELETE /api/classes/:classId` - Hapus kelas

### Siswa (Students)
- `GET /api/students` - Daftar siswa
- `POST /api/students` - Tambah siswa
- `GET /api/students/:studentId` - Detail siswa
- `PUT /api/students/:studentId` - Update siswa
- `DELETE /api/students/:studentId` - Hapus siswa

---

## 🗄️ Database Schema Preview

### Users Table
```
id (PK) | email | password | name | role | created_at
```

### Classes Table
```
id (PK) | name | teacher_id (FK) | school_id (FK) | created_at
```

### Students Table
```
id (PK) | name | email | class_id (FK) | qr_code | created_at
```

### Attendance Table
```
id (PK) | student_id (FK) | class_id (FK) | scan_time | status | created_at
```

---

## 🧪 Testing

```bash
# Backend tests
cd backend
npm run test

# Frontend tests
cd frontend
npm run test

# Coverage report
npm run test:coverage
```

---

## 🔨 Build & Production

### Backend
```bash
cd backend
npm run build
npm start
```

### Frontend
```bash
cd frontend
npm run build
# Output tersimpan di dist/
```

---

## 📦 Deployment

### Docker Setup
```bash
docker-compose up -d
```

### Heroku/Vercel/Railway
Lihat dokumentasi di `docs/DEPLOYMENT.md`

---

## 🤝 Kontribusi

Kami menerima kontribusi! Silakan:

1. Fork repository ini
2. Buat branch feature (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buka Pull Request

---

## 📄 Lisensi

Project ini dilisensikan di bawah MIT License - lihat file `LICENSE` untuk detail.

---

## 📞 Kontak & Support

- 📧 Email: support@qr-attendance.local
- 🐛 Issues: [GitHub Issues](https://github.com/salselsil/qr-attendance-app/issues)
- 💬 Discussions: [GitHub Discussions](https://github.com/salselsil/qr-attendance-app/discussions)

---

**Happy Coding! 🎉**
