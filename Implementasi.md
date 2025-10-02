
User Story

User dapat menambahkan data kamar baru
- Database & Models
	- Create rooms table schema
	- Create Room entity dengan JPA annotations
	- Create RoomRequestDTO dan RoomResponseDTO
	- Create RoomRepository extending JpaRepository
- Business Logic
	- Create createRoom() method di RoomService
	- Create POST /api/rooms endpoint di RoomController
	- Add validation untuk room number uniqueness
- State & API
	- Create roomSlice.ts untuk Redux state
	- Create roomService.ts dengan createRoom() API call
- Pages & Components
	- Create AddRoomPage.tsx component
	- Create RoomForm.tsx dengan validation
	- Add navigation dari Room List ke Add Room page
	- Create success/error notification
## Backend

## Database & Models

Jalankan prompt berikut:

```
Setup Spring Boot menggunakan Hibernate JPA dengan konfigurasi database MySQL localhost:
- host: localhost
- port: 3306
- database: hotel_db
- username: root
- password: 
```

```
1. Buat schema 'rooms' table di MySQL dengan field-field berikut (deskripsi sederhana):
   - id (Long, @Id, @GeneratedValue)
   - adultCapacity (int)
   - childrenCapacity (int)
   - createdAt (LocalDateTime, @CreationTimestamp)
   - price (BigDecimal)
   - roomNumber (String, unique)
   - updatedAt (LocalDateTime, @UpdateTimestamp, nullable)
   - description (String, nullable)
   - isActive (boolean)
   - roomType (Enum: STANDARD, DELUXE, SUITE, @Enumerated(EnumType.STRING))
```

2. Buat entity class 'Room' di package 'entity' dengan Hibernate annotations sesuai schema di atas.

3. Buat DTO di package 'dto':
	   - RoomRequestDTO' untuk input request
	   - RoomResponseDTO' untuk output response

3. Buat 'RoomRepository' di package 'repository' yang extend JpaRepository<Room, Long>.

4. Pastikan Hibernate mengelola entity 'Room':
	   - Mapping kolom 'roomNumber' dengan unique constraint
	   - Mapping kolom 'createdAt' dan 'updatedAt' dengan otomatisasi Hibernate
	   - Mapping enum 'roomType' dengan '@Enumerated(EnumType.STRING)'

5. Atur 'application.properties' untuk koneksi ke MySQL:
	   - spring.datasource.url=jdbc:mysql://localhost:3306/hotel_db
	   - spring.datasource.username=root
	   - spring.datasource.password=root
	   - spring.jpa.hibernate.ddl-auto=update
	   - spring.jpa.show-sql=true
	   - spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect  

Gunakan praktik clean code sesuai struktur project Spring Boot di atas.

## Business Logic
Jalankan prompt berikut:

Tambahkan pada project backend Spring Boot berikut:

1. Buat method 'createRoom(RoomRequestDTO request)' di 'RoomService':
   - Menerima data dari RoomRequestDTO
   - Mengecek apakah roomNumber sudah ada di database (gunakan RoomRepository)
   - Jika sudah ada, lempar custom exception 'RoomAlreadyExistsException'
   - Jika belum ada, simpan data baru ke table 'rooms'
   - Return RoomResponseDTO setelah berhasil disimpan

2. Buat endpoint POST '/api/rooms' di 'RoomController':
   - Menerima request body JSON yang dipetakan ke RoomRequestDTO
   - Memanggil 'roomService.createRoom()'
   - Mengembalikan response dalam bentuk RoomResponseDTO dengan status 201 CREATED
   - Tangani exception 'RoomAlreadyExistsException' dan kembalikan status 400 BAD REQUEST dengan pesan error

3. Tambahkan validasi untuk roomNumber uniqueness:
   - Pada level DTO gunakan '@NotBlank' untuk memastikan tidak kosong
   - Pada level service pastikan roomNumber tidak duplikat dengan query ke RoomRepository
   - Gunakan custom exception untuk error handling

4. Pastikan semua class berada di package sesuai struktur:
   - 'controller/RoomController.java'
   - 'service/RoomService.java'
   - 'dto/RoomRequestDTO.java' dan 'dto/RoomResponseDTO.java'
   - 'exception/RoomAlreadyExistsException.java'
   - 'repository/RoomRepository.java'
   - 'entity/Room.java'

5. Pastikan semua kode menggunakan praktik clean architecture Spring Boot:
   - DTO dipakai hanya di lapisan controller/service
   - Entity hanya di repository/service
   - Validasi pakai Hibernate Validator ('@NotBlank', dsb)
   - Exception ditangani oleh global exception handler di package 'exception'

## Dokumentasi API

Jalankan prompt ini:

Buatkan dokumentasi API untuk fitur Room pada backend Spring Boot yang sudah dibuat. Dokumentasi harus berisi:

1. Endpoint Deskripsi
   - Nama endpoint
   - Method (HTTP verb)
   - Path URL
   - Deskripsi singkat fungsinya

2. Request Format
   - Header yang dibutuhkan (misalnya Content-Type: application/json)
   - Contoh JSON body (untuk request yang membutuhkan payload)

3. Response Format
   - Contoh response sukses (200/201)
   - Contoh response error (400/404/500)

4. Sample Request untuk testing API
   - Contoh curl command
   - Contoh request di Postman (JSON body)

Dokumentasi harus mencakup endpoint berikut:

- POST /api/rooms
  - Membuat room baru dengan data dari 'RoomRequestDTO'
  - Validasi: 'roomNumber' harus unik
  - Jika duplikat, return error dengan status 400

- (Opsional, jika ada) GET /api/rooms
  - Mengambil semua room yang tersedia

