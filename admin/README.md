# Employee Management Dashboard

A modern, responsive frontend dashboard built with Next.js for the Employee Management API. This application provides role-based access for administrators and employees with comprehensive features for managing employee data, attendance, and salary records.

## 🚀 Features

### Admin Features

- **User Management**: Create, view, and manage system users with role assignment
- **Employee Management**: Add, update, and view employee profiles and details
- **Attendance Monitoring**: View attendance records for all employees with detailed analytics
- **Salary Management**: Update salary payment status and view salary records
- **Dashboard Analytics**: Overview of system metrics and recent activities

### Employee Features

- **Personal Dashboard**: Overview of personal metrics and quick actions
- **Profile Management**: View personal and employment information
- **Attendance Tracking**:
  - Quick check-in/check-out functionality
  - Submit leave requests and holiday requests
  - View personal attendance history and statistics
- **Salary Records**: View personal salary history and payment status

### Technical Features

- **Role-based Authentication**: Secure login with automatic role-based redirection
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern UI**: Built with Tailwind CSS and shadcn/ui components
- **Real-time Updates**: Dynamic data fetching and state management
- **Form Validation**: Client-side validation with error handling
- **Type Safety**: Full TypeScript implementation

## 🛠️ Technology Stack

- **Framework**: Next.js 14+ (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui, Radix UI
- **State Management**: React Hooks + Context API
- **Forms**: React Hook Form with Zod validation
- **HTTP Client**: Axios
- **Authentication**: JWT with js-cookie for storage
- **Icons**: Lucide React
- **Notifications**: Sonner

## 📋 Prerequisites

Before running this application, ensure you have:

1. **Node.js** (v18 or higher)
2. **npm** or **yarn** package manager
3. **Employee Management API** running on `http://localhost:8000`

## 🏗️ Installation

1. **Navigate to the project directory:**

   ```bash
   cd employee-dashboard
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Set up environment variables:**
   The `.env.local` file should contain:

   ```env
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```

4. **Start the development server:**

   ```bash
   npm run dev
   ```

5. **Open your browser:**
   Navigate to [http://localhost:3060](http://localhost:3060)

## 🔧 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## 🗂️ Project Structure

```
employee-dashboard/
├── src/
│   ├── app/                    # Next.js App Router pages
│   │   ├── admin/             # Admin dashboard pages
│   │   ├── employee/          # Employee dashboard pages
│   │   ├── login/             # Authentication pages
│   │   └── layout.tsx         # Root layout
│   ├── components/            # Reusable UI components
│   │   ├── ui/               # shadcn/ui components
│   │   ├── layout/           # Layout components
│   │   └── auth/             # Authentication components
│   ├── hooks/                 # Custom React hooks
│   ├── lib/                   # Utility functions and API client
│   └── types/                 # TypeScript type definitions
├── public/                    # Static assets
└── package.json              # Project dependencies
```

## 🔐 Authentication & Authorization

### Login Flow

1. Users login with username/password
2. Application determines user role based on credentials
3. Users are redirected to appropriate dashboard:
   - Admins → `/admin`
   - Employees → `/employee`

### Role-Based Access Control

- **Admin Users**: Full access to all features and data
- **Employee Users**: Access only to personal data and features

### Default Credentials

Based on your API setup, you can use:

- **Admin**: Username containing "admin"
- **Employee**: Any other username created via the API

## 📱 User Interface

### Admin Dashboard

- **Overview Dashboard**: Metrics cards and recent activity
- **Users Management**: Create and manage system users
- **Employees Management**: Add/edit employee profiles
- **Attendance Monitoring**: View all employee attendance with filters
- **Salary Management**: Update payment status and view records

### Employee Dashboard

- **Personal Dashboard**: Personal metrics and quick actions
- **Profile**: View personal information
- **Attendance**: Check-in/out, submit leave requests, view history
- **Salary**: View salary history and payment status

## 🔗 API Integration

The application integrates with the Employee Management API with the following endpoints:

### Authentication

- `POST /auth/login` - User login

### Admin Endpoints

- `GET /admin/users` - Get all users
- `POST /admin/users` - Create user
- `GET /admin/employees` - Get all employees
- `POST /admin/employees` - Create employee
- `PUT /admin/employees/{id}` - Update employee
- `PUT /admin/salary-records/{id}` - Update salary status

### Employee Endpoints

- `GET /employees/me` - Get personal profile
- `GET /employees/me/salary-records` - Get personal salary records

### Attendance Endpoints

- `POST /attendance/check-in` - Check in
- `POST /attendance/check-out` - Check out
- `GET /attendance/my-attendance` - Get personal attendance
- `POST /attendance/` - Submit attendance request

## 🚀 Getting Started

1. **Start the Employee Management API** (ensure it's running on `http://localhost:8000`)

2. **Run this frontend application:**

   ```bash
   npm run dev
   ```

3. **Access the application:**

   - Navigate to [http://localhost:3060](http://localhost:3060)
   - You'll be redirected to the login page

4. **Login with credentials:**
   - Use credentials created via the API's admin interface
   - Admin users: usernames containing "admin"
   - Employee users: other usernames

## 📞 Support

For issues and questions:

1. Ensure the Employee Management API is running and accessible
2. Check browser console for error messages
3. Verify all dependencies are installed correctly
4. Check the `.env.local` file for correct API URL

---

Built with ❤️ using Next.js, TypeScript, and Tailwind CSS

## Local ports

Each XynoLab project has its own ports, so several projects can run at the same time.

| What | Port |
| --- | --- |
| Admin | 3060 |
| API | 8000 |

**After pulling the port change (2026-11-09):**

1. Add `PORT=3060` to `admin/.env` (see `.env.example`); `pnpm dev` reads it from there. Without it, Next.js falls back to 3000, which other projects use. Open http://localhost:3060. Database steps are in `../api/README.md`.
