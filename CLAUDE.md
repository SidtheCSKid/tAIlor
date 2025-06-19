# tAllor - AI Resume Tailoring App

## Project Overview
tAllor is an AI-powered resume tailoring application that helps job seekers instantly customize their resumes based on specific job descriptions.

## Key Features
- AI-powered resume tailoring based on job descriptions
- Support for PDF and DOCX resume uploads
- Job description input via text or URL
- One-page resume generation
- Clean, minimal blue-themed UI
- Google OAuth authentication
- PDF preview and download functionality

## Technical Requirements
- **File Support**: PDF and DOCX for existing resumes (required upload)
- **URL Parsing**: Extract job descriptions from any URL
- **Resume Constraint**: All generated resumes must fit on one page
- **Storage**: Unlimited resume storage, job descriptions saved for history
- **Error Handling**: Toast notifications for failures, no card creation on processing errors

## User Flow
1. Google sign-in
2. Dashboard with resume cards grid
3. Floating "New Tailored Resume" button
4. Modal for job description + resume upload
5. AI processing with loading states
6. Resume card with PDF thumbnail
7. Click thumbnail for preview modal
8. Hover for download/delete options

## Development Notes
- No styling customization options
- Indefinite loading states (unknown processing time)
- Specific error messages for URL extraction failures
- Clean, minimal design approach
- refer to the UIUX spec always
- refer to resume best practice md when creating the tailored resume or new resume
- **IMPORTANT**: Follow agentic coding best practices from AGENTIC_CODING_BEST_PRACTICES.md
- Use visual iteration with screenshots for UI development
- Implement test-driven development approach
- Use TodoWrite tool for task tracking and progress management

## Architecture
- Frontend: Next.js 14+ with TypeScript and Tailwind CSS
- Backend: Supabase (PostgreSQL + Auth + Storage + Edge Functions)
- AI Service: Claude API (Anthropic)
- Database: PostgreSQL via Supabase
- File Storage: Supabase Storage
- Deployment: Vercel

## Development Progress

### Phase 1: UI Framework (Tasks 1-12)
- [ ] 1. Set up Next.js project with TypeScript and Tailwind CSS
- [ ] 2. Configure project structure and basic routing
- [ ] 3. Create landing page with sign-in UI (no auth functionality)
- [ ] 4. Build main dashboard layout with navigation
- [ ] 5. Create resume card component with mock data
- [ ] 6. Build floating action button for new resume
- [ ] 7. Create resume creation modal UI
- [ ] 8. Add loading states and shimmer effects
- [ ] 9. Implement PDF preview modal UI
- [ ] 10. Add hover interactions and button overlays
- [ ] 11. Create toast notification system
- [ ] 12. Implement responsive design for mobile/tablet

### Phase 2: Backend Integration (Tasks 13-15)
- [ ] 13. Set up Supabase project and database schema
- [ ] 14. Integrate Google OAuth authentication
- [ ] 15. Connect frontend to Supabase for data persistence

### Phase 3: Core Features (Tasks 16-19)
- [ ] 16. Implement file upload functionality (PDF/DOCX)
- [ ] 17. Build job description URL parsing service
- [ ] 18. Integrate Claude API for resume tailoring
- [ ] 19. Implement PDF generation and thumbnail creation

### Phase 4: Polish & Deploy (Tasks 20-22)
- [ ] 20. Add error handling and user feedback
- [ ] 21. Deploy to Vercel and configure production environment
- [ ] 22. Final testing and bug fixes

## Current Status
**Phase:** 1 (UI Framework)
**Current Task:** Task 1 - Set up Next.js project
**Last Updated:** 2025-06-19

## Commands
```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run type-check   # TypeScript type checking

# Supabase
npx supabase start   # Start local Supabase
npx supabase stop    # Stop local Supabase
npx supabase reset   # Reset local database
npx supabase gen types typescript --local > types/database.types.ts
```