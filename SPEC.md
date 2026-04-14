# 🎮 IELTS Quest - Web Game Học Tiếng Anh IELTS

## 1. Tổng Quan Dự Án

### 1.1 Giới thiệu
**IELTS Quest** là một nền tảng web game giáo dục, kết hợp gamification với việc học tiếng Anh IELTS. Người dùng sẽ được trải nghiệm các mini-game thú vị, qua đó vừa giải trí vừa nâng cao trình độ IELTS một cách hiệu quả.

### 1.2 Mục tiêu
- Học tiếng Anh IELTS qua gameplay hấp dẫn
- Theo dõi tiến độ học tập rõ ràng
- Phù hợp với mọi trình độ (Beginner → Advanced)
- Tạo động lực học tập qua hệ thống phần thưởng

### 1.3 Đối tượng người dùng
- Học sinh, sinh viên chuẩn bị thi IELTS
- Người đi làm muốn cải thiện tiếng Anh
- Người mới bắt đầu học tiếng Anh nâng cao

---

## 2. Tính Năng Chính

### 2.1 Các Mini-Games Chính

#### 📚 **1. Vocabulary Builder (Xây Dựng Từ Vựng)**
| Game | Mô tả | Kỹ năng |
|------|-------|---------|
| **Word Match** | Ghép từ vựng với nghĩa tiếng Việt | Từ vựng |
| **Spelling Bee** | Điền chính tả từ vựng | Spelling |
| **Word Puzzle** | Giải ô chữ từ vựng IELTS | Từ vựng + Ngữ pháp |
| **Flash Card Race** | Lật thẻ nhanh để ghi nhớ từ | Memory + Từ vựng |

#### 🎧 **2. Listening Lab (Luyện Nghe)**
| Game | Mô tả | Kỹ năng |
|------|-------|---------|
| **Dictation** | Nghe và viết lại câu | Listening + Writing |
| **Multiple Choice** | Chọn đáp án đúng khi nghe | Listening comprehension |
| **Audio Sequence** | Sắp xếp câu đúng thứ tự nghe được | Listening + Grammar |

#### 📖 **3. Reading Arena (Luyện Đọc)**
| Game | Mô tả | Kỹ năng |
|------|-------|---------|
| **Quick Scan** | Tìm từ khóa nhanh trong bài đọc | Skimming |
| **Fill in Blank** | Điền từ còn thiếu vào đoạn văn | Reading comprehension |
| **True/False/Not Given** | Xác định câu đúng/sai/không có trong bài | Critical reading |

#### ✍️ **4. Writing Workshop (Luyện Viết)**
| Game | Mô tả | Kỹ năng |
|------|-------|---------|
| **Sentence Building** | Sắp xếp từ thành câu đúng ngữ pháp | Grammar |
| **Paragraph Puzzle** | Sắp xếp câu thành đoạn văn mạch lạc | Coherence & Cohesion |
| **Essay Outline** | Lập dàn ý bài luận IELTS | Writing structure |

#### 🗣️ **5. Speaking Studio (Luyện Nói)**
| Game | Mô tả | Kỹ năng |
|------|-------|---------|
| **Pronunciation** | Phát âm và nhận dạng từ | Speaking + Pronunciation |
| **Topic Talk** | Trả lời câu hỏi theo chủ đề IELTS | Fluency |
| **Picture Description** | Mô tả hình ảnh theo mẫu IELTS | Speaking Part 2 |

### 2.2 Hệ Thống Phần Thưởng & Gamification

```
🏆 Hệ thống Achievement:
├── 🥉 Bronze Badges (0-100 XP)
├── 🥈 Silver Badges (100-500 XP)  
├── 🥇 Gold Badges (500-1000 XP)
├── 💎 Diamond Badges (1000+ XP)
└── 👑 IELTS Champion (Hoàn thành tất cả)
```

**Yếu tố gamification:**
- ⭐ **Star Rating**: Đánh giá 1-3 sao mỗi game
- 💰 **Coins**: Tiền tệ trong game để unlock items
- 🏅 **Achievements**: Huy hiệu thành tích
- 📊 **Leaderboard**: Bảng xếp hạng người chơi
- 🎁 **Daily Streak**: Chuỗi ngày học liên tiếp
- 📈 **Level System**: Cấp độ người chơi (Beginner → Master)