Gunakan format markdown agar mudah dibaca, misalnya:

  

## Create Room

POST '/api/rooms'
- Deskripsi: Membuat room baru
- Request body:

```
{

  "roomNumber": "101",

  "type": "DELUXE",

  "capacity": 2,

  "price": 500000.00

}
```

AI akan membuat file API_DOCUMENTATION.md

## Frontend

## Pages & Components

Gunakan [https://aistudio.google.com/](https://aistudio.google.com/) untuk slicing UI dari gambar hasil export Figma, dan jalankan prompt berikut:

  

Buatkan fitur Add Room untuk project frontend React + TypeScript + Tailwind dengan struktur project berikut:

  

booking-fe/

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

  

Task yang harus dibuat:

1. Create AddRoomPage.tsx component

   - Lokasi: 'src/features/dashboard/pages/AddRoomPage.tsx'

   - Page ini menampilkan judul “Add New Room” dan menyertakan RoomForm.

  

2. Create RoomForm.tsx dengan validation & UI slicing

   - Lokasi: 'src/features/dashboard/components/RoomForm.tsx'

   - Gunakan React Hook Form + Zod untuk validasi.

   - Field form:

     - 'roomNumber' (string, required, unique)

     - 'type' (select: STANDARD, DELUXE, SUITE)

     - 'capacity' (number, required, min 1)

     - 'price' (number, required, min 0)

     - 'description' (textarea, optional)

   - Tambahkan validasi: tampilkan error di bawah input jika tidak valid.

   - UI harus di-slicing mengikuti desain dari gambar yang saya lampirkan (warna, spacing, typography, button style sesuai gambar).

   - Pastikan layout responsive (desktop + mobile).

  

3. Add navigation dari Room List ke Add Room page

   - Pada 'RoomListPage.tsx' (asumsi sudah ada), tambahkan button “+ Add Room”

   - Button akan navigate ke '/dashboard/add-room'.

  

4. Create success/error notification

   - Buat reusable component 'Notification.tsx' di 'src/components/Notification.tsx'

   - Tampilkan notifikasi sukses jika room berhasil ditambahkan, atau error jika gagal.

   - Gunakan Tailwind untuk styling, tambahkan animasi sederhana (slide in/out).

  

Tambahan aturan implementasi:

- Gunakan TypeScript interface 'Room' dari 'src/types/room.ts'

- Gunakan axios instance dari 'src/lib/axios.ts' untuk API call

- Semua UI pakai TailwindCSS, responsive sesuai desain gambar

- Terapkan clean code: pisahkan page, form, service, dan komponen.

  

Setelah selesai di generate, download app dan extract di project

Install dependencies dengan menjalankan npm install

Jalankan npm run dev untuk running aplikasi

## State & API

Jalankan prompt ini:

  

Buatkan integrasi Redux + Service untuk fitur Room dengan detail berikut:

Task:

1. Create roomSlice.ts untuk Redux state

   - Lokasi: 'src/store/roomSlice.ts'

   - Gunakan Redux Toolkit ('createSlice', 'createAsyncThunk')

   - State berisi:

     - 'rooms': Room[] (list room)

     - 'loading': boolean

     - 'error': string | null

   - Tambahkan async thunk 'createRoom()' yang memanggil service API.

   - Handle 'pending', 'fulfilled', 'rejected'.

  

2. Create roomService.ts dengan createRoom() API call

   - Lokasi: 'src/features/dashboard/services/roomService.ts'

   - Gunakan axios instance dari 'src/lib/axios.ts'

   - Method: 'POST /api/rooms'

   - Request body: 'RoomRequestDTO'

   - Return: 'RoomResponseDTO'

   - Jika error (status 400), lempar pesan error dari response.

  

3. Gunakan TypeScript types

   - Buat interface di 'src/types/room.ts':

     ts

     export interface RoomRequestDTO {

       adultCapacity: number;

       childrenCapacity: number;

       price: number;

       roomNumber: string;

       description?: string;

       isActive: boolean;

       roomType: "STANDARD" | "DELUXE" | "SUITE";

     }

  

     export interface RoomResponseDTO {

       id: number;

       adultCapacity: number;

       childrenCapacity: number;

       createdAt: string;

       price: number;

       roomNumber: string;

       updatedAt?: string;

       description?: string;

       isActive: boolean;

       roomType: "STANDARD" | "DELUXE" | "SUITE";

     }

  

4. API Spec

   - Endpoint: 'POST /api/rooms'

   - Header: 'Content-Type: application/json'

   - Request body contoh:

     json

     {

       "adultCapacity": 2,

       "childrenCapacity": 1,

       "price": 1500000.00,

       "roomNumber": "A101",

       "description": "Kamar standar dengan pemandangan kota.",

       "isActive": true,

       "roomType": "STANDARD"

     }

   - Response success (201):

     json

     {

       "id": 1,

       "adultCapacity": 2,

       "childrenCapacity": 1,

       "createdAt": "2025-09-10T10:30:00",

       "price": 1500000.00,

       "roomNumber": "A101",

       "updatedAt": "2025-09-10T10:30:00",

       "description": "Kamar standar dengan pemandangan kota.",

       "isActive": true,

       "roomType": "STANDARD"

     }

   - Response error (400 - RoomAlreadyExistsException):

     "Room with number A101 already exists."

   - Response error (400 - Validation Error):

     json

     {

       "roomNumber": "Room number cannot be empty"

     }

  

Aturan tambahan:

- Semua ditulis dengan TypeScript.

- Gunakan clean code (pisahkan slice, service, types).

- Pastikan error dari API ditangani dengan baik di Redux slice.

  
**