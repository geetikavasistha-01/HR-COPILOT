# HR Copilot

A comprehensive Human Resources management system built with Next.js, TypeScript, and Supabase. This application provides role-based dashboards, CSV data management with Excel-like functionality, and complete HR workflow automation.

## 🚀 Features

### Authentication & User Management
- **Google OAuth Integration** - Seamless signup and login
- **Role-Based Access Control** - Three distinct user roles (Employee, Manager, Administrator)
- **User Profile Management** - Complete profile system with business unit assignments
- **Invitation System** - Secure team invitations with token-based acceptance

### Role-Based Dashboards
- **Employee Dashboard** - Personal profile, time-off requests, company announcements, attendance tracking
- **Manager Dashboard** - Team management, approval workflows, team analytics, recruitment pipeline
- **Admin Dashboard** - Company-wide analytics, user management, system settings, global reports

### Excel-like Data Workspace
- **CSV Upload & Processing** - Drag-and-drop CSV upload with validation and preview
- **Spreadsheet Interface** - Excel-like grid with cell editing, sorting, filtering, and navigation
- **CRUD Operations** - Complete data manipulation with real-time validation
- **Auto-save & Resume** - Automatic work saving with session tracking and resumable workflows
- **Work Monitoring** - Track user activity, edit history, and time spent on tasks

### HR Analytics & KPIs
- Headcount metrics and trends
- Turnover rates and retention analytics
- Recruitment funnel metrics
- Employee engagement tracking
- Performance review statistics
- Training completion rates
- Diversity and inclusion metrics

## 🛠️ Technology Stack

- **Frontend**: Next.js 13+, TypeScript, Tailwind CSS
- **Backend**: Supabase (PostgreSQL, Authentication, Storage)
- **Database**: PostgreSQL with Row Level Security (RLS)
- **Authentication**: Supabase Auth with Google OAuth
- **Styling**: Tailwind CSS with dark theme
- **Charts**: Chart.js/Recharts for data visualization
- **Spreadsheet**: React-based Excel-like grid component

## 📋 Prerequisites

- Node.js 18+ and npm/yarn
- Supabase account and project
- Google OAuth credentials (for authentication)

## 🚀 Quick Start

### 1. Clone the Repository
git clone <repository-url>
cd hr-copilot
npm install


### 2. Environment Setup
Create a `.env.local` file in the root directory:
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key


### 3. Database Schema Setup
Run the provided SQL schema in your Supabase SQL editor:
The complete schema is available in /database/schema.sql
This includes all tables, RLS policies, functions, and seed data


### 4. Google OAuth Configuration
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create OAuth 2.0 credentials
3. Add your redirect URIs to Supabase Auth settings
4. Configure the OAuth provider in Supabase Dashboard

### 5. Run the Application
Visit `http://localhost:3000` to access the application.

## 📊 Database Schema

### Core Tables
- **`user_profiles`** - Employee information and role assignments
- **`business_units`** - Organizational departments and teams
- **`business_unit_heads`** - Leadership assignments (eliminates circular references)
- **`invitations`** - Team invitation system with token-based acceptance
- **`role_permissions`** - Granular permission management

### Workspace Tables
- **`workspaces`** - CSV upload and workspace management
- **`work_sessions`** - User activity and session tracking
- **`workspace_changes`** - Complete audit trail of data modifications

### Key Features
- **No Circular References** - Clean schema design prevents authentication issues
- **Row Level Security** - Comprehensive RLS policies for data protection
- **Automatic Triggers** - User profile creation and role assignment automation
- **Performance Optimized** - Proper indexing and query optimization

## 🔐 Authentication Flow

1. **User Registration** - Google OAuth or email/password signup
2. **Role Selection** - New users choose their role (Employee/Manager/Admin)
3. **Profile Creation** - Automatic profile generation with default permissions
4. **Dashboard Redirect** - Role-based routing to appropriate dashboard

## 📱 User Roles & Permissions

### Employee (`view_only`)
- View personal information and company directory
- Submit time-off requests and view balances
- Access training materials and announcements
- Upload and edit personal CSV data