### 2.3 Theo Dõi Tiến Độ

- **Dashboard cá nhân**: Hiển thị điểm mạnh/yếu theo từng kỹ năng
- **Progress Chart**: Biểu đồ tiến độ học tập
- **Skill Radar**: Đánh giá 4 kỹ năng IELTS (Listening, Reading, Writing, Speaking)
- **Practice History**: Lịch sử bài tập đã làm

---

## 3. Nội Dung Học Tập

### 3.1 Cấu trúc Từ Vựng theo chủ đề IELTS
```
📁 IELTS Vocabulary Topics:
├── 📌 Academic Word List (AWL)
├── 📌 General Training Vocabulary
├── 📌 Common IELTS Topics:
│   ├── Education
│   ├── Environment
│   ├── Technology
│   ├── Health
│   ├── Society
│   ├── Culture
│   ├── Work & Business
│   └── Travel & Tourism
```

### 3.2 Bài nghe theo dạng IELTS
- Short conversations (Part 1)
- Long discussions (Part 2)
- Interviews (Part 3)
- Academic discussions (Part 4)

### 3.3 Bài đọc mẫu IELTS
- Biểu đồ, đồ thị (Part 1)
- Bài luận học thuật (Part 2)
- Bài báo khoa học (Part 3)

---

## 4. Kiến Trúc Kỹ Thuật

### 4.1 Tech Stack (Đề xuất)

#### **Frontend (Client-side)**
| Technology | Purpose |
|------------|---------|
| ⚛️ Next.js 14 (App Router) | UI Framework + API routes |
| 🎨 Tailwind CSS + Shadcn/ui | Styling + Components |
| 🎮 Framer Motion | Animations |
| 🔊 Howler.js | Audio playback |
| 📱 Responsive Design | Mobile-friendly |

#### **Backend (Server-side)** - Tích hợp trong Next.js
| Technology | Purpose |
|------------|---------|
| 🟢 Next.js API Routes | Backend API (TypeScript) |
| 🗄️ **Vercel Postgres** | Database (PostgreSQL on Vercel) |
| 🧪 Prisma ORM | Database ORM |
| 🔐 NextAuth.js | Authentication |
| 📧 Resend | Email notifications |

#### **Database: Vercel Postgres**
| Feature | Details |
|---------|---------|
| 🗄️ Provider | Vercel Postgres (Neon-powered) |
| 💰 Pricing | Free tier: 1GB storage, 10M row reads |
| 🔗 Integration | Native Vercel integration |
| 🌍 Region | Auto-select closest region |
| ⚡ Performance | Serverless, auto-scaling |

### 4.1.1 Backend TypeScript Architecture
```
📁 Backend Structure:
├── src/
│   ├── controllers/      # Business logic
│   ├── routes/           # API endpoints
│   ├── middleware/      # Auth, validation
│   ├── services/        # Core services
│   ├── entities/       # TypeScript interfaces
│   ├── config/         # Environment config
│   └── utils/          # Helper functions
│
├── prisma/
│   └── schema.prisma   # Database schema
│
└── package.json
```

#### **DevOps & Tools**
| Tool | Purpose |
|------|---------|
| 🐳 Docker | Containerization |
| 🌿 Git | Version control |
| ☁️ Vercel / Netlify | Hosting (Frontend) |
| 🖥️ Railway / Render | Hosting (Backend) |

### 4.2 Database Schema (Vercel Postgres với Prisma)

#### Kết nối Vercel Postgres
```bash
# Cài đặt Vercel CLI
npm i -g vercel

# Link project với Vercel
vercel link

# Pull environment variables
vercel env pull .env.local

# Hoặc thêm biến môi trường thủ công trong Vercel Dashboard:
# DATABASE_URL=postgresql://user:password@host:5432/database?sslmode=require
```

#### Prisma Schema
```prisma
// prisma/schema.prisma

generator client {
  provider = "prisma-client-js"
  // Thêm previewFeatures cho Vercel Postgres
  previewFeatures = ["postgresqlExtensions"]
}

datasource db {
  provider = "postgresql"
  url      = env("POSTGRES_URL")  // Vercel Postgres URL
  extensions = [pg_trgm, citext]  // PostgreSQL extensions
}
```

