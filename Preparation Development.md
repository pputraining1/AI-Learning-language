# Deskripsi Proyek: Sistem Booking Assessment

Proyek ini akan membangun sebuah sistem Booking Assessment yang dirancang untuk membantu staf resepsionis hotel dalam mengelola proses pemesanan, check-in, pelayanan kamar, hingga check-out. Proyek ini mensimulasikan alur kerja operasional hotel, memberikan pengalaman praktis dalam membangun aplikasi bisnis yang terintegrasi.

Modul utama yang akan dikerjakan meliputi:

- **Booking Kamar**: Sistem untuk membuat, mengubah, atau membatalkan pemesanan kamar hotel.    
- **Check-in**: Proses pencatatan kedatangan tamu dan penyerahan kamar yang sudah dipesan.
- **Pelayanan Kamar (Room Service)**: Modul untuk mencatat permintaan layanan tambahan dari tamu, seperti permintaan makanan, minuman, atau laundry.
- **Check-out**: Proses penyelesaian pembayaran dan pencatatan kepulangan tamu.

Tentu, ini adalah draf dokumen Persiapan Pelaksanaan Proyek (Project Doing Preparation) untuk bootcamp Anda. Anda bisa langsung menggunakannya atau menyesuaikannya sesuai kebutuhan.

### Deskripsi Proyek: Sistem Booking Assessment

Proyek ini akan membangun sebuah sistem Booking Assessment yang dirancang untuk membantu staf resepsionis hotel dalam mengelola proses pemesanan, check-in, pelayanan kamar, hingga check-out. Proyek ini mensimulasikan alur kerja operasional hotel, memberikan pengalaman praktis dalam membangun aplikasi bisnis yang terintegrasi.

Modul utama yang akan dikerjakan meliputi:

- Booking Kamar: Sistem untuk membuat, mengubah, atau membatalkan pemesanan kamar hotel.
- Check-in: Proses pencatatan kedatangan tamu dan penyerahan kamar yang sudah dipesan.
- Pelayanan Kamar (Room Service): Modul untuk mencatat permintaan layanan tambahan dari tamu, seperti permintaan makanan, minuman, atau laundry.
- Check-out: Proses penyelesaian pembayaran dan pencatatan kepulangan tamu.

---

# Teknologi yang Digunakan

Proyek ini akan menggunakan kombinasi teknologi modern untuk pengembangan full-stack dan integrasi kecerdasan buatan (AI) untuk meningkatkan fungsionalitas.

### 1. Bahasa Pemrograman & Framework

- **Frontend**: React
- Menggunakan JavaScript untuk membangun antarmuka pengguna yang dinamis dan interaktif.
- **Backend**: Spring Boot
- Menggunakan Java untuk membangun server dan API yang kuat dan scalable.
### 2. AI Agent

- Gemini CLI: Digunakan untuk berinteraksi dengan model AI Gemini langsung dari command-line.
- Qwen CLI: Digunakan untuk berinteraksi dengan model AI Qwen langsung dari command-line.
- Google AI Studio: Digunakan untuk eksplorasi, prototyping, dan deployment model AI yang disesuaikan dengan kebutuhan proyek.

Tentu, ini adalah draf dokumen Persiapan Pelaksanaan Proyek (Project Doing Preparation) untuk bootcamp Anda. Anda bisa langsung menggunakannya atau menyesuaikannya sesuai kebutuhan.

### Deskripsi Proyek: Sistem Booking Assessment

Proyek ini akan membangun sebuah sistem Booking Assessment yang dirancang untuk membantu staf resepsionis hotel dalam mengelola proses pemesanan, check-in, pelayanan kamar, hingga check-out. Proyek ini mensimulasikan alur kerja operasional hotel, memberikan pengalaman praktis dalam membangun aplikasi bisnis yang terintegrasi.

Modul utama yang akan dikerjakan meliputi:

