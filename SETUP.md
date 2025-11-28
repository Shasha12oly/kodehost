# Setup Instructions

## Prerequisites

Before you can run this project, you need to install Node.js and npm.

### Step 1: Install Node.js

1. Download Node.js from [https://nodejs.org/](https://nodejs.org/)
2. Choose the LTS (Long Term Support) version
3. Run the installer and follow the installation wizard
4. Make sure to check "Add to PATH" during installation
5. Restart your terminal/PowerShell after installation

### Step 2: Verify Installation

Open PowerShell and run:
```powershell
node --version
npm --version
```

You should see version numbers for both commands.

## Installation & Running

### Step 1: Navigate to Project Directory

```powershell
cd "C:\Users\Shashank Sharma\Desktop\web"
```

### Step 2: Install Dependencies

```powershell
npm install
```

This will install all required packages including:
- Next.js
- React
- Tailwind CSS
- Lucide React Icons
- next-themes

### Step 3: Run Development Server

```powershell
npm run dev
```

The server will start on `http://localhost:3000`

### Step 4: Open in Browser

Open your web browser and go to:
```
http://localhost:3000
```

## Available Commands

```powershell
# Development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Run linter
npm run lint
```

## Troubleshooting

### npm command not found
- Restart your terminal/PowerShell after installing Node.js
- Verify Node.js is in your PATH

### Port 3000 already in use
- The development server will automatically try port 3001, 3002, etc.
- Or kill the process using port 3000

### Module not found errors
- Delete `node_modules` folder and `.next` folder
- Run `npm install` again

## Project Structure

```
web/
├── app/                    # Next.js app directory
│   ├── layout.tsx         # Root layout
│   ├── page.tsx           # Home page
│   └── globals.css        # Global styles
├── components/            # React components
│   ├── navigation.tsx
│   ├── hero.tsx
│   ├── services.tsx
│   ├── features.tsx
│   ├── pricing.tsx
│   ├── testimonials.tsx
│   ├── cta.tsx
│   ├── footer.tsx
│   └── theme-provider.tsx
├── package.json           # Dependencies
├── tailwind.config.js     # Tailwind configuration
├── tsconfig.json          # TypeScript configuration
├── next.config.js         # Next.js configuration
└── README.md              # Project documentation
```

## Features

✅ Modern, responsive design
✅ Dark/Light mode support
✅ SEO optimized
✅ Fast performance with Next.js
✅ Beautiful UI with Tailwind CSS
✅ Icon library with Lucide React
✅ Mobile-friendly navigation
✅ Smooth animations and transitions

## Support

For issues or questions, refer to:
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [React Documentation](https://react.dev)
