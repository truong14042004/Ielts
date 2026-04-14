# 🔌 Hướng Dẫn Setup Vercel Postgres

## Bước 1: Tạo Database trên Vercel

### Cách 1: Qua Vercel Dashboard (Khuyến nghị)

1. **Truy cập Vercel Dashboard**
   - Đăng nhập: https://vercel.com
   - Click **"Add New..."** → **"Database"**

2. **Chọn PostgreSQL**
   - Chọn **PostgreSQL** (được hỗ trợ native bởi Vercel)

3. **Cấu hình Database**
   ```
   - Region: Singapore (ap-southeast-1) - gần Việt Nam nhất
   - Environment: Production
   - Type: Free ( Hobby )
   ```

4. **Đợi khởi tạo** (~1-2 phút)
   - Vercel sẽ tự động tạo database và cung cấp connection URL

5. **Copy Connection URL**
   - Sau khi tạo xong, copy `POSTGRES_URL` từ tab **".env.local"**

---

### Cách 2: Qua Vercel CLI

```bash
# Cài đặt Vercel CLI (nếu chưa có)
npm i -g vercel

# Login Vercel
vercel login

# Link project
vercel link

# Thêm Database
vercel add postgres

# Pull environment variables về local
vercel env pull .env.local
```

---

## Bước 2: Cấu hình trong Project

### 1. Tạo file `.env.local`

```env
# Database Connection (từ Vercel Dashboard)
POSTGRES_URL=postgresql://default:xxx@xyz.aws.neon.tech/neondb?sslmode=require
POSTGRES_PRISMA_URL=postgresql://default:xxx@xyz.aws.neon.tech/neondb?sslmode=require&pgmatic=false
POSTGRES_URL_NON_POOLING=postgresql://default:xxx@xyz.aws.neon.tech/neondb?sslmode=require
POSTGRES_USER=default
POSTGRES_HOST=xyz.aws.neon.tech
POSTGRES_PASSWORD=xxx
POSTGRES_DATABASE=neondb

# NextAuth
NEXTAUTH_SECRET=your-super-secret-key-here-generate-with-openssl
NEXTAUTH_URL=http://localhost:3000
```

### 2. Cập nhật `next.config.js`

```javascript
// next.config.js
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    serverComponentsExternalPackages: ['@prisma/client'],
  },
}

module.exports = nextConfig
```

---

## Bước 3: Cài đặt Prisma

```bash
# Di chuyển vào thư mục project
cd ielts-quest

# Cài đặt Prisma dependencies
npm install prisma @prisma/client

# Khởi tạo Prisma
npx prisma init
```

---

## Bước 4: Tạo Prisma Schema

### Tạo file `prisma/schema.prisma`:

```prisma
// prisma/schema.prisma

generator client {
  provider        = "prisma-client-js"
  previewFeatures = ["postgresqlExtensions"]
}

datasource db {
  provider = "postgresql"
  url      = env("POSTGRES_URL")
  extensions = [pg_trgm, citext]
}

// ==================== USER & AUTH ====================
model User {
  id            String    @id @default(uuid())
  email         String    @unique
  username      String    @unique
  password      String
  avatar        String?
  level         Int       @default(1)
  xp            Int       @default(0)
  coins         Int       @default(0)
  streakDays    Int       @default(0)
  lastPlayedAt  DateTime?
  createdAt     DateTime  @default(now())
  updatedAt     DateTime  @updatedAt

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
  slug        String   @unique
  category    String
  description String?
  icon        String?
  difficulty  Int      @default(1)
  xpReward    Int      @default(10)
  coinReward  Int      @default(5)
  createdAt   DateTime @default(now())

  progress    UserProgress[]
  history     GameHistory[]
  questions   GameQuestion[]

  @@map("games")
}

model GameQuestion {
  id         String   @id @default(uuid())
  gameId     String
  game       Game     @relation(fields: [gameId], references: [id])
  type       String
  content    Json
  difficulty Int      @default(1)
  createdAt  DateTime @default(now())

  @@map("game_questions")
}

// ==================== VOCABULARY ====================
model Vocabulary {
  id             String   @id @default(uuid())
  word           String
  pronunciation  String?
  partOfSpeech   String?
  meaning        String
  example        String?
  exampleMeaning String?
  audioUrl       String?
  topic          String
  level          String   @default("A2")
  createdAt      DateTime @default(now())

  progress VocabularyProgress[]

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
  stars       Int      @default(0)
  timesPlayed Int      @default(0)
  bestTime    Int?
  updatedAt   DateTime @updatedAt

  @@unique([userId, gameId])
  @@map("user_progress")
}

model VocabularyProgress {
  id         String     @id @default(uuid())
  userId     String
  vocabId    String
  vocabulary Vocabulary @relation(fields: [vocabId], references: [id])
  correct    Int        @default(0)
  incorrect  Int        @default(0)
  lastTested DateTime?
  mastered   Boolean    @default(false)
  updatedAt  DateTime   @updatedAt

  @@unique([userId, vocabId])
  @@map("vocabulary_progress")
}

model GameHistory {
  id           String   @id @default(uuid())
  userId       String
  gameId       String
  game         Game     @relation(fields: [gameId], references: [id])
  score        Int
  correct      Int
  incorrect    Int
  timeSpent    Int
  xpEarned     Int
  coinsEarned  Int
  playedAt     DateTime @default(now())

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
  category    String
  requirement Json
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
  period    String
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

## Bước 5: Tạo Database Client

### Tạo file `src/lib/prisma.ts`:

```typescript
// src/lib/prisma.ts
import { PrismaClient } from '@prisma/client'

