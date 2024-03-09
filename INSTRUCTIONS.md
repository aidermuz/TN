# Environment Setup

- Next.js 14.0.1
npx create-next-app@14.0.1 antonio-trello-clone

```
√ Would you like to use TypeScript? Yes
√ Would you like to use ESLint? Yes
√ Would you like to use Tailwind CSS? Yes
√ Would you like to use `src/` directory? No
√ Would you like to use App Router? (recommended) Yes
√ Would you like to customize the default import alias (@/\*)? No
```
`cd antonio-trello-clone`

`npx shadcn-ui@latest init`
```
√ Would you like to use TypeScript (recommended)? ... yes
√ Which style would you like to use? » Default
√ Which color would you like to use as base color? » Neutral
√ Where is your global CSS file? ... app/globals.css
√ Would you like to use CSS variables for colors? ... yes
√ Where is your tailwind.config.js located? ... tailwind.config.ts
√ Configure the import alias for components: ... @/components
√ Configure the import alias for utils: ... @/lib/utils
√ Are you using React Server Components? ... yes
√ Write configuration to components.json. Proceed? ... yes
```

`npm run dev`

# Folders Setup

...

# Marketing

npx shadcn-ui@latest add button

# Authentication

Clerk setup: https://clerk.com/ - login - add application 
```
application name: antonio-trello 
turn off email address
create application
copy API KEYS to .env
.gitignore .env
npm i @clerk/nextjs
```

.env 
```
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY= 
CLERK_SECRET_KEY= 
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in 
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up 
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/ 
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/
```

# Organizations

Clerk dashboard: https://dashboard.clerk.com/ - Organizations - "Enable"

# Sidebar

```
npm i usehooks-ts zustand`
npx shadcn-ui@latest add accordion skeleton separator sheet
```

# Settings

...

# Server Actions

NeonDB: https://neon.tech/ - login - create service

```
npm i -D prisma
npx prisma init
npx prisma generate
npx prisma db push
npx prisma studio
.
npx shadcn-ui@latest add input
npm i zod
```

.env 
```
DATABASE_URL=
```

.package.json
```
"scripts": {
    "postinstall": "prisma generate"
  },
```


# Use Action (error log)

...

# Form Components

`npx shadcn-ui@latest add label`

# Form Popover

```
npm i sonner
npx shadcn-ui@latest add popover tooltip
```

# Create Board

Unsplash
```
npm i unsplash-js
unsplash.com/developer - register
https://unsplash.com/oauth/applications - create application
copy Access Key
```

.env
```
NEXT_PUBLIC_UNSPLASH_ACCESS_KEY=
```

```
npx prisma migrate reset
npx prisma db push
npx prisma generate
```

# Board List 

...

# Board Page

```
npm i lodash
npm i -D @types/lodash
```

# List Form

```
npx prisma migrate reset
npx prisma db push
npx prisma generate
npx prisma studio - "view list"
```

# List Header

...

# List Options

...

# Card Form

`npx shadcn-ui@latest add textarea`

# Drag and Drop

```
npm i @hello-pangea/dnd
```

# Card Modal

```
npx shadcn-ui@latest add dialog
npm i @tanstack/react-query
```

# Card Actions

...

# Activity

```
npm i date-fns
npx shadcn-ui@latest add avatar
npx prisma db push
npx prisma generate
```

# Stripe

```
npx prisma db push
npx prisma generate
``` 

Stripe API KEY & Webhook
```
npm i stripe
stripe.com - login - create store "antonio-trello"
click developers tab
api keys - copy secret key to .env
.
webhooks - "test in local environment"
download & open stripe cli - visit link - allow access
run stripe listen --forward-to localhost:3000/api/webhook
copy webhook signing secret to .env
.
stripe.com - search "billing portal" - customer portal
click "activate test link"
validate Billing - "Manage Billing" show "Stripe Plan"
```

Stripe Payment
```
Card Information: 4242*
Cardholder name: a
click "Pay and subscribe"
show "200" requests
validate OrgSubscription in "npx prisma studio"
validate "create new board unlimited"
validate can create new board
validate Billing - "Manage Billing" show "Stripe Plan"
```

.env
```
NEXT_PUBLIC_APP_URL=http://localhost:3000
STRIPE_API_KEY=
STRIPE_WEBHOOK_SECRET=
```

Webhook production
```
stripe.com - login - developers tab - "add endpoint"
copy vercel endpoint to stripe "endpoint url" + "api/webhook/
select events - checkout.session.completed & invoice.payment.succeeded
click "add events" - "add endpoint"
click "reveal signing secret" - copy to vercel env vars
copy endpoint url to vercel env var NEXT_PUBLIC_APP_URL + remove "/" at end
```

# Deployment

foreach
```
git add .
git commit -m "XX: message"
git push
validate deployment succeed
```

once
```
github.com/new - name "antonio-trello" - create repo
use second option - "push an existing repo"
.
vercel.com/new - import "antonio-trello" - deploy
settings - environment variables - add from .env
```