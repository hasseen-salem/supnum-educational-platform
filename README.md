# Supnum Educational Platform

> A unified messaging and collaboration platform for educational institutions, built with **React** (Vite) and **Pure PHP**.

## 🚀 Overview

The Supnum Educational Platform is a consolidated Single Page Application (SPA) designed to streamline communication and academic resource management for SUPNUM students and staff.

### Key Modules:

| Module | Description |
| :--- | :--- |
| **Dashboard** | Central hub for schedules, profile, and quick overview |
| **Webmail** | Branching conversation system with thread isolation |
| **Community** | Real-time chat with 3-second polling and chunked media uploads |
| **Archive** | Hierarchical repository for semesters, subjects, and academic materials |
| **Results** | Academic performance tracking via matricule lookup |
| **Admin Command Center** | Manage subjects and upsert student grades |
| **Bulk Importer** | Excel/CSV grade importer with auto-column mapping |

---

## 👥 Contributors

| Name | GitHub | Role |
| :--- | :--- | :--- |
| **Abdellahi** | [@abdellahi-yuki](https://github.com/abdellahi-yuki) | Project lead / Core developer |
| **Saadbouh** | — | Contributor |
| **Hassen Salem** | [@hasseen-salem](https://github.com/hasseen-salem) | Contributor |

---

## 👤 Role Hierarchy

The platform implements a strict role-based access control system:

| Role | Description | Permissions |
| :--- | :--- | :--- |
| **Student** | Primary user | Access Learning, Results, Mail, and Community |
| **Teacher** | Academic Staff | All Student permissions + Upload materials to Archive |
| **Root** | Super Admin | All Staff permissions + User Banning, Mailing Lists, and Reports |

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React 18, Vite, Vanilla CSS |
| **Backend** | Pure PHP 7.4+ |
| **Database** | MySQL / MariaDB |
| **Build** | Vite (ESM) |

### Key Technical Decisions

- **Leaf-node inbox filtering** — the inbox shows only the latest message per conversation branch
- **1MB chunked uploads** — robust handling of large media files in Community
- **Single-entry routing** — all routes managed in `src/App.jsx` with centralized API config in `src/apiConfig.js`
- **Scoped CSS** — each module's styles are container-scoped to prevent conflicts

---

## 📖 Developer Documentation

- **[probably.md](probably.md)** — Project handover, architecture, and core logic
- **[APIs.md](APIs.md)** — Backend API endpoint specifications
- **[CSS_REGISTRY.md](CSS_REGISTRY.md)** — CSS class registry to prevent conflicts
- **[INSTRUCTIONS.md](INSTRUCTIONS.md)** — Development guidelines

---

## 💻 Getting Started

### Prerequisites

- **Node.js** v18+
- **PHP** 7.4+
- **MySQL** / **MariaDB**

### Running Locally

**1. Backend:**
```bash
cd backend
php -S localhost:8000 index.php
```

**2. Frontend:**
```bash
npm install
npm run dev
```

> [!IMPORTANT]
> The backend must be running on port **8000** for the frontend to connect. Update `src/apiConfig.js` if using a different port.

### Project Structure

```
├── src/
│   ├── components/       # Shared components (Header, Footer)
│   ├── pages/            # Module pages (Auth, Dashboard, Mail, Community, Archive, Results)
│   ├── apiConfig.js      # Centralized API base URL
│   ├── App.jsx           # Main router + auth state
│   └── App.css           # Global styles
├── public/               # Static assets
├── package.json
├── vite.config.js
└── APIs.md               # API documentation
```

---

## 📄 License

This project is licensed under the Unlicense — see the [LICENSE](LICENSE) file for details.