### Manager (`bu_head`)
- All employee features plus:
- Team management and oversight
- Approve/deny team requests
- Access team analytics and reports
- Manage team CSV workspaces

### Administrator (`admin`)
- All manager features plus:
- Company-wide user management
- System configuration and settings
- Global analytics and reporting
- Access to all workspaces and data

## 🧮 CSV Workspace Features

### Upload & Processing
- Drag-and-drop CSV file upload
- Automatic data type detection
- Column mapping interface
- File validation and error handling

### Excel-like Interface
- Grid-based spreadsheet view
- Cell editing with keyboard navigation
- Column sorting and filtering
- Copy/paste functionality
- Undo/redo operations

### Data Management
- Real-time CRUD operations
- Auto-save every 30 seconds
- Version history and change tracking
- Resumable work sessions
- Export to multiple formats

### Monitoring & Analytics
- User activity tracking
- Time spent on tasks
- Edit history and audit trail
- Performance metrics
- Collaboration indicators

## 🎨 UI/UX Features

- **Dark Theme** - Professional dark interface throughout
- **Responsive Design** - Optimized for desktop, tablet, and mobile
- **Intuitive Navigation** - Sidebar navigation with role-based menus
- **Real-time Updates** - Live data synchronization across all components
- **Loading States** - Comprehensive loading indicators and error handling

## 🔧 Development

### Project Structure
hr-copilot/
├── components/
│ ├── dashboard/ # Dashboard components
│ ├── auth/ # Authentication components
│ ├── workspace/ # CSV workspace components
│ └── ui/ # Shared UI components
├── pages/
│ ├── admin/ # Admin dashboard pages
│ ├── manager/ # Manager dashboard pages
│ ├── employee/ # Employee dashboard pages
│ └── auth/ # Authentication pages
├── lib/
│ ├── supabase.ts # Supabase client configuration
│ ├── auth.ts # Authentication helpers
│ └── utils.ts # Utility functions
├── database/
│ └── schema.sql # Complete database schema
└── types/
└── index.ts # TypeScript type definitions


### Key Components
- **`DashboardLayout`** - Main layout with navigation and header
- **`RoleSelection`** - User role selection interface
- **`SpreadsheetGrid`** - Excel-like data grid component
- **`CSVUploader`** - File upload and processing component
- **`StatsCard`** - Analytics and KPI display component

### Custom Hooks
- **`useAuth`** - Authentication state management
- **`useWorkspace`** - CSV workspace data management
- **`useUserProfile`** - User profile and permissions
- **`useRealTime`** - Supabase real-time subscriptions

## 🚀 Deployment

### Vercel Deployment (Recommended)
1. Connect your GitHub repository to Vercel
2. Configure environment variables in Vercel dashboard
3. Deploy automatically on git push

### Manual Deployment

### Key Components
- **`DashboardLayout`** - Main layout with navigation and header
- **`RoleSelection`** - User role selection interface
- **`SpreadsheetGrid`** - Excel-like data grid component
- **`CSVUploader`** - File upload and processing component
- **`StatsCard`** - Analytics and KPI display component

### Custom Hooks
- **`useAuth`** - Authentication state management
- **`useWorkspace`** - CSV workspace data management
- **`useUserProfile`** - User profile and permissions
- **`useRealTime`** - Supabase real-time subscriptions

## 🚀 Deployment

### Vercel Deployment (Recommended)
1. Connect your GitHub repository to Vercel
2. Configure environment variables in Vercel dashboard
3. Deploy automatically on git push

### Manual Deployment
npm run build
npm run start


### Environment Variables for Production
Ensure all environment variables are properly configured in your production environment.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the documentation in the `/docs` folder
- Review the database schema in `/database/schema.sql`

## 🎯 Roadmap

- [ ] Advanced reporting and analytics
- [ ] Mobile app development
- [ ] Integration with external HR systems
- [ ] AI-powered insights and recommendations
- [ ] Advanced collaboration features
- [ ] Multi-language support

---

**HR Copilot** - Streamlining HR management with modern technology and intuitive design.
