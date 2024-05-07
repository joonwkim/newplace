This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.


## Prisma 
npm install prisma -D
npm install @prisma/client
npx prisma init

init으로 생성된 schema.prisma File에 provider를 'mongodb'로 변경한다.

.env file을 생성하고 DATABASE_URL MongoDb Atlast Url을 기록한다.

schema.prisma에 data model을 생성한다

## MongoDb 생성
npx prisma db push
npx prisma generate

## Share Prisma Client across the Project
prisma folder에 prisma.ts 생성

import { PrismaClient } from '@prisma/client'

declare global{
   var prisma: PrismaClient | undefined
}
const prisma = global.prisma || new PrismaClient()

if(process.env.NODE_ENV === 'development') global.prisma = prisma

export default prisma

## ERD 생성
Prisma Generate UML Extension 설치

- prisma folder에서 schema.prisma file click
- editor 우측 상단에 Generate Prisma UML 버튼 클릭


