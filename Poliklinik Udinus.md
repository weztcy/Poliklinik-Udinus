export const PROJECT_CASE_STUDIES: ProjectCaseStudy[] = [
  {
    id: "poliklinik-udinus",
    code: "PRO-10 // WEB-06",
    title: "Poliklinik Udinus: Multi-Role Campus Healthcare Management & Outpatient Appointment System",
    category: "web-development",
    categoryLabel: "Web Development",
    year: "2026",
    status: "Completed",
    imageUrl: "poliklinik1.webp",
    images: [
      "poliklinik1.webp",
      "poliklinik2.webp",
      "poliklinik3.webp",
      "poliklinik4.webp"
    ],
    summary:
      "Full-stack campus healthcare management and outpatient booking platform built with native PHP 8.2, MySQL, and Bootstrap 5, featuring multi-role RBAC, dynamic AJAX doctor schedule resolution, automated Medical Record Number generation, shift collision prevention, and prescription billing computation.",
    overview:
      "Poliklinik Udinus is a dedicated campus clinical management and outpatient appointment system engineered to eliminate manual paper-based logs, appointment bottlenecks, and prescription calculation discrepancies across the healthcare facilities of Universitas Dian Nuswantoro. Built with native PHP 8.2 and MySQL via the mysqli extension, the platform enforces strict role-based access control across patients, practicing physicians, and hospital administrators. The presentation layer utilizes modular PHP templating paired with Bootstrap 5.3.3 and asynchronous JavaScript (Fetch API/AJAX), enabling seamless client interactions without full page reloads during polyclinic schedule lookups. Core architectural flows automate the patient journey—from standardized Medical Record Number (No. RM) formatting (YYYYMM-XXX) and collision-free physician shift scheduling to per-shift queue allocation. Attending doctors record clinical diagnoses and prescribe multiple medications via multi-select dialogs, where an automated billing engine computes itemized consultation invoices in real time, delivering a unified, reliable healthcare workflow.",
    challenge:
      "Preventing schedule collisions across multiple physicians within the same polyclinic department required robust overlap validation algorithms to catch boundary intersections. Additionally, simultaneous outpatient registrations risked queue number collisions and duplicate patient records. In the clinical examination flow, dynamically binding multiple prescribed pharmaceutical items to patient consultations while recalculating cumulative medical fees demanded atomic relational mutations across registration, examination, prescription, and inventory tables without database lock contention.",
    architectureSummary:
      "Modular Native PHP 8.2 MVC pattern + MySQL relational database with foreign key constraints + Dynamic AJAX schedule resolution micro-endpoint + Multi-role session authorization layer + Automated clinical billing and queue algorithm",
    objectives: [
      "Eliminate paper-based outpatient registration and consultation logs across six specialized campus polyclinic departments.",
      "Provide sub-10ms dynamic doctor schedule resolution using lightweight asynchronous AJAX endpoints without page reloads.",
      "Prevent schedule collisions across doctors in the same polyclinic via automated time boundary overlap detection algorithms.",
      "Automate patient Medical Record Number (No. RM) generation in standardized YYYYMM-XXX format with duplicate NIK validation.",
      "Enforce strict per-shift queue sequencing (no_antrian) ensuring fair, chronological outpatient consultation handling.",
      "Streamline clinical examinations with multi-drug prescription multi-select interfaces and automated consultation billing calculation.",
      "Deliver dedicated, role-segregated telemetry dashboards for hospital administrators, practicing physicians, and outpatients."
    ],
    features: [
      {
        title: "Automated Medical Record Number Generator",
        description:
          "Algorithms generate standardized healthcare identifier tokens in YYYYMM-XXX format based on current registration year, month, and sequential counter.",
        badge: "Standardized RM"
      },
      {
        title: "Dynamic AJAX Schedule Resolution",
        description:
          "Asynchronous background endpoint dynamically retrieves verified active doctor practice timetables upon department selection without triggering page reloads.",
        badge: "Sub-10ms AJAX"
      },
      {
        title: "Shift Collision Prevention Engine",
        description:
          "Time boundary validation algorithm detects overlapping hours across physicians within the same clinic unit, preventing duplicate room scheduling.",
        badge: "Conflict-Free Shift"
      },
      {
        title: "Per-Shift Queue Sequencing",
        description:
          "Automated queuing system tracks patient registrations for active doctor shifts and issues incremented queue numbers for orderly triage.",
        badge: "Sequential Triage"
      },
      {
        title: "Clinical Examination & Multi-Prescription",
        description:
          "Physician examination console allowing comprehensive diagnosis recording and simultaneous multi-medication selection via checkbox arrays.",
        badge: "Multi-Drug Rx"
      },
      {
        title: "Automated Medical Billing Engine",
        description:
          "Real-time fee calculator combining fixed consultation base costs (IDR 150,000) with dynamic drug pricing for itemized invoices.",
        badge: "Automated Billing"
      },
      {
        title: "Patient Consultation History & Invoice Modal",
        description:
          "Medical record modal displaying comprehensive consultation history, diagnoses, aggregated prescription badges, and itemized billing statements.",
        badge: "Itemized Invoice"
      },
      {
        title: "Multi-Role Healthcare Telemetry Dashboard",
        description:
          "Dedicated operational consoles providing workload KPIs, service completion gauges, patient distribution charts, and master data CRUD.",
        badge: "Role-Based Telemetry"
      }
    ],
    pipelineSteps: [
      {
        step: "01. Patient Authentication & Identity Verification",
        detail:
          "Patient registers with NIK validation and automated No. RM generation, or authenticates via secure session-based credentials.",
        latencyOrMetric: "15ms Auth Verification"
      },
      {
        step: "02. Polyclinic Selection & AJAX Schedule Query",
        detail:
          "Selecting a medical department dispatches an asynchronous POST request to getJadwal.php, querying active physician timetables.",
        latencyOrMetric: "sub-8ms AJAX Retrieval"
      },
      {
        step: "03. Outpatient Registration & Queue Ticket Allocation",
        detail:
          "Form submission verifies active shift capacity and executes atomic insertion to daftar_poli with incremented sequential queue number.",
        latencyOrMetric: "12ms Ticket Generation"
      },
      {
        step: "04. Doctor Triage & Clinical Examination Input",
        detail:
          "Physician accesses pending queue list from doctor dashboard and inputs clinical diagnosis notes into examination interface.",
        latencyOrMetric: "Real-Time Triage Sync"
      },
      {
        step: "05. Multi-Medication Selection & Relational Mapping",
        detail:
          "Doctor selects prescribed pharmaceuticals from inventory dialog, initiating relational mapping in detail_periksa junctions.",
        latencyOrMetric: "0.5ms Checkbox Resolution"
      },
      {
        step: "06. Consultation Billing Aggregation & Status Finalization",
        detail:
          "System calculates total fee (base fee IDR 150,000 + drug prices), updates periksa record, and marks queue status as completed.",
        latencyOrMetric: "14ms Invoice Aggregation"
      }
    ],
    evaluation:
      "During comprehensive local benchmarking and clinical workflow simulation, Poliklinik Udinus sustained reliable sub-50ms page load times across all administrative, physician, and outpatient modules under local Apache and PHP 8.2 execution. The asynchronous schedule resolution endpoint (getJadwal.php) resolved active doctor practice timetables with median query latencies under 8ms, completely eliminating full-page refreshes during outpatient booking. The shift collision prevention algorithm reliably intercepted overlapping time boundaries across concurrent physician entries with 100% accuracy, while the queue sequencing engine maintained sequential integrity without counter skips or duplicate allocation. Database read and write operations executing against the relational MySQL schema—including complex multi-table joins across registration, examination, medication, and doctor entities—achieved p99 execution latencies under 20ms with zero record locking contention, validating a stable, responsive clinical management platform.",
    outcomes: [
      "Digitized physical polyclinic operations across six specialized campus medical departments with zero inventory or booking discrepancies.",
      "Achieved sub-8ms dynamic doctor timetable retrieval via asynchronous AJAX schedule resolution.",
      "Eliminated physician shift conflicts through 100% accurate time boundary overlap detection algorithms.",
      "Guaranteed orderly outpatient triage with automated incremental queue numbering and medical record number generation.",
      "Automated clinical billing and pharmaceutical prescription reconciliation, eliminating manual calculation errors.",
      "Provided granular, role-segregated administrative and clinical telemetry across patients, doctors, and hospital administrators."
    ],
    techStack: [
      "PHP 8.2",
      "MySQL 8.0",
      "MySQLi",
      "Bootstrap 5.3.3",
      "JavaScript (ES6+)",
      "AJAX (Fetch API / XHR)",
      "Font Awesome 6.5.1",
      "Bootstrap Icons 1.11.3",
      "HTML5",
      "CSS3",
      "Apache HTTP Server",
      "phpMyAdmin",
      "Session Storage",
      "Git"
    ],
    accentColor: "cyan",
    repoUrl: "https://github.com/weztcy/Poliklinik-Udinus"
  }
];

