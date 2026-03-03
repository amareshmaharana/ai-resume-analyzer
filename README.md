# RESUMEScan — AI Resume Analyzer

An AI-powered resume analysis tool that provides detailed feedback, ATS compatibility scoring, and actionable improvement tips to help you land your dream job.

## ✨ Features

- **AI-Powered Analysis** — Analyzes resumes using Claude 3.7 Sonnet to deliver expert-level feedback
- **ATS Compatibility Scoring** — Rates how well your resume performs with Applicant Tracking Systems
- **Multi-Category Evaluation** — Scores across five key areas: ATS, Tone & Style, Content Quality, Structure, and Skills Match
- **Job-Specific Feedback** — Tailors analysis based on the target job title and description you provide
- **PDF Upload with Drag & Drop** — Simple file upload experience with drag-and-drop support
- **Resume History** — View and manage all previously analyzed resumes
- **Cloud Authentication** — Secure sign-in via [Puter](https://puter.com) with cloud-based storage

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| **Framework** | [React Router v7](https://reactrouter.com/) (full-stack with SSR) |
| **UI** | [React 19](https://react.dev/), [Tailwind CSS 4](https://tailwindcss.com/) |
| **Language** | [TypeScript](https://www.typescriptlang.org/) |
| **State Management** | [Zustand](https://zustand.docs.pmnd.rs/) |
| **PDF Processing** | [PDF.js](https://mozilla.github.io/pdf.js/) |
| **File Upload** | [React Dropzone](https://react-dropzone.js.org/) |
| **AI / Backend Services** | [Puter.js](https://docs.puter.com/) (Auth, Storage, KV Store, AI Chat) |
| **Build Tool** | [Vite](https://vite.dev/) |
| **Runtime** | [Node.js 20](https://nodejs.org/) |

## 📁 Project Structure

```
ai-resume-analyzer/
├── app/
│   ├── components/        # Reusable UI components
│   │   ├── Navbar.tsx
│   │   ├── FileUploader.tsx
│   │   ├── ResumeCard.tsx
│   │   ├── ScoreGauge.tsx
│   │   ├── ScoreCircle.tsx
│   │   ├── ScoreBadge.tsx
│   │   ├── Summary.tsx
│   │   ├── ATS.tsx
│   │   ├── Details.tsx
│   │   └── Accordion.tsx
│   ├── lib/
│   │   ├── puter.ts       # Puter.js Zustand store & integration
│   │   ├── pdf2img.ts     # PDF-to-image conversion utility
│   │   └── utils.ts       # Helper functions
│   ├── routes/
│   │   ├── home.tsx       # Dashboard — resume history
│   │   ├── auth.tsx       # Authentication page
│   │   ├── upload.tsx     # Upload & analyze resume
│   │   ├── resume.tsx     # Detailed resume feedback view
│   │   └── wipe.tsx       # Clear all stored resumes
│   ├── routes.ts          # Route definitions
│   ├── root.tsx           # Root layout & error boundary
│   └── app.css            # Global styles
├── constants/
│   └── index.ts           # AI prompt templates & response format
├── types/
│   ├── index.d.ts         # Application TypeScript interfaces
│   └── puter.d.ts         # Puter.js type definitions
├── public/                # Static assets (icons, images, PDF worker)
├── Dockerfile             # Multi-stage production Docker build
├── package.json
├── tsconfig.json
├── vite.config.ts
└── react-router.config.ts
```

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 20 or later
- npm (included with Node.js)

### Installation

```bash
# Clone the repository
git clone https://github.com/amareshmaharana/ai-resume-analyzer.git
cd ai-resume-analyzer

# Install dependencies
npm install
```

### Development

Start the development server with Hot Module Replacement:

```bash
npm run dev
```

The application will be available at `http://localhost:5173`.

### Type Checking

```bash
npm run typecheck
```

## 📦 Building for Production

```bash
npm run build
npm run start
```

The production server will start on port `3000`.

## 🐳 Docker Deployment

Build and run with Docker:

```bash
docker build -t ai-resume-analyzer .
docker run -p 3000:3000 ai-resume-analyzer
```

The containerized application can be deployed to any Docker-compatible platform such as AWS ECS, Google Cloud Run, Azure Container Apps, Fly.io, or Railway.

## 🔄 How It Works

1. **Sign In** — Authenticate via Puter to access your personal dashboard.
2. **Upload Resume** — Upload a PDF resume along with the target company name, job title, and job description.
3. **AI Analysis** — The resume is sent to Claude 3.7 Sonnet, which evaluates it across multiple categories.
4. **Review Feedback** — View your overall score, category breakdowns, and specific tips labeled as strengths or areas for improvement.
5. **Track History** — Access all your previously analyzed resumes from the home dashboard.

## 📊 Scoring Categories

| Category | Description |
|----------|-------------|
| **Overall Score** | Composite score reflecting the resume's overall quality |
| **ATS Compatibility** | How well the resume is optimized for Applicant Tracking Systems |
| **Tone & Style** | Professionalism, clarity, and consistency of language |
| **Content Quality** | Relevance, depth, and impact of the information presented |
| **Structure** | Layout, formatting, and logical organization |
| **Skills Match** | Alignment of listed skills with the target job requirements |

## 🗺 Routes

| Route | Description |
|-------|-------------|
| `/` | Home — resume history dashboard (requires authentication) |
| `/auth` | Sign in / sign out |
| `/upload` | Upload and analyze a resume (requires authentication) |
| `/resume/:id` | View detailed feedback for a specific resume |
| `/wipe` | Clear all stored resume data |

## 🤝 Contributing

Contributions are welcome! To get started:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## 📄 License

This project is open source. See the repository for license details.

---

Built with ❤️ using React Router, Tailwind CSS, and Puter.js