// ==================== USER & AUTH ====================
model User {
  id            String    @id @default(uuid())
  email         String    @unique
  username      String    @unique
  password      String    // hashed with bcrypt
  avatar        String?   // URL avatar
  level         Int       @default(1)
  xp            Int       @default(0)
  coins         Int       @default(0)
  streakDays    Int       @default(0)
  lastPlayedAt  DateTime?
  createdAt     DateTime  @default(now())
  updatedAt     DateTime  @updatedAt

  // Relations
  progress      UserProgress[]
  achievements  UserAchievement[]
  vocabProgress VocabularyProgress[]
  gameHistory   GameHistory[]
  
  @@map("users")
}

// ==================== GAMES ====================
model Game {
  id          String   @id @default(uuid())
  name        String
  slug        String   @unique  // e.g., "word-match", "spelling-bee"
  category    String   // "vocabulary", "listening", "reading", "writing", "speaking"
  description String?
  icon        String?  // emoji or icon class
  difficulty  Int      @default(1)  // 1-5
  xpReward    Int      @default(10)
  coinReward  Int      @default(5)
  createdAt   DateTime @default(now())

  // Relations
  progress    UserProgress[]
  history     GameHistory[]
  questions   GameQuestion[]
  
  @@map("games")
}

model GameQuestion {
  id        String   @id @default(uuid())
  gameId    String
  game      Game     @relation(fields: [gameId], references: [id])
  type      String   // "multiple_choice", "fill_blank", "matching", etc.
  content   Json    // question data (text, options, correct answer, etc.)
  difficulty Int     @default(1)
  createdAt DateTime @default(now())

  @@map("game_questions")
}

// ==================== VOCABULARY ====================
model Vocabulary {
  id             String   @id @default(uuid())
  word           String
  pronunciation  String?  // IPA: /wɜːrd/
  partOfSpeech   String?  // noun, verb, adjective, etc.
  meaning        String   // nghĩa tiếng Việt
  example        String?  // ví dụ câu
  exampleMeaning String?  // nghĩa ví dụ
  audioUrl       String?  // pronunciation audio
  topic          String   // "education", "technology", etc.
  level          String   @default("A2")  // CEFR: A1, A2, B1, B2, C1, C2
  createdAt      DateTime @default(now())

  // Relations
  progress       VocabularyProgress[]

  @@unique([word, topic])
  @@map("vocabularies")
}

// ==================== USER PROGRESS ====================
model UserProgress {
  id          String   @id @default(uuid())
  userId      String
  gameId      String
  game        Game     @relation(fields: [gameId], references: [id])
  user        User     @relation(fields: [userId], references: [id])
  highScore   Int      @default(0)
  stars       Int      @default(0)  // 0-3 stars
  timesPlayed Int      @default(0)
  bestTime    Int?     // seconds
  updatedAt   DateTime @updatedAt

  @@unique([userId, gameId])
  @@map("user_progress")
}

model VocabularyProgress {
  id          String     @id @default(uuid())
  userId      String
  vocabId     String
  vocabulary  Vocabulary @relation(fields: [vocabId], references: [id])
  correct     Int        @default(0)
  incorrect   Int        @default(0)
  lastTested  DateTime?
  mastered    Boolean    @default(false)
  updatedAt   DateTime   @updatedAt

  @@unique([userId, vocabId])
  @@map("vocabulary_progress")
}

model GameHistory {
  id        String   @id @default(uuid())
  userId    String
  gameId    String
  game      Game     @relation(fields: [gameId], references: [id])
  score     Int
  correct   Int
  incorrect Int
  timeSpent Int      // seconds
  xpEarned  Int
  coinsEarned Int
  playedAt  DateTime @default(now())

  @@index([userId, playedAt])
  @@map("game_history")
}

// ==================== ACHIEVEMENTS ====================
model Achievement {
  id          String   @id @default(uuid())
  name        String
  slug        String   @unique
  description String
  icon        String?
  category    String   // "vocabulary", "streak", "level", "special"
  requirement Json     // e.g., {"type": "games_played", "count": 10}
  xpReward    Int      @default(50)
  coinReward  Int      @default(25)
  createdAt   DateTime @default(now())

  @@map("achievements")
}