const globalForPrisma = globalThis as unknown as {
  prisma: PrismaClient | undefined
}

export const prisma =
  globalForPrisma.prisma ??
  new PrismaClient({
    log: process.env.NODE_ENV === 'development' ? ['query', 'error', 'warn'] : ['error'],
  })

if (process.env.NODE_ENV !== 'production') globalForPrisma.prisma = prisma

export default prisma
```

---

## Bước 6: Push Database Schema

### Development (Local)
```bash
# Generate Prisma Client
npx prisma generate

# Push schema lên Vercel Postgres
npx prisma db push

# Hoặc tạo migration
npx prisma migrate dev --name init
```

### Production (Sau khi deploy)
```bash
# Deploy migrations
npx prisma migrate deploy
```

---

## Bước 7: Seed Data (Optional)

### Tạo file `prisma/seed.ts`:

```typescript
// prisma/seed.ts
import { PrismaClient } from '@prisma/client'

const prisma = new PrismaClient()

async function main() {
  // Seed Vocabularies
  const vocabularies = [
    {
      word: 'abundant',
      pronunciation: '/əˈbʌndənt/',
      partOfSpeech: 'adjective',
      meaning: 'dồi dào, phong phú',
      example: 'The region has abundant natural resources.',
      exampleMeaning: 'Vùng này có nguồn tài nguyên thiên nhiên dồi dào.',
      topic: 'environment',
      level: 'B1',
    },
    {
      word: 'accumulate',
      pronunciation: '/əˈkjuːmjuleɪt/',
      partOfSpeech: 'verb',
      meaning: 'tích lũy, tập trung',
      example: 'Students accumulate knowledge over time.',
      exampleMeaning: 'Học sinh tích lũy kiến thức theo thời gian.',
      topic: 'education',
      level: 'B1',
    },
    // Thêm more...
  ]

  for (const vocab of vocabularies) {
    await prisma.vocabulary.upsert({
      where: { word_topic: { word: vocab.word, topic: vocab.topic } },
      update: {},
      create: vocab,
    })
  }

  console.log('Seed completed!')
}

main()
  .catch((e) => {
    console.error(e)
    process.exit(1)
  })
  .finally(async () => {
    await prisma.$disconnect()
  })
```

### Thêm script vào `package.json`:

```json
{
  "scripts": {
    "db:push": "prisma db push",
    "db:studio": "prisma studio",
    "db:seed": "ts-node --compiler-options {\"module\":\"CommonJS\"} prisma/seed.ts",
    "db:generate": "prisma generate"
  },
  "prisma": {
    "seed": "ts-node --compiler-options {\"module\":\"CommonJS\"} prisma/seed.ts"
  }
}
```

### Chạy seed:
```bash
npm run db:seed
```

---

## Bước 8: Deploy lên Vercel

```bash
# Commit changes
git add .
git commit -m "Setup Prisma with Vercel Postgres"

# Push lên GitHub
git push origin main

# Vercel sẽ tự động deploy và lấy environment variables từ dashboard
```

---

## Troubleshooting

### Lỗi "Cannot find module '@prisma/client'"
```bash
npm install @prisma/client
npx prisma generate
```

### Lỗi "Connection refused"
- Kiểm tra `POSTGRES_URL` trong Vercel Dashboard
- Đảm bảo có `?sslmode=require` ở cuối URL

### Lỗi "Table does not exist"
```bash
# Chạy lại migrate
npx prisma db push --force-reset
```

### Kiểm tra Database trong Vercel
- Vào **Storage** → **Database** → **"Query"** (Neon)
- Hoặc dùng Prisma Studio: `npx prisma studio`

---

## 📁 Files cần có sau khi setup:

```
ielts-quest/
├── prisma/
│   ├── schema.prisma      # Database schema
│   └── seed.ts            # Seed data (optional)
├── src/
│   └── lib/
│       └── prisma.ts      # Prisma client singleton
├── .env.local             # Environment variables (local)
├── next.config.js
└── package.json
```

---

## 🔗 Resources

- [Vercel Postgres Documentation](https://vercel.com/docs/storage/vercel-postgres)
- [Prisma Documentation](https://prisma.io/docs)
- [Neon (PostgreSQL provider)](https://neon.tech)

---

⭐ **Hoàn thành!** Bây giờ bạn có thể bắt đầu code các tính năng của IELTS Quest!
