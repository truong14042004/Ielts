# 🎮 IELTS Quest

> Học tiếng Anh IELTS qua chơi game - Gamified IELTS Learning Platform

## 🚀 Giới thiệu

IELTS Quest là nền tảng web game giáo dục, kết hợp gamification với việc học tiếng Anh IELTS. Người dùng sẽ được trải nghiệm các mini-game thú vị, qua đó vừa giải trí vừa nâng cao trình độ IELTS một cách hiệu quả.

## ✨ Tính năng

- 📚 **Vocabulary Builder** - Xây dựng từ vựng IELTS
- 🎧 **Listening Lab** - Luyện nghe IELTS
- 📖 **Reading Arena** - Luyện đọc IELTS
- ✍️ **Writing Workshop** - Luyện viết IELTS
- 🗣️ **Speaking Studio** - Luyện nói IELTS
- 🏆 **Hệ thống Achievement** - Phần thưởng & Huy hiệu
- 📊 **Progress Tracking** - Theo dõi tiến độ học tập
- 👑 **Leaderboard** - Bảng xếp hạng người chơi

## 🛠️ Tech Stack

### Frontend
- ⚛️ Next.js 14 (App Router)
- 🎨 Tailwind CSS + Shadcn/ui
- 🎮 Framer Motion

### Backend
- 🟢 Next.js API Routes (TypeScript)
- 🗄️ Vercel Postgres (PostgreSQL)
- 🧪 Prisma ORM
- 🔐 NextAuth.js

### DevOps
- ☁️ Vercel (Hosting)
- 🐳 Docker (Containerization)
- 🌿 Git + GitHub

## 📦 Cài đặt

```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/ielts-quest.git
cd ielts-quest

# Cài đặt dependencies
npm install

# Cài đặt Prisma & tạo database
npx prisma generate
npx prisma db push

# Chạy development server
npm run dev
```

## 🔧 Cấu hình môi trường

Tạo file `.env.local` trong thư mục gốc:

```env
# Database
POSTGRES_URL=postgresql://user:password@host:5432/database?sslmode=require

# NextAuth
NEXTAUTH_SECRET=your-secret-key
NEXTAUTH_URL=http://localhost:3000

# Resend (Email)
RESEND_API_KEY=your-resend-api-key
```

## 📁 Cấu trúc dự án

```
ielts-quest/
├── prisma/
│   └── schema.prisma    # Database schema
├── src/
│   ├── app/              # Next.js App Router
│   ├── components/       # React components
│   ├── lib/              # Utilities & helpers
│   └── styles/           # Global styles
├── public/               # Static assets
├── SPEC.md               # Project specification
└── README.md
```

## 🎮 Các Game

### Vocabulary Builder
| Game | Mô tả |
|------|-------|
| Word Match | Ghép từ vựng với nghĩa tiếng Việt |
| Spelling Bee | Điền chính tả từ vựng |
| Word Puzzle | Giải ô chữ từ vựng IELTS |
| Flash Card Race | Lật thẻ nhanh để ghi nhớ từ |

### Listening Lab
| Game | Mô tả |
|------|-------|
| Dictation | Nghe và viết lại câu |
| Multiple Choice | Chọn đáp án đúng khi nghe |
| Audio Sequence | Sắp xếp câu đúng thứ tự |

## 👥 Đóng góp

1. Fork repository
2. Tạo feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Tạo Pull Request

## 📄 License

Dự án này được phân phối theo giấy phép MIT.

## 📧 Liên hệ

- GitHub Issues: [Link Issues](https://github.com/YOUR_USERNAME/ielts-quest/issues)

---

⭐ Nếu dự án này hữu ích, hãy star cho mình nhé!