model UserAchievement {
  id            String      @id @default(uuid())
  userId        String
  achievementId String
  achievement   Achievement @relation(fields: [achievementId], references: [id])
  earnedAt      DateTime    @default(now())

  @@unique([userId, achievementId])
  @@map("user_achievements")
}

// ==================== LEADERBOARD ====================
model Leaderboard {
  id        String   @id @default(uuid())
  period    String   // "daily", "weekly", "monthly", "all_time"
  userId    String
  username  String
  totalXp   Int
  rank      Int
  updatedAt DateTime @updatedAt

  @@unique([period, userId])
  @@index([period, rank])
  @@map("leaderboards")
}
```

---

## 5. Giao Diện Người Dùng (UI/UX)

### 5.1 Trang Chủ (Home)
```
┌─────────────────────────────────────────┐
│  🎮 IELTS Quest          [👤] [⚙️]     │
├─────────────────────────────────────────┤
│                                         │
│   🎯 "Học IELTS qua chơi game!"         │
│                                         │
│   ╔═══════════════════════════════╗    │
│   ║  Continue Learning            ║    │
│   ║  📊 45% Today    🔥 7 days    ║    │
│   ╚═══════════════════════════════╝    │
│                                         │
│   🎮 Quick Play                         │
│   ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐      │
│   │ 📚  │ │ 🎧  │ │ 📖  │ │ 🗣️  │      │
│   │ Vocab│ │Listen│ │Read │ │Speak│      │
│   └─────┘ └─────┘ └─────┘ └─────┘      │
│                                         │
│   📈 Your Progress                       │
│   ┌─────────────────────────────────┐   │
│   │  Listening ████████░░ 80%      │   │
│   │  Reading   ██████░░░░ 60%      │   │
│   │  Writing   ████░░░░░░ 40%      │   │
│   │  Speaking  ███████░░░ 70%      │   │
│   └─────────────────────────────────┘   │
│                                         │
└─────────────────────────────────────────┘
```

### 5.2 Màn hình Game
```
┌─────────────────────────────────────────┐
│  ← Back    ⏱️ 00:45    ⭐⭐⭐   💰 50   │
├─────────────────────────────────────────┤
│                                         │
│   Câu 5/10                              │
│   ████████████░░░░░░░░░░░ 50%          │
│                                         │
│   ┌───────────────────────────────┐   │
│   │                               │   │
│   │    What is the synonym of     │   │
│   │    "ENORMOUS"?                │   │
│   │                               │   │
│   └───────────────────────────────┘   │
│                                         │
│   ┌─────────────┐  ┌─────────────┐     │
│   │    A. Tiny  │  │  B. Huge    │     │
│   └─────────────┘  └─────────────┘     │
│   ┌─────────────┐  ┌─────────────┐     │
│   │  C. Fast    │  │  D. Slow    │     │
│   └─────────────┘  └─────────────┘     │
│                                         │
│   💡 Hint (-10 coins)                   │
│                                         │
└─────────────────────────────────────────┘
```

### 5.3 Màu sắc & Phong cách
```
🎨 Design System:
├── Primary: #6366F1 (Indigo - chủ đạo)
├── Secondary: #10B981 (Emerald - thành công)
├── Accent: #F59E0B (Amber - phần thưởng)
├── Background: #0F172A (Dark mode)
├── Text: #F8FAFC (Light text)
└── Game UI: Rounded corners, smooth animations
```

---

## 6. Lộ Trình Phát Triển

### Phase 1: MVP (2-3 tuần)
```
✅ Core Features:
- Đăng ký/Đăng nhập
- 1-2 mini-games (Vocabulary)
- Hệ thống XP & Level
- Dashboard cơ bản
```

### Phase 2: Core Games (4-6 tuần)
```
📚 Expanding Games:
- Listening games (5-8 games)
- Reading games (5-8 games)  
- Vocabulary (10+ games)
- Hệ thống Achievement
- Leaderboard
```

### Phase 3: Full Features (8-12 tuần)
```
🎯 Advanced Features:
- Speaking games (với microphone)
- Writing games (auto-grading)
- Progress tracking chi tiết
- Social features (chia sẻ, so sánh)
- Mobile responsive
```

### Phase 4: Polish & Launch
```
🚀 Launch:
- Testing & Bug fixes
- Performance optimization
- SEO & Marketing
- Launch chính thức
```

---

## 7. Ước Tính Chi Phí (nếu có)

### Chi phí hàng tháng (Production)
| Service | Chi phí |
|---------|---------|
| Domain (.com) | ~$12/năm |
| Hosting (Vercel Pro) | ~$20/tháng |
| Database (MongoDB Atlas) | ~$0-30/tháng |
| Audio/CDN | ~$5-20/tháng |
| **Tổng** | **~$30-50/tháng** |

### Chi phí miễn phí (Starter)
- Vercel (Frontend): Free tier
- Railway (Backend): Free tier
- MongoDB Atlas: Free tier (512MB)
- **Tổng: $0/tháng** (đủ cho MVP)

---

## 8. Hệ Thống Admin Dashboard

### 8.1 Vai trò Admin

```
👑 Admin Roles:
├── 🔧 Super Admin: Toàn quyền hệ thống
├── 📊 Content Manager: Quản lý nội dung (từ vựng, câu hỏi)
├── 📈 Analytics Manager: Theo dõi thống kê người dùng
└── 🎮 Game Manager: Quản lý games và achievements
```

### 8.2 Chức Năng Chi Tiết của Admin

#### 📊 **A. Dashboard Tổng Quan**
| Chức năng | Mô tả |
|-----------|--------|
| **Thống kê người dùng** | Tổng số user, user mới/ngày, user active |
| **Doanh thu & Coins** | Tổng coins phát hành, coins đã dùng |
| **Game Analytics** | Số lượt chơi, thời gian chơi trung bình |
| **Progress Metrics** | Tỷ lệ hoàn thành game, điểm trung bình |

#### 👥 **B. Quản Lý Người Dùng**
| Chức năng | Mô tả |
|-----------|--------|
| **Danh sách users** | Xem, tìm kiếm, lọc theo level, XP, streak |
| **Chi tiết user** | Xem profile, tiến độ, lịch sử chơi |
| **Cấm/Khóa tài khoản** | Ban users vi phạm |
| **Reset progress** | Reset tiến độ user (nếu cần) |
| **Gửi thông báo** | Gửi notification đến user |

#### 📚 **C. Quản Lý Từ Vựng (Vocabulary Management)**
| Chức năng | Mô tả |
|-----------|--------|
| **CRUD Vocabulary** | Thêm, sửa, xóa từ vựng |
| **Import bulk** | Import từ vựng từ file CSV/Excel |
| **Phân loại theo topic** | Education, Technology, Health... |
| **Phân loại theo level** | A1, A2, B1, B2, C1, C2 |
| **Audio upload** | Upload file phát âm cho từ |
| **Export data** | Export từ vựng ra file |

#### 🎮 **D. Quản Lý Games**
| Chức năng | Mô tả |
|-----------|--------|
| **CRUD Games** | Thêm, sửa, xóa game |
| **Quản lý câu hỏi** | Thêm, sửa, xóa câu hỏi cho game |
| **Cấu hình game** | Điểm XP, coins reward, difficulty |
| **Preview game** | Xem trước game trước khi publish |
| **Enable/Disable** | Bật/tắt game tạm thời |

#### 📝 **E. Quản Lý Câu Hỏi (Question Bank)**
| Chức năng | Mô tả |
|-----------|--------|
| **Question Editor** | Tạo câu hỏi với nhiều loại (MCQ, fill-blank, matching...) |
| **Tagging** | Gắn tag topic, difficulty |
| **Bulk import** | Import từ file JSON/CSV |
| **AI Generation** | Tạo câu hỏi tự động (GPT integration - optional) |
| **Question validation** | Kiểm tra đáp án đúng/sai |

#### 🏆 **F. Quản Lý Achievements & Rewards**
| Chức năng | Mô tả |
|-----------|--------|
| **CRUD Achievements** | Thêm, sửa, xóa achievement |
| **Cấu hình requirements** | Đặt điều kiện nhận achievement |
| **Phần thưởng** | XP reward, coin reward |
| **Manual award** | Trao thủ công achievement cho user |

#### 📈 **G. Báo Cáo & Analytics**
| Chức năng | Mô tả |
|-----------|--------|
| **User Activity Report** | Biểu đồ user active theo ngày/tuần/tháng |
| **Game Performance** | Game nào được chơi nhiều nhất |
| **Revenue Report** | Coins purchased, coins spent |
| **Learning Progress** | Trung bình tiến độ user |
| **Retention Report** | Tỷ lệ user quay lại |

#### ⚙️ **H. Cấu Hình Hệ Thống**
| Chức năng | Mô tả |
|-----------|--------|
| **XP Rules** | Cấu hình XP earned per action |
| **Level Thresholds** | XP cần để lên level |
| **Daily Limits** | Số game/ngày, coins/ngày |
| **Maintenance Mode** | Bật/tắt chế độ bảo trì |
| **Feature Flags** | Bật/tắt tính năng Beta |

### 8.3 Admin UI Mockup

```
┌─────────────────────────────────────────────────────────────────┐
│  🎮 IELTS Quest Admin                          [🔔] [👤 Admin] │
├──────────┬──────────────────────────────────────────────────────┤
│          │                                                      │
│  📊 Dashboard                                                    │
│  👥 Users     ┌──────────────────────────────────────────────┐  │
│  📚 Vocab     │  Overview                    Today ▼        │  │
│  🎮 Games     ├──────────────────────────────────────────────┤  │
│  📝 Questions │  ┌─────────┐  ┌─────────┐  ┌─────────┐      │  │
│  🏆 Awards    │  │ 1,234   │  │  89     │  │  45.2%  │      │  │
│  📈 Reports   │  │Users    │  │Active   │  │Completion│      │  │
│  ⚙️ Settings  │  └─────────┘  └─────────┘  └─────────┘      │  │
│               │                                              │  │
│               │  📈 User Growth (30 days)                    │  │
│               │  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                  │  │
│               │                                              │  │
│               │  🎮 Popular Games                            │  │
│               │  ┌────────────────────────────────────┐      │  │
│               │  │ Word Match      ████████████  89%  │      │  │
│               │  │ Spelling Bee    █████████░░░  71%  │      │  │
│               │  │ Flash Cards    ███████░░░░░  53%  │      │  │
│               │  └────────────────────────────────────┘      │  │
│               │                                              │  │
└──────────────┴──────────────────────────────────────────────────┘
```

### 8.4 Database Tables cho Admin

```prisma
// ==================== ADMIN & PERMISSIONS ====================
model Admin {
  id        String   @id @default(uuid())
  email     String   @unique
  password  String   // hashed
  name      String
  role      String   @default("content_manager") // super_admin, content_manager, analyst
  createdAt DateTime @default(now())
  
  @@map("admins")
}