- **Booking Kamar**: Sistem untuk membuat, mengubah, atau membatalkan pemesanan kamar hotel.
- **Check-in**: Proses pencatatan kedatangan tamu dan penyerahan kamar yang sudah dipesan.
- **Pelayanan Kamar (Room Service)**: Modul untuk mencatat permintaan layanan tambahan dari tamu, seperti permintaan makanan, minuman, atau laundry.
- **Check-out**: Proses penyelesaian pembayaran dan pencatatan kepulangan tamu.

---
### Teknologi yang Digunakan

Proyek ini akan menggunakan kombinasi teknologi modern untuk pengembangan full-stack dan integrasi kecerdasan buatan (AI) untuk meningkatkan fungsionalitas.

#### 1. Bahasa Pemrograman & Framework

- Frontend: React    

| Teknologi        | Versi  | Fungsi                         |
| ---------------- | ------ | ------------------------------ |
| React            | 19.1.1 | JavaScript library untuk UI    |
| TypeScript       | 5.8.3  | Static typing untuk JavaScript |
| Vite             | 7.1.2  | Build tool dan dev server      |
| Redux Toolkit    | 2.8.2  | State management               |
| React Router     | 7.8.2  | Client-side routing            |
| Tailwind CSS     | 4.1.12 | Utility-first CSS framework    |
| Axios            | 1.11.0 | HTTP client untuk API calls    |
| Chart.js         | 4.5.0  | Data visualization library     |
| React Chart.js 2 | 5.3.0  | React wrapper untuk Chart.js   |

- Backend: Spring Boot

| Teknologi              | Versi  | Fungsi                         |
| ---------------------- | ------ | ------------------------------ |
| Spring Boot            | 3.2.0  | Java framework untuk REST API  |
| Spring Security        | -      | Authentication & authorization |
| Spring Data JPA        | -      | Database access layer          |
| OAuth2 Resource Server | -      | JWT token validation           |
| MySQL Connector        | 8.0.33 | Database driver                |
| JJWT                   | 0.11.5 | JWT token handling             |
| Spring Boot DevTools   | -      | Development utilities          |
| Hibernate              | -      | ORM framework                  |

##### Authentication & Security
- JWT Tokens – Stateless authentication
- CORS Configuration – Cross-origin resource sharing
- Password Encoding – BCrypt hashing


#### 2. AI Agent

- Gemini CLI: Digunakan untuk berinteraksi dengan model AI Gemini langsung dari command-line.
- Qwen CLI: Digunakan untuk berinteraksi dengan model AI Qwen langsung dari command-line.
- Google AI Studio: Digunakan untuk eksplorasi, prototyping, dan deployment model AI yang disesuaikan dengan kebutuhan proyek.

---
# ERD (Entity-Relationship Diagram) Proyek Booking

Berikut adalah draf ERD yang menggambarkan relasi antar entitas utama dalam sistem Booking Assessment. Diagram ini bisa menjadi acuan dasar untuk perancangan database.

![[ERD Booking.png]]
### **Relasi hotel_booking_users dan hotel_booking_bookings**

- **Jenis Relasi**: One-to-Many
- **Penjelasan**:
	- Satu pengguna (hotel_booking_users) dapat membuat banyak pemesanan (hotel_booking_bookings).
	- Sebaliknya, setiap pemesanan hanya dibuat oleh satu pengguna.
	- Implementasi: Relasi ini diwakili oleh foreign key user_id yang ada pada tabel hotel_booking_bookings, yang merujuk pada id di tabel hotel_booking_users.

### **Relasi hotel_booking_rooms dan hotel_booking_bookings**

- **Jenis Relasi**: One-to-Many
- **Penjelasan**:
	- Satu kamar (hotel_booking_rooms) dapat digunakan untuk banyak pemesanan (hotel_booking_bookings) yang berbeda (tentunya pada tanggal yang berbeda).
	- Setiap pemesanan hanya terkait dengan satu kamar.
	- Implementasi: Relasi ini diwakili oleh foreign key room_id yang ada pada tabel hotel_booking_bookings, yang merujuk pada id di tabel hotel_booking_rooms.

### **Relasi hotel_booking_rooms dan hotel_booking_room_amenities**

