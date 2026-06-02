# Joey Bae's Digital Portfolio

Welcome to the repository for my digital portfolio. This website showcases my projects, professional experience, technical skills, and background spanning software engineering, data science, AI automation, and graphic design.

The portfolio is built as a highly responsive, modern single-page application using **Next.js**, **React**, and **Tailwind CSS**, and is set up for automatic deployment to **GitHub Pages**.

---

## 🚀 Live Site
Check out the live portfolio: **[joeyb-portfolio](https://joeybae.github.io/joeyb-portfolio)** *(or your configured GitHub Pages URL)*

---

## 🛠️ Tech Stack & Tools (Why This Architecture?)

To build a modern, high-performance, and cost-effective portfolio, the following tech stack was chosen:

*   **Next.js 16 (App Router)**: Chosen for its modern react capabilities and robust static site generation (`output: "export"`), allowing hosting on free static platforms (GitHub Pages) while maintaining excellent load times and SEO.
*   **React 19 & TypeScript**: Provides strict type safety, modular UI components (reusable cards, custom buttons), and helps write predictable front-end state management.
*   **Tailwind CSS v4 & PostCSS**: Used to build a responsive, custom dark-mode portfolio with modern styling tokens (like custom grids and premium gradients) without writing excessive CSS.
*   **Web3Forms API**: Enables direct, secure contact form submissions without requiring a separate backend database or API routes, keeping the site 100% serverless, fast, and secure.
*   **GitHub Actions (CI/CD) & GitHub Pages**: Implements a pipeline where pushing code to the `main` branch automatically triggers static export and deploys the site, ensuring zero-downtime and automated updates.

---

## ✨ Features

- **Dynamic Navigation & Smooth Scrolling**: Seamless scrolling navigation between section anchors (`#skills`, `#projects`, `#experiences`, `#contact`).
- **Interactive Skills Section**: Dynamic grids displaying grayscale tech logos that light up and zoom on hover.
- **Projects Showcase**: Customized grid components featuring selected works (e.g., AI Dungeon Master Assistant, Automated Content Pipeline, and Predictive Market Models).
- **Interactive Experience Timeline**: Structured and rich details of professional roles (Liberty University Research Assistant, Trans World Radio Intern) with relevant skill badges.
- **Working Contact Form**: Integrates directly with Web3Forms API to send messages straight to inbox.
- **Dark Mode Aesthetics**: Sleek dark theme featuring premium mint-yellow gradients, custom-styled buttons, and glassmorphism.

---

## 📂 Project Structure

```text
joeyb-portfolio/
├── .github/workflows/   # CI/CD configs
│   └── deploy.yml       # Automates build and deploy to GitHub Pages
├── app/
│   ├── globals.css      # Custom Tailwind imports & utility styles
│   ├── layout.tsx       # Root layout containing Navbar, Footer, and viewport setups
│   └── page.tsx         # Single Page application layout containing all sections
├── components/
│   ├── ui/
│   │   ├── button.tsx         # Global button component
│   │   ├── experienceCard.tsx # Experience card/timeline component
│   │   └── projectCard.tsx    # Showcase project card component
│   ├── footer.tsx       # Global website footer
│   └── navbar.tsx       # Header with smooth-scroll section anchors
├── sections/
│   ├── hero.tsx         # Welcome banner, resume download, profile picture
│   ├── skills.tsx       # Grayscale-to-color skills grid
│   ├── projects.tsx     # Custom project mapping
│   ├── experiences.tsx  # Work experience listings
│   └── contact.tsx      # Contact form connected to Web3Forms API
├── public/
│   ├── image/           # Images and SVG logos
│   └── JoeyBae_SWEngineer_2026.pdf # Resume PDF
├── next.config.ts       # Next.js configurations (includes static export configurations)
├── package.json         # Project dependencies & scripts
└── tsconfig.json        # TypeScript configurations
```

---

## ⚙️ Configuration & Setup

### Environment Variables

The contact form uses a Web3Forms access key. To configure it, create a `.env.local` file in the root directory:

```bash
NEXT_PUBLIC_WEB3FORMS_ACCESS_KEY=your_web3forms_access_key_here
```

### GitHub Pages Settings (`next.config.ts`)

To allow Next.js to export static files and host them properly under GitHub Pages subpaths:
- `output: "export"` (configured for static exports)
- `images.unoptimized: true` (disables Next.js default image optimization, which requires a Node server)
- `basePath: "/joeyb-portfolio"` (prefixes asset links with the repository name)

---

## 💻 Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/joeybae/joeyb-portfolio.git
   cd joeyb-portfolio
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the development server:**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) with your browser to view it.

4. **Linting:**
   ```bash
   npm run lint
   ```

---

## 📦 Build & Deployment

### Manual Static Build
To build and export the site locally into a static `./out` folder:
```bash
npm run build
```

### Automated GitHub Pages Deployment
This repository is configured with a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automatically builds and deploys the site whenever changes are pushed to the `main` branch:

1. Code is checked out and built statically (`npm run build`).
2. The `./out` directory is bundled and uploaded as a GitHub Pages artifact.
3. The bundle is deployed live on GitHub Pages.

---

## 📄 License
This project is open-source. Feel free to clone or customize it for your own portfolio.
