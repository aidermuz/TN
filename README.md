### Prerequisites

**Node version 18.x.x**

### Cloning the repository

```shell
git clone https://github.com/aidermuz/tasknexus_.git
```

### Install packages

```shell
npm i
```

### Setup .env file


```js
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_bGVhZGluZy1hbnQtOTkuY2xlcmsuYWNjb3VudHMuZGV2JA
CLERK_SECRET_KEY=sk_test_0MP4vT70TlcWeHNhAORx5rcEoo7JQbmthcnEprPU9X
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/

DATABASE_URL="postgresql://neondb_owner:amwZedtx9yo8@ep-odd-glitter-a53jr6d1.us-east-2.aws.neon.tech/neondb?sslmode=require"

NEXT_PUBLIC_UNSPLASH_ACCESS_KEY=

STRIPE_API_KEY=

NEXT_PUBLIC_APP_URL=

STRIPE_WEBHOOK_SECRET=
```

### Setup Prisma

Add MySQL Database (I used NeonTech)

```shell
npx prisma generate
npx prisma db push

```

### Start the app

```shell
npm run dev
```
