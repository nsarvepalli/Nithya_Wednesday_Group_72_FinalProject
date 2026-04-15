# HuskyHomestead - Student Housing Management System

HuskyHomestead is a Java Swing desktop application built for managing off-campus student housing workflows. The project supports multiple user roles (student, university admin, head realtor, broker, landlord, marketplace admin, tech support, and system admin) and combines apartment listings, tour requests, appointment booking, and marketplace features in one system.

## Project Highlights

- Multi-role login and navigation from a central landing page.
- Student registration/login and housing search workflows.
- Realtor and broker management for listings and housing-tour operations.
- Landlord-side listing and booking management.
- Marketplace module for student products and admin moderation.
- Technical support and system administration interfaces.
- MySQL-backed persistence layer via JDBC.

## Tech Stack

- **Language:** Java (source/target set to Java 19)
- **UI:** Java Swing (NetBeans GUI Builder `.form` + `.java` files)
- **Build Tool:** Apache Ant (NetBeans project structure)
- **Database:** MySQL (`studenthousing` schema expected)
- **External Libraries:** MySQL Connector/J, JavaMail, JAF, iText, AbsoluteLayout

## Repository Structure

```text
.
├── src/
│   ├── Model/     # Data models, directories, SQL connector, utilities
│   ├── UI/        # Swing screens for all user roles and workflows
│   └── Project Images/
├── nbproject/     # NetBeans build configuration
├── Libraries for Student Housing/   # Bundled dependency artifacts
├── build.xml      # Ant build file
└── manifest.mf
```

## Prerequisites

Before running the project, ensure:

1. **JDK 19** is installed and configured (`java -version`).
2. **Apache Ant** is installed (`ant -version`) if building from terminal.
3. **MySQL** is running locally.
4. A schema/database named **`studenthousing`** exists.
5. MySQL credentials match the code in `src/Model/SQLconnection.java`:
   - URL: `jdbc:mysql://localhost:3306/studenthousing`
   - Username: `root`
   - Password: *(blank by default in current code)*

## Dependency Setup

This project was developed in NetBeans and references several JAR files through project properties.

### Option A (Recommended): Open in NetBeans

1. Open the project folder in NetBeans.
2. Resolve missing libraries if prompted by pointing NetBeans to JARs in:
   - `Libraries for Student Housing/`
3. Build and run from NetBeans.

### Option B: Build with Ant from terminal

If Ant build fails due to missing classpath references, update `nbproject/project.properties` paths to match where your dependency JARs are stored.

## Running the Application

### NetBeans

- Open project -> Clean and Build -> Run.
- Default configured main class is `UI.BrokerLoginpage`.
- You can also run `UI.StartPage` to access the role-based landing screen.

### Ant (terminal)

```bash
ant clean
ant compile
ant run
```

## Core Modules (High Level)

- **UI module (`src/UI`)**
  - Role-based login pages and dashboards.
  - Screens for apartment listings, brokers, appointments, marketplace, and reporting.

- **Model module (`src/Model`)**
  - Domain objects such as `Student`, `Broker`, `Apartmentlistings`, requests, and history records.
  - Database connection utility (`SQLconnection`) and shared data directories.

## Notes

- The project includes design and documentation artifacts (UML/image/PDF/PPT files) in repository root.
- Some dependency path entries in `nbproject/project.properties` are environment-specific; adjust paths for your machine.
- This is a desktop Java Swing application (not a web app).

## Contributors

Team 72 (Wednesday Group) - Final Project.

---

If you want, I can also add a **Database Setup** section with starter `CREATE TABLE` SQL templates based on the model usage in this codebase.