- **Jenis Relasi**: Many-to-Many (melalui tabel perantara)
- **Penjelasan**:
	- Satu kamar (hotel_booking_rooms) dapat memiliki banyak fasilitas (hotel_booking_amenities).
	- Satu fasilitas juga dapat dimiliki oleh banyak kamar.
	- Implementasi: Relasi ini dijembatani oleh tabel perantara hotel_booking_room_amenities. Tabel ini memiliki dua foreign key: room_id (merujuk ke hotel_booking_rooms) dan amenity_id (merujuk ke hotel_booking_amenities).

### Relasi hotel_booking_amenities dan hotel_booking_room_amenities

- **Jenis Relasi**: One-to-Many
- **Penjelasan**:
	- Satu fasilitas (hotel_booking_amenities) dapat terkait dengan banyak baris di tabel perantara hotel_booking_room_amenities.
	- Setiap baris di tabel perantara hanya merujuk ke satu fasilitas.
	- Implementasi: Relasi ini diwakili oleh foreign key amenity_id yang ada pada tabel hotel_booking_room_amenities, yang merujuk pada id di tabel hotel_booking_amenities.
    

### Relasi hotel_booking_bookings dan hotel_booking_room_services

- **Jenis Relasi**: One-to-Many
- **Penjelasan**:
	- Satu pemesanan (hotel_booking_bookings) dapat memiliki banyak permintaan layanan kamar (hotel_booking_room_services).
	- Setiap permintaan layanan hanya terkait dengan satu pemesanan.
	- Implementasi: Meskipun tidak terlihat secara eksplisit pada diagram yang Anda berikan, relasi ini bisa diasumsikan dengan menambahkan foreign key booking_id pada tabel hotel_booking_room_services, yang merujuk ke id di tabel hotel_booking_bookings. Ini akan menghubungkan setiap layanan yang diminta dengan pemesanan spesifik yang bersangkutan.

---
# Struktur Proyek

Struktur ini dirancang agar setiap tim dapat bekerja secara terorganisir dan efisien.

## Frontend

```
frontend/

│── public/                 # Static files (images, icons, manifest, dll)

│── src/

│   │── app/                # (khusus Next.js App Router)

│   │   │── layout.tsx      # Layout global

│   │   │── page.tsx        # Halaman utama

│   │   └── ...

│   │

│   │── features/           # Modularisasi by-feature

│   │   │── auth/           # Fitur authentication

│   │   │   │── components/

│   │   │   │── hooks/

│   │   │   │── services/

│   │   │   └── pages/

│   │   │── dashboard/      # Fitur dashboard

│   │   │   │── components/

│   │   │   └── pages/

│   │

│   │── components/         # Reusable UI components (button, modal, input)

│   │── hooks/              # Reusable React hooks

│   │── lib/                # Library/helper (fetch wrapper, formatters)

│   │── store/              # State management (Redux/Zustand)

│   │── styles/             # Global CSS/Tailwind config

│   │── types/              # TypeScript types/interfaces

│   │── utils/              # Utility functions

│

│── .env                    # Environment variables

│── package.json

│── tsconfig.json
```

## Backend

```
backend/

│── src/

│   └── main/

│       └── java/com/example/app/

│           │── AppApplication.java         # Main entry

│           │

│           │── config/                     # Configuration (security, CORS, beans)

│           │── controller/                 # REST Controllers

│           │── dto/                        # Data Transfer Objects

│           │── entity/                     # JPA Entities

│           │── exception/                  # Custom exceptions & handler

│           │── repository/                 # JPA Repositories (DAO)

│           │── service/                    # Business logic (Service layer)

│           │── mapper/                     # DTO ↔ Entity converter

│           │── util/                       # Helper utils (date, formatter)

│

│   └── resources/

│       │── application.properties          # App config

│       │── application-dev.properties      # Dev config

│       │── application-prod.properties     # Prod config

│       └── static/                         # Static files (jika perlu)

│

│── pom.xml                                 # Maven dependencies
```