model AuditLog {
  id         String   @id @default(uuid())
  adminId    String
  action     String   // "create", "update", "delete"
  entity     String   // "vocabulary", "game", "user"
  entityId   String
  details    Json?
  ipAddress  String?
  createdAt  DateTime @default(now())
  
  @@index([adminId, createdAt])
  @@map("audit_logs")
}
```

---

## 9. Kết Luận & Bước Tiếp Theo

### Tóm tắt ý tưởng
IELTS Quest là một nền tảng web game học tiếng Anh IELTS, kết hợp giữa **giải trí** và **giáo dục**. Với hệ thống mini-games phong phú, người dùng có thể:
- 🎮 Học mà không cảm thấy nhàm chán
- 📈 Theo dõi tiến độ rõ ràng
- 🏆 Nhận phần thưởng và achievement
- 📱 Học mọi lúc mọi nơi (desktop/mobile)

### Bước tiếp theo khuyến nghị
1. **Thảo luận & Feedback** - Bạn muốn điều chỉnh gì?
2. **Chọn Tech Stack** - React hay Next.js? Node hay Python?
3. **Ưu tiên games** - Bạn muốn phát triển games nào trước?
4. **Thiết kế Database** - Cần lưu trữ những gì?
5. **Bắt đầu code** - Setup project & develop MVP!

---

*Bản thiết kế này là điểm khởi đầu. Bạn có thể điều chỉnh, bổ sung hoặc thay đổi bất kỳ phần nào phù hợp với nhu cầu của mình!*
