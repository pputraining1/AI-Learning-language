
# Introduction

AI Learning Language di sini adalah Integrasi **Generative AI** (Gen AI) ke dalam proses pengembangan bukanlah tentang membuat aplikasi dengan fitur AI, melainkan tentang menggunakan AI itu sendiri sebagai alat bagi para developer. Tujuannya adalah untuk mengotomatisasi, mempercepat, dan meningkatkan kualitas setiap tahapan dalam siklus hidup pengembangan perangkat lunak, memungkinkan developer untuk fokus pada inovasi dan pemecahan masalah yang lebih kompleks.

Ini bukan tentang mengganti developer, melainkan memberdayakan mereka dengan "asisten" super cerdas.

---
# Guide
>Pemahaman Project (Wajib untuk Semua)
### 1. Pendahuluan → Pahami konteks project

Header dokumen: #Pendahuluan

- Tujuan Aplikasi: Hotel Booking management system
- Target Pengguna: Admin hotel atau Resepsionis
- Fitur Utama: Booking, dashboard monitoring, check-in/out, room service
- Arsitektur: Spring Boot (Backend) + React (Frontend) + MySQL**

### 2. Teknologi dan Library → Stack teknologi yang digunakan

Header dokumen: #Teknologi_dan_library 

- Frontend Stack: React 19.1.1, TypeScript, Vite, Redux Toolkit, Tailwind CSS
- Backend Stack: Spring Boot 3.2.0, Spring Security, JPA, MySQL
- Authentication: JWT Tokens, OAuth2, BCrypt
- Sub-bab: Frontend, Backend, Authentication & Security
### 3. Struktur Project → Organisasi folder dan file

Header dokumen: #Struktur_Project

- Frontend Structure: Features-based organization, components, hooks, store
- Backend Structure: Clean architecture dengan controller, service, repository
- Sub-bab: Frontend, Backend
### 4. Struktur Database → ERD dan relasi tabel

Header dokumen: #Struktur_Database

- Visual ERD: Diagram hubungan antar tabel
- Room entity: Fields dan constraints yang diperlukan

---
## Workflow Development 

### 1. Penggunaan AI dalam Project → Role AI dalam development

Header dokumen: #Penggunaan_AI_dalam_Project

- Code Architect: Rancang struktur aplikasi
- Full-Stack Developer: Implementasi fitur
- Code Reviewer: Review kode dan bug detection
- Documentation Writer: Buat dokumentasi
### 2. Drafting Task → User story breakdown

Header dokumen: #Drafting_Task

- Task Categories: Database & Models, Business Logic, State & API, Pages & Components
- User Story: "User dapat menambahkan data kamar baru"
### 3. Instalasi Gemini CLI → Setup AI tools

Header dokumen: #Instalasi_Gemini_CLI

- Prerequisites: Node.js installation
- Setup Steps: Install, login, API key configuration
- Commands: npm install -g @google/gemini-cli

### 4. Instalasi Qwen Code → Setup AI coding assistant

Header dokumen: #Instalasi_Qwen_Code

- Installation: npm install -g @qwen-code/qwen-code@latest
- Authentication: OAuth login process
- Verification: Version check command

---
## Metodologi Development 

### 1. Metode Prompting → AI prompt engineering techniques

Header dokumen: #Metode_Kerja → #Metode_Prompting

- Persiapan Input: Struktur bahan (user story, schema, ERD)
- High-level Prompting: Arsitektur dan API design
- Incremental Prompting: Modular development approach
- Design-to-Code: Figma mockup ke React components
- Validation & Refinement: Check acceptance criteria
- Iterasi & Integrasi: Gabung komponen dan refactor
### 2. Kerangka Prompting 4C → Structured prompting framework

Header dokumen: #Metode_Kerja → #Kerangka_Prompting_4C

- Context: Background, framework, domain problem
- Constraint: Aturan, validasi, style coding
- Command: Instruksi utama yang spesifik
- Check: Evaluasi dan format output yang diinginkan

### 3. Code Review → Quality assurance process

Header dokumen: #Metode_Kerja → #Code_Review

- User Story Check: Kesesuaian dengan acceptance criteria
- Code Quality: Naming convention, structure, clean code
- Manual Testing: Backend (Postman), Frontend (browser)
- Database Validation: Schema dan constraint verification
- Static Analysis: SonarCube, ESLint, Prettier integration
- AI Iteration: Feedback loop untuk perbaikan

---
## Implementasi Backend 

### 1. Create Project → Backend project initialization

Header dokumen: #Implementasi → #Backend → #Create_Project

- Project Structure: Complete Spring Boot folder organization
- Maven Setup: Dependencies dan configuration
- AI Command: Automated project scaffolding
### 2. Database & Models → Entity dan data layer

Header dokumen: #Implementasi → #DatabaseAndModels

- MySQL Configuration: Database connection setup
- Room Entity: JPA annotations, constraints, enums
- DTO Classes: Request/Response data transfer objects
- Repository: JpaRepository extension
- Schema: Table creation dengan Hibernate

### 3. Business Logic → Service layer implementation

Header dokumen: #Implementasi → #Business_Logic

- RoomService: createRoom() method dengan validasi
- Controller Layer: REST API endpoint POST /api/rooms
- Exception Handling: Custom exceptions dan global handler
- Validation: Uniqueness check dan input validation

### 4. Dokumentasi API → API documentation

Header dokumen: #Implementasi → #Dokumentasi_API

- Endpoint Description: Method, path, functionality
- Request/Response Format: JSON examples
- Error Handling: Status codes dan error messages
- Testing Samples: cURL commands dan Postman examples

---
## Implementasi Frontend

### 1. Pages & Components → UI development

Header dokumen: #Implementasi → #Frontend → #Pages_Components

- Component Structure: AddRoomPage, RoomForm dengan validation
- UI Slicing: Figma design ke React components
- Form Validation: React Hook Form + Zod integration
- Responsive Design: Desktop dan mobile compatibility
- Navigation: Routing dan page transitions
- Notification System: Success/error feedback

### 2. State & API → State management dan API integration

Header dokumen: #Implementasi → #StateAndAPI

- Redux Setup: roomSlice dengan createAsyncThunk
- Service Layer: API calls dengan axios
- TypeScript Types: Request/Response DTO interfaces
- Error Handling: API error management
- State Management: Loading, success, error states
