**

## Metode Prompting

1. Persiapan Input
	- Kumpulkan semua bahan: user story, database schema, ERD, acceptance criteria, dan mockup Figma.
    - Strukturkan dalam format rapi (misalnya markdown atau doc). Contoh:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP1.png?raw=true)
2. High-level Prompting 
	Gunakan AI untuk membuat rancangan awal: arsitektur, API design, struktur folder React & Spring Boot.
	Prompt contoh:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP2.png?raw=true)
3. Incremental Prompting (Modular)
	Jangan langsung minta full code satu kali. Bagi jadi 4 kategori besar:

	- Database & Models (Spring Boot Entities, JPA, DTO)
	- Business Logic (Service & Repository)
	- API Layer (Controller + Request/Response)
	- Frontend (React Components + State Management + API calls)
	Contoh prompt untuk model:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP3.png?raw=true)
4. Design-to-Code Prompting (Mockup → Component)
	- Untuk frontend (Figma → React):
	- Kita bisa export figma ke image
	- Atau menggunakan MCP Server dari Figma
	- Mulai dari layout dasar → minta AI generate JSX dengan Tailwind.
	- Lanjut ke state & API integration.
	- Gunakan prompt slicing → satu halaman per prompt agar hasil lebih bersih.
	Contoh prompt:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP4.png?raw=true)
5. Validation & Refinement
	Setelah AI generate, cek acceptance criteria satu per satu.
	Jika ada gap, gunakan prompt lanjutan:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP5.png?raw=true)
6. Iterasi & Integrasi
	Setelah semua komponen modular siap, gabungkan manual.
	Gunakan AI untuk refactor:
	![MetodePrompt](https://github.com/pputraining1/AI-Learning-language/blob/main/Img/MP6.png?raw=true)
## Kerangka Prompting 4C

4C adalah kerangka untuk membuat prompt yang jelas, terstruktur, dan bisa diulang ketika kita minta AI generate kode atau solusi.

Tujuannya: mengurangi jawaban “ngaco” dan memastikan hasil sesuai kebutuhan developer.

1. Context    
	Memberikan latar belakang yang cukup agar AI tahu lingkungan & tujuan.
	- Framework / tools (React, Spring Boot, PostgreSQL, Tailwind, Redux).
	- Domain problem (booking hotel, sistem rumah sakit, e-commerce).
	- Level detail (apakah butuh full code, hanya function, atau arsitektur).
	Contoh:

2. Constraint
	Aturan & batasan yang harus dipatuhi AI dalam hasilnya.
	- Acceptance criteria.
	- Validasi tertentu.
	- Style coding (DTO wajib, RESTful, Clean Architecture).
	- Library / framework yang boleh digunakan.
	Contoh:
	
3. Command
	Instruksi utama: apa yang ingin dibuat/generate.
	- Bisa berupa generate code, buat arsitektur, atau refactor.
	- Fokus 1 tugas per prompt (lebih rapi & terarah).
	Contoh:
	
4. Check
	Bagian ini membantu AI mengevaluasi hasilnya sendiri sebelum memberikan output.
	- Format output yang diinginkan (Java class, TSX file).
	- Cara validasi (harus sesuai acceptance criteria, harus ada validasi unik, dll).
	- Kadang juga kita bisa tambahkan expected output (contoh JSON response).
	Contoh:

	Contoh Full Prompt dengan Kerangka Prompting 4C:

## Code Review

1. Cek Kesesuaian dengan User Story & Acceptance Criteria
    

- Buka kembali user story + acceptance criteria.
    
- Buat checklist.
    

Contoh untuk “User dapat menambahkan data kamar baru”:

1.  Entity Room ada dengan field id dan roomNumber unik
    
2.  Service createRoom() ada, validasi uniqueness jalan
    
3.  API POST /api/rooms tersedia
    
4.  Frontend punya form tambah room
    
5.  Ada notifikasi sukses/error
    

  

6. Code Quality & Clean Code Check
    

- Check naming convention, apakah nama class, dan variable sudah sesuai
    
- Check structure project apakah sudah sesuai
    
- Check pada IDE apakah masih ada warning atau error
    
- Check apakah ada redudancy atau duplicate logic
    
- Check error handling apakah sudah konsisten
    

3. Testing Manual
    

- Pada backend project dapat dijalankan dan test endpoint API menggunakan tools seperti Postman
    
- Pada frontend project dapat dijalankan dan di test apakah fitur sudah sesuai dengan user story atau belum
    

4. Cross-Check dengan Database
    

Pastikan struktur tabel dan constraint yang terbentuk pada database sudah sesuai

5. Static Analysis & Linter
    

Backend: pada IDE dapat menginstall extension seperti Sonarcube.

Frontend: pada IDE dapat menginstall extension ESLint + Prettier.

Agar mempermudah untuk mendeteksi issue pada IDE

6. Iterasi dengan AI
    

Kalau saat manual check Anda temukan issue, kembalikan ke AI dengan prompt spesifik:

  
**