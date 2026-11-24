# Portfolio Project Data — Poliklinik Udinus

- **Category:** `web-development` (`Web Development`)
- **Accent Color:** `cyan`
- **Target Assets Folder:** `public/images/projects/poliklinik_udinus/`
- **Required Local Images:** `banner.webp`, `image01.webp` .. `image04.webp`

## TypeScript Data (`ProjectCaseStudy`)

```typescript
{
  "id": "poliklinik-udinus",
  "code": "PRO-43 // WEB-07",
  "title": "Poliklinik Udinus",
  "category": "web-development",
  "categoryLabel": "Website",
  "year": "2025",
  "status": "Completed",
  "accentColor": "cyan",
  "repoUrl": "https://github.com/weztcy/Poliklinik-Udinus",
  "license": "MIT License",
  "banner": "/images/projects/poliklinik_udinus/banner.webp",
  "summary": "A full-stack PHP and MySQL clinic management system uniting patient queueing, doctor scheduling, clinical exams, and billing across three portals.",
  "projectDescription": "Poliklinik Udinus digitizes outpatient clinic workflows with role-based portals for Administrators, Doctors, and Patients. Built with PHP, MySQL, Bootstrap, jQuery AJAX, and Chart.js, it automates medical record numbering, active schedule lookups, queue ticketing, and prescription billing.",
  "architectureSummary": "Server-rendered PHP portals and form handlers connected via MySQLi to an 8-table relational MySQL database with jQuery AJAX schedule lookups.",
  "techStack": [
    "PHP",
    "MySQL",
    "MySQLi",
    "Bootstrap",
    "JavaScript",
    "jQuery",
    "Chart.js",
    "SweetAlert2",
    "Font Awesome",
    "Bootstrap Icons",
    "HTML5",
    "CSS3"
  ],
  "telemetryMatrix": {
    "projectType": "Full-Stack Clinic Management System",
    "targetPlatform": "Web Browser (Apache / PHP / MySQL)",
    "primaryDomain": "Healthcare & Outpatient Polyclinic",
    "architecturePipeline": "Server-Rendered PHP + AJAX + MySQLi",
    "testingAndAudit": "Passed",
    "projectStatus": "Completed",
    "projectYear": "2025"
  },
  "projectInfo": {
    "projectType": "Full-Stack Healthcare Information System",
    "developmentStatus": "Completed",
    "developmentYear": "2025",
    "platform": "Web (PHP & MySQL)",
    "projectCategory": "Web Development"
  },
  "projectBackground": "Campus polyclinic operations frequently struggle with manual patient registration, fragmented doctor practice schedules, uncoordinated queue numbering, and error-prone prescription billing. Poliklinik Udinus was built to centralize outpatient records, appointment booking, and clinical documentation into one unified web platform.",
  "problemStatements": [
    {
      "title": "Manual Patient Registration & Record Tracking",
      "description": "Paper-based intake creates duplicate patient entries and slows retrieval of unique medical record numbers during repeat visits.",
      "issueCode": "ISSUE_01"
    },
    {
      "title": "Overlapping Doctor Practice Schedules",
      "description": "Without automated slot validation within each polyclinic, doctors risk booking conflicting hours or leaving inactive schedules visible to patients.",
      "issueCode": "ISSUE_02"
    },
    {
      "title": "Disconnected Queue & Prescription Billing",
      "description": "Manual calculation of consultation fees combined with variable multi-drug prescriptions introduces billing inconsistencies and delays medical history updates.",
      "issueCode": "ISSUE_03"
    }
  ],
  "projectObjectives": [
    {
      "title": "Automate Medical Record Numbering",
      "description": "Enforce duplicate National ID checks on registration and generate sequential YYYYMM-XXX medical record numbers in MySQL.",
      "targetTag": "TARGET_01"
    },
    {
      "title": "Prevent Schedule Conflicts & Filter Active Slots",
      "description": "Validate overlapping time windows per polyclinic on creation and expose only active schedules via AJAX during patient booking.",
      "targetTag": "TARGET_02"
    },
    {
      "title": "Streamline Clinical Exams & Fee Calculation",
      "description": "Enable doctors to record clinical notes and multi-drug prescriptions while automatically totaling the base consultation fee and medication prices.",
      "targetTag": "TARGET_03"
    }
  ],
  "coreFeatures": [
    {
      "title": "Multi-Role Portals & Session Access",
      "description": "Dedicated dashboards and dynamic sidebars for Administrators, Doctors, and Patients backed by PHP session state.",
      "badge": "Access Control"
    },
    {
      "title": "Patient Self-Registration & Queue Booking",
      "description": "Validates KTP uniqueness, generates YYYYMM-XXX medical record numbers, loads active schedules via jQuery AJAX, and assigns per-schedule queue numbers.",
      "badge": "Patient Flow"
    },
    {
      "title": "Doctor Schedule & Overlap Validation",
      "description": "Lets doctors manage weekly practice schedules with polyclinic-level time overlap checks and single-active-schedule toggles.",
      "badge": "Scheduling"
    },
    {
      "title": "Clinical Examination & Automated Billing",
      "description": "Captures examination dates, doctor notes, and multi-drug prescriptions, computing total fees from the Rp 150,000 consultation base plus selected medications.",
      "badge": "Clinical"
    },
    {
      "title": "Master Data CRUD & Analytics Charts",
      "description": "Provides Admin CRUD for doctors, polyclinics, medications, and patients alongside Chart.js bar charts on Admin and Doctor dashboards.",
      "badge": "Analytics"
    }
  ],
  "interfaceShowcase": [
    {
      "imageUrl": "/images/projects/poliklinik_udinus/image01.webp"
    },
    {
      "imageUrl": "/images/projects/poliklinik_udinus/image02.webp"
    },
    {
      "imageUrl": "/images/projects/poliklinik_udinus/image03.webp"
    },
    {
      "imageUrl": "/images/projects/poliklinik_udinus/image04.webp"
    }
  ],
  "userFlow": {
    "summary": "Patients register to receive a medical record number, pick an active polyclinic schedule via AJAX to obtain a queue ticket, undergo examination by the assigned doctor with itemized medication billing, and review their complete consultation details online.",
    "steps": [
      {
        "step": "01",
        "title": "Account Registration & Authentication",
        "description": "Patients register with KTP validation to receive a YYYYMM-XXX medical record number, while Admins and Doctors sign in through the staff login portal.",
        "actorOrNode": "Patient / Staff Auth"
      },
      {
        "step": "02",
        "title": "Polyclinic Selection & Dynamic Schedule Lookup",
        "description": "On the Daftar Poli page, selecting a polyclinic triggers a jQuery AJAX POST to getJadwal.php to populate active doctor schedules.",
        "actorOrNode": "daftarPoliklinik.php / getJadwal.php"
      },
      {
        "step": "03",
        "title": "Queue Ticket Assignment",
        "description": "Submitting the complaint inserts a daftar_poli record with an incremented per-schedule queue number (no_antrian) and pending status.",
        "actorOrNode": "pages/daftarPoli/daftarPoli.php"
      },
      {
        "step": "04",
        "title": "Clinical Examination & Prescription Billing",
        "description": "The Doctor records examination timestamps, clinical notes, and prescribed drugs, updating examination status and calculating total fees.",
        "actorOrNode": "pages/periksaPasien/periksaPasien.php"
      },
      {
        "step": "05",
        "title": "Medical History & Detail Review",
        "description": "Patients and Doctors inspect diagnosis notes, prescribed medications, queue numbers, and itemized examination costs.",
        "actorOrNode": "detailDaftarPoli.php / riwayatPasien.php"
      }
    ]
  },
  "systemArchitecture": {
    "summary": "The application implements a server-rendered PHP architecture organized into role-specific entry points, reusable navigation components, and modular CRUD directories. Client pages interact with jQuery AJAX schedule lookups and persist all clinic transactions via MySQLi into an 8-table InnoDB MySQL schema.",
    "layers": [
      {
        "name": "Presentation & UI Layer",
        "role": "Renders responsive landing, authentication, dashboard, and CRUD views with Bootstrap, Font Awesome, SweetAlert2, and Chart.js.",
        "components": ["index.php", "components/navbar.php", "components/sidebar.php", "pages/*/index.php"]
      },
      {
        "name": "Client Interaction & AJAX Layer",
        "role": "Provides dynamic polyclinic-to-schedule filtering and interactive dashboard data visualizations in the browser.",
        "components": ["jQuery AJAX (daftarPoliklinik.php)", "getJadwal.php", "Chart.js (index2.php, index3.php)"]
      },
      {
        "name": "Application & Business Logic Layer",
        "role": "Handles session authentication, role routing, medical record generation, schedule overlap checks, queue increments, and billing.",
        "components": ["pages/login/checkLogin.php", "pages/register/checkRegister.php", "pages/jadwalPeriksa/*.php", "pages/periksaPasien/*.php"]
      },
      {
        "name": "Database Persistence Layer",
        "role": "Maintains relational integrity across polyclinics, doctors, schedules, patients, queues, exams, and medications via MySQLi.",
        "components": ["config/koneksi.php", "data/poli_bk.sql (MySQL InnoDB)"]
      }
    ]
  },
  "databaseDataFlow": {
    "type": "Database Schema / ERD",
    "summary": "Eight InnoDB tables in poli_bk enforce foreign-key links from polyclinics and doctors down to active practice schedules, patient queue registrations, examination headers, and multi-item medication details.",
    "entitiesOrPipelines": [
      {
        "name": "poli",
        "type": "Table",
        "fields": ["id", "nama_poli", "keterangan"]
      },
      {
        "name": "dokter",
        "type": "Table",
        "fields": ["id", "nama", "password", "alamat", "no_hp", "id_poli"]
      },
      {
        "name": "jadwal_periksa",
        "type": "Table",
        "fields": ["id", "id_dokter", "hari", "jam_mulai", "jam_selesai", "aktif"]
      },
      {
        "name": "pasien",
        "type": "Table",
        "fields": ["id", "nama", "password", "alamat", "no_ktp", "no_hp", "no_rm"]
      },
      {
        "name": "daftar_poli",
        "type": "Table",
        "fields": ["id", "id_pasien", "id_jadwal", "keluhan", "no_antrian", "status_periksa"]
      },
      {
        "name": "periksa",
        "type": "Table",
        "fields": ["id", "id_daftar_poli", "tgl_periksa", "catatan", "biaya_periksa"]
      },
      {
        "name": "detail_periksa",
        "type": "Table",
        "fields": ["id", "id_periksa", "id_obat"]
      },
      {
        "name": "obat",
        "type": "Table",
        "fields": ["id", "nama_obat", "kemasan", "harga"]
      }
    ]
  },
  "technicalImplementation": [
    {
      "category": "Authentication",
      "title": "Role-Based Session Routing & Guards",
      "description": "Separates staff (Admin and Doctor) and Patient authentication endpoints, storing user ID, username, polyclinic ID, and access role in PHP $_SESSION to enforce dashboard access and conditional sidebar rendering.",
      "badge": "RBAC"
    },
    {
      "category": "Scheduling",
      "title": "Polyclinic Time-Overlap Validation & Single Active Slot",
      "description": "Queries existing jadwal_periksa intervals within the same polyclinic before inserting new slots to block overlapping hours, and resets previous active flags when a doctor activates a schedule.",
      "badge": "Validation"
    },
    {
      "category": "Queueing",
      "title": "Dynamic Schedule Filtering & Per-Slot Queue Increment",
      "description": "Uses jQuery AJAX against getJadwal.php to return only active schedules for a chosen polyclinic and computes sequential no_antrian values per id_jadwal.",
      "badge": "AJAX Flow"
    },
    {
      "category": "Billing",
      "title": "Transactional Prescription & Fee Aggregation",
      "description": "Iterates selected medication IDs during examination creation and editing, persisting detail_periksa junction rows while summing the Rp 150,000 consultation fee and individual drug prices.",
      "badge": "Billing"
    }
  ],
  "primaryTechSpecs": {
    "programmingLanguage": "PHP",
    "framework": "Bootstrap",
    "database": "MySQL"
  },
  "architectureQuality": {
    "badges": [
      "Role Based Access",
      "Relational MySQL Schema",
      "Dynamic Queue System",
      "Modular PHP Views"
    ]
  }
}
```
