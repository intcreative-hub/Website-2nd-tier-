# Service Business Template - $500 Tier Website

A modern, professional website template built with Next.js 15, React 18, and TypeScript. Features beautiful animations, a working contact form, and SEO optimization. Perfect for service-based businesses.

## 🚀 Features

- **4 Complete Pages**: Home, Services, About, Contact
- **Modern Tech Stack**: Next.js 15, React 18, TypeScript, Tailwind CSS
- **Beautiful Animations**: Framer Motion animations and 3D effects
- **Functional Contact Form**: With validation and API integration
- **SEO Optimized**: Meta tags, sitemap.xml, robots.txt, structured data
- **Fully Responsive**: Works perfectly on all devices
- **Easy Customization**: Single content.ts file for all site content
- **Docker Ready**: Includes Docker configuration for easy deployment
- **Production Ready**: Optimized build with excellent performance

## 📋 Quick Start

### Prerequisites

- Node.js 18+ and npm installed
- Git installed

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd Website-2nd-tier-
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Customize your content**
   - Open `/lib/content.ts`
   - Update all the configuration values (see Customization Guide below)

4. **Run development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   - Navigate to [http://localhost:3000](http://localhost:3000)

## 🎨 Customization Guide

All website content can be customized by editing `/lib/content.ts`. Here's what you can change:

### 1. Branding & Colors

\`\`\`typescript
export const BRANDING = {
  primaryColor: {
    hex: "#10b981",      // Change to your brand color
    tailwind: "emerald",
  },
  secondaryColor: {
    hex: "#a855f7",      // Change to your secondary color
    tailwind: "purple",
  },
  logo: "/logo-placeholder.svg",  // Replace with your logo path
};
\`\`\`

### 2. Site Configuration

\`\`\`typescript
export const SITE_CONFIG = {
  name: "Your Business Name",              // Your company name
  tagline: "Your tagline here",            // Your tagline/slogan
  phone: "(555) 123-4567",                 // Your phone number
  email: "hello@yourbusiness.com",         // Your email
  address: "123 Main St, City, ST 12345",  // Your address
  mapsEmbedUrl: "...",                     // Your Google Maps embed URL
  googleMapsLink: "...",                   // Your Google Maps link
  website: "https://yourbusiness.com",     // Your website URL
};
\`\`\`

### 3. Business Hours

\`\`\`typescript
export const BUSINESS_HOURS = {
  weekday: "Monday - Friday, 9:00 AM - 6:00 PM",
  weekend: "Saturday, 10:00 AM - 4:00 PM",
  closed: "Sunday - Closed",
};
\`\`\`

### 4. Services

Update the \`SERVICES\` array with your actual services:

\`\`\`typescript
export const SERVICES = [
  {
    id: "your-service",
    title: "Your Service Name",
    description: "Description of your service",
    icon: "Briefcase",  // Options: Briefcase, TrendingUp, Palette, Code
    features: ["Feature 1", "Feature 2", "Feature 3", "Feature 4"],
    gradient: "from-purple-600 via-purple-500 to-emerald-500",
  },
  // Add more services...
];
\`\`\`

## 📧 Contact Form Setup

The contact form is functional but needs email service integration for production use.

### Current Setup (Development)
- Form submissions are logged to console
- Returns success message to user
- No actual emails sent

### Production Setup

1. **Choose an email service:**
   - [Resend](https://resend.com) - Recommended, easy setup
   - [SendGrid](https://sendgrid.com) - Popular choice
   - [AWS SES](https://aws.amazon.com/ses/) - Enterprise option
   - Nodemailer with SMTP

2. **Install the package** (example with Resend):
   ```bash
   npm install resend
   ```

3. **Add environment variable:**
   ```bash
   # Create .env.local
   RESEND_API_KEY=your_api_key_here
   ```

4. **Update \`/app/api/contact/route.ts\`:**
   - Uncomment the email service code
   - Add your configuration

Example Resend integration is already commented in the code!

## 🌐 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import your repository
4. Add environment variables (if using email service)
5. Deploy!

### Docker

\`\`\`bash
# Build the image
docker build -t service-business-template .

# Run the container
docker run -p 3000:3000 service-business-template
\`\`\`

### Docker Compose

\`\`\`bash
docker-compose up
\`\`\`

## 🛠️ Development Commands

\`\`\`bash
# Development server
npm run dev

# Production build
npm run build

# Start production server
npm run start

# Lint code
npm run lint
\`\`\`

## 📁 Project Structure

\`\`\`
├── app/
│   ├── (pages)/
│   │   ├── about/page.tsx
│   │   ├── contact/page.tsx
│   │   └── services/page.tsx
│   ├── api/
│   │   └── contact/route.ts
│   ├── layout.tsx
│   ├── page.tsx
│   ├── robots.ts
│   └── sitemap.ts
├── components/
│   ├── ContactForm.tsx
│   ├── FAQ.tsx
│   ├── Footer.tsx
│   ├── Header.tsx
│   ├── Hero.tsx
│   ├── HoursLocation.tsx
│   ├── SocialProof.tsx
│   ├── WhatWeOffer.tsx
│   └── WhyChooseUs.tsx
├── lib/
│   └── content.ts          # ⭐ Main customization file
└── public/
    └── (static assets)
\`\`\`

## 🎯 SEO Features

- ✅ Meta tags (title, description, keywords)
- ✅ Open Graph tags (social media sharing)
- ✅ Twitter Card tags
- ✅ Structured data (JSON-LD)
- ✅ Sitemap.xml (auto-generated)
- ✅ Robots.txt (auto-generated)
- ✅ Semantic HTML5
- ✅ Fast page load times
- ✅ Mobile-responsive

## 🎨 Styling

- **Framework**: Tailwind CSS
- **Animations**: Framer Motion
- **3D Effects**: Custom CSS/JS
- **Icons**: Lucide React

## 🔧 Advanced Customization

### Adding New Pages

1. Create new folder in \`/app/\` (e.g., \`/app/blog/\`)
2. Add \`page.tsx\` file
3. Use existing pages as templates
4. Update \`/lib/content.ts\` NAV_LINKS

### Changing Fonts

Edit \`/app/layout.tsx\`:
\`\`\`typescript
import { YourFont } from "next/font/google";

const yourFont = YourFont({
  subsets: ["latin"],
  display: "swap",
  variable: "--font-your-font",
});
\`\`\`

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📝 License

This is a commercial template created for INT Creative clients.

## 🆘 Support

For support or customization requests:
- Email: hello@intcreative.co
- Website: [intcreative.co](https://intcreative.co)

## 🎉 Credits

Built with:
- [Next.js](https://nextjs.org)
- [React](https://react.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [Framer Motion](https://www.framer.com/motion/)
- [Lucide Icons](https://lucide.dev)

---

**Built by [INT Creative](https://intcreative.co)** - Professional web development services
