# Appointment App 📅

نظام لحجز المواعيد أونلاين (Full-stack)، مبني بـ **React** و **Strapi**، بيسهّل على المستخدمين حجز المواعيد وعلى الإدارة تنظيمها.

## المميزات

- حجز موعد باختيار التاريخ والوقت المتاح
- إدارة المواعيد (عرض، تعديل، إلغاء)
- لوحة تحكم للإدارة عن طريق Strapi
- تسجيل دخول وصلاحيات المستخدمين
- واجهة Responsive تشتغل على الموبايل والكمبيوتر
- [أضف مميزاتك: إشعارات، تقويم، مواعيد الأطباء/الخدمات ...]

## هيكل المشروع

| الفولدر | الوصف | التقنيات |
|---|---|---|
| [`appointment_app`](./appointment_app) | واجهة المستخدم | React 19, TypeScript, Vite, Tailwind CSS 4, Redux Toolkit |
| [`backend`](./backend) | الـ API ولوحة الإدارة | Strapi 5, TypeScript, SQLite |

## المتطلبات

- Node.js 20 أو أحدث
- npm

## التشغيل محلياً

### 1. الـ Backend

```bash
cd backend
npm install
cp .env.example .env     # عدّل القيم السرية
npm run develop
```

- لوحة الإدارة: http://localhost:1337/admin
- الـ API: http://localhost:1337/api

### 2. الـ Frontend

في Terminal تاني:

```bash
cd appointment_app
npm install
npm run dev
```

أنشئ `appointment_app/.env`:

```env
VITE_API_URL=http://localhost:1337/api
```

## متغيرات البيئة

| الملف | المتغيرات |
|---|---|
| `backend/.env` | `APP_KEYS`, `API_TOKEN_SALT`, `ADMIN_JWT_SECRET`, `JWT_SECRET`, `TRANSFER_TOKEN_SALT`, `ENCRYPTION_KEY` |
| `appointment_app/.env` | `VITE_API_URL` |

> ⚠️ ملفات `.env` ممنوع تترفع على GitHub.

## الأوامر

| الأمر | الفولدر | الوظيفة |
|---|---|---|
| `npm run dev` | appointment_app | سيرفر التطوير |
| `npm run build` | appointment_app | بناء نسخة الإنتاج |
| `npm run develop` | backend | تشغيل Strapi للتطوير |
| `npm run start` | backend | تشغيل Strapi للإنتاج |

## المؤلف

**Mohamed Abuzaid** — [GitHub](https://github.com/mo7amedabuzaid)