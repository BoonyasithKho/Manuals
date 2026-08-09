# BurnCheck

เว็บแอปพลิเคชันที่ประกอบด้วย Backend API, Frontend Web Application และ PostgreSQL Database โดยสามารถรันระบบทั้งหมดผ่าน Docker Compose ได้

## Project Structure

โครงสร้างหลักของโปรเจกต์มีดังนี้

```text
project-root/
│
├── docker-compose.yml
├── .env
│
├── backend/
│   ├── Dockerfile
│   ├── package.json
│   ├── package-lock.json
│   └── src/
│       ├── index.js
│       └── db.js
│
└── web-app/
    ├── Dockerfile
    ├── package.json
    ├── package-lock.json
    ├── vite.config.js
    └── src/
```

## Requirements

ก่อนเริ่มใช้งาน ควรติดตั้งโปรแกรมต่อไปนี้

- Docker
- Docker Compose
- Git

ตรวจสอบว่า Docker สามารถใช้งานได้ด้วยคำสั่ง

```bash
docker --version
docker compose version
```

## Clone Project

ดาวน์โหลดโปรเจกต์จาก Git Repository

```bash
git clone <repository-url>
cd project-root
```

## Environment Variables

สร้างไฟล์ `.env` ที่ตำแหน่ง root ของโปรเจกต์

```text
project-root/
├── .env
├── docker-compose.yml
├── backend/
└── web-app/
```

ตัวอย่างการกำหนดค่า

```env
POSTGRES_DB=your_database
POSTGRES_USER=your_username
POSTGRES_PASSWORD=your_password
POSTGRES_HOST=postgres
POSTGRES_HOST=5432

DB_NAME=your_database
DB_USER=your_username
DB_PASSWORD=your_password

DATABASE_URL=postgresql://gistda_postgresuser:gistda_password@db:5432/burncheck_db

BACKEND_PORT=8000
FRONTEND_PORT=3000

JWT_SECRET=burncheck_secret_key_dev
```

> ควรแก้ไขค่าต่าง ๆ ให้ตรงกับการตั้งค่าของระบบจริง และไม่ควร commit รหัสผ่านหรือข้อมูลสำคัญลง Git Repository

แนะนำให้เพิ่ม `.env` ลงใน `.gitignore`

```gitignore
.env
```

## Run Project with Docker Compose

ที่ตำแหน่ง root ของโปรเจกต์ รันคำสั่ง

```bash
docker compose up --build
```

หากต้องการรันแบบ Background

```bash
docker compose up -d --build
```

ตรวจสอบ Container ที่กำลังทำงาน

```bash
docker compose ps
```

## Stop Project

หยุด Container

```bash
docker compose down
```

หากต้องการหยุดระบบและลบ Volume

```bash
docker compose down -v
```

> ระวัง: การใช้ `-v` จะลบ Docker Volume ซึ่งอาจรวมถึงข้อมูล PostgreSQL ที่จัดเก็บอยู่

## Rebuild Project

หากมีการแก้ไข `Dockerfile`, dependency หรือ configuration และต้องการ build ใหม่

```bash
docker compose down
docker compose up --build
```

หากต้องการบังคับ build ใหม่โดยไม่ใช้ cache

```bash
docker compose build --no-cache
docker compose up
```

## Backend

Backend อยู่ในโฟลเดอร์

```text
backend/
```

โครงสร้างหลัก

```text
backend/
├── Dockerfile
├── package.json
├── package-lock.json
└── src/
    ├── index.js
    └── db.js
```

ไฟล์สำคัญ

- `src/index.js` - จุดเริ่มต้นของ Backend API
- `src/db.js` - การเชื่อมต่อกับ PostgreSQL
- `package.json` - Dependencies และ Scripts ของ Backend
- `Dockerfile` - Configuration สำหรับสร้าง Backend Container

หากต้องการติดตั้ง dependencies โดยไม่ใช้ Docker

```bash
cd backend
npm install
```

## Web Application

Frontend อยู่ในโฟลเดอร์

```text
web-app/
```

โครงสร้างหลัก

```text
web-app/
├── Dockerfile
├── package.json
├── package-lock.json
├── vite.config.js
└── src/
```

Frontend พัฒนาด้วย Vite และ Node.js ecosystem

หากต้องการติดตั้ง dependencies โดยไม่ใช้ Docker

```bash
cd web-app
npm install
```

รัน Development Server

```bash
npm run dev
```

## Database

ระบบใช้ PostgreSQL เป็นฐานข้อมูลหลัก

เมื่อรันผ่าน Docker Compose ตัว Backend ควรเชื่อมต่อ PostgreSQL ผ่านชื่อ Service ของ PostgreSQL เช่น

```env
DB_HOST=postgres
DB_PORT=5432
```

ไม่ควรใช้

```env
DB_HOST=localhost
```

สำหรับการเชื่อมต่อระหว่าง Container เนื่องจาก `localhost` ภายใน Backend Container จะหมายถึง Backend Container เอง

## Useful Docker Commands

ดู Container ที่กำลังทำงาน

```bash
docker ps
```

ดู Log ของทุก Service

```bash
docker compose logs
```

ดู Log แบบต่อเนื่อง

```bash
docker compose logs -f
```

ดู Log เฉพาะ Backend

```bash
docker compose logs -f backend
```

Restart Service

```bash
docker compose restart
```

Restart เฉพาะ Backend

```bash
docker compose restart backend
```

เข้าไปภายใน Container

```bash
docker compose exec backend sh
```

## Troubleshooting

### Container ไม่ทำงาน

ตรวจสอบสถานะ

```bash
docker compose ps
```

และตรวจสอบ Log

```bash
docker compose logs
```

### Backend เชื่อมต่อ Database ไม่ได้

ตรวจสอบค่าใน `.env`

```env
DB_HOST=postgres
DB_PORT=5432
```

รวมถึงตรวจสอบว่า PostgreSQL Container ทำงานอยู่

```bash
docker compose ps
```

### แก้ไขโค้ดแล้วผลลัพธ์ไม่เปลี่ยน

ลอง Build Container ใหม่

```bash
docker compose down
docker compose up --build
```

หรือ

```bash
docker compose build --no-cache
docker compose up
```

## Development

Workflow เบื้องต้นสำหรับการพัฒนา

```bash
git pull

docker compose up -d --build

docker compose logs -f
```

หลังจากแก้ไขโค้ด

```bash
git status
git add .
git commit -m "update project"
git push
```

## License

กำหนด License ของโปรเจกต์ตามนโยบายของ Repository หรือหน่วยงานที่ดูแลโครงการ
