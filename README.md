# Hostzy - Game Hosting & VPS Website

A modern, responsive website for Hostzy - a premium game hosting, VPS, and bot hosting service provider.

## Features

- **Modern Design**: Beautiful dark/light mode UI with smooth transitions
- **Responsive**: Fully responsive design that works on all devices
- **Fast Performance**: Built with Next.js for optimal performance
- **Dark Mode Support**: Automatic theme detection with manual toggle
- **SEO Optimized**: Complete metadata and structured data
- **Accessibility**: WCAG compliant components

## Tech Stack

- **Framework**: Next.js 14
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **Theme**: next-themes
- **Language**: TypeScript

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Run the development server:
```bash
npm run dev
```

3. Open [http://localhost:3000](http://localhost:3000) in your browser

## Project Structure

```
├── app/
│   ├── layout.tsx          # Root layout with metadata
│   ├── page.tsx            # Home page
│   └── globals.css         # Global styles
├── components/
│   ├── navigation.tsx      # Navigation bar
│   ├── hero.tsx            # Hero section
│   ├── services.tsx        # Services section
│   ├── features.tsx        # Features section
│   ├── pricing.tsx         # Pricing plans
│   ├── testimonials.tsx    # Customer testimonials
│   ├── cta.tsx             # Call-to-action section
│   ├── footer.tsx          # Footer
│   └── theme-provider.tsx  # Theme provider
├── package.json
├── tailwind.config.js
└── tsconfig.json
```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run lint` - Run ESLint

## Sections

1. **Navigation** - Sticky header with theme toggle and mobile menu
2. **Hero** - Eye-catching hero section with CTA buttons
3. **Services** - Four main service offerings
4. **Features** - Key features and benefits
5. **Pricing** - Three-tier pricing plans
6. **Testimonials** - Customer reviews
7. **CTA** - Final call-to-action section
8. **Footer** - Links and contact information

## Customization

### Colors
Edit `tailwind.config.js` to customize the color scheme.

### Content
Update component files in `components/` to modify content and structure.

### Metadata
Edit `app/layout.tsx` to update SEO metadata.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

All rights reserved © 2024 Hostzy
