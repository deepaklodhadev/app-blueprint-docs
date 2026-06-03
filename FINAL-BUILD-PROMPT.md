# 🚀 Complete App Build Prompt

**The Master Prompt to Generate Your Entire App**

Use this prompt with any AI coding tool (ChatGPT, Claude, GitHub Copilot, Cursor, etc.) to generate a complete, production-ready application based on all your documentation.

---

## How to Use This Prompt

1. **Fill out ALL 5 documents first** (PRD, Architecture, Security, Frontend, Tickets)
2. **Copy the template below**
3. **Paste into your AI tool** (ChatGPT, Claude, Cursor, etc.)
4. **Replace all [PLACEHOLDERS]** with content from your documents
5. **Hit generate** and watch your app come to life

---

## 🤖 Master Build Prompt

```
You are an expert full-stack developer with 10+ years of experience building 
production-ready web applications. I am providing you with complete product 
documentation for an app. Your job is to generate clean, well-structured, 
production-ready code that follows all the specifications.

## APP OVERVIEW

[PASTE YOUR PRODUCT VISION FROM PRD]

---

## PRODUCT REQUIREMENTS DOCUMENT (PRD)

### Problem Statement
[PASTE: Problem Statement]

### Target Users
[PASTE: Target User Personas]

### Core Features
[PASTE: Must-Have Features list]

### User Flows
[PASTE: 2-3 key user flows step-by-step]

### Success Metrics
[PASTE: Your success metrics]

---

## TECHNICAL ARCHITECTURE DOCUMENT

### Tech Stack
[PASTE: Your complete tech stack - Frontend, Backend, Database, Hosting]

### File & Folder Structure
[PASTE: Your complete folder structure]

### Database Schema
[PASTE: Your database tables, fields, and relationships]

### Environment Variables
[PASTE: All required environment variables]

### Security Considerations
[PASTE: Your security requirements]

---

## SECURITY & ACCESS DOCUMENT

### Authentication
[PASTE: Your authentication method and requirements]

### User Roles & Permissions
[PASTE: All user roles and their permissions]

### Row-Level Security
[PASTE: Data access rules]

### Error Handling
[PASTE: Error handling for all failure points]

### Edge Cases
[PASTE: Edge cases you need to handle]

---

## FRONTEND SPECIFICATION DOCUMENT

### Color Palette
[PASTE: Your color palette with hex codes]

### Typography
[PASTE: Your fonts, sizes, weights]

### Component Styles
[PASTE: Your button, input, card, modal styles]

### Spacing & Layout
[PASTE: Your spacing scale and layout rules]

### API & Integrations
[PASTE: All external services and API specifications]

---

## FEATURE TICKETS

### Phase 1: MVP (Must-Have)
[PASTE: ALL Phase 1 tickets with descriptions and acceptance criteria]

### Phase 2: Enhancement (Should-Have)
[PASTE: Phase 2 tickets if applicable]

---

## BUILD REQUIREMENTS

Please generate:

1. **Complete Frontend Application**
   - Organized folder structure exactly as specified
   - All pages and components
   - State management (Redux/Context)
   - Forms with validation
   - Error handling and loading states
   - Responsive design (mobile, tablet, desktop)
   - All styling from the design specification
   - Integration with all external APIs

2. **Complete Backend Application**
   - API routes for all features
   - Controllers and services
   - Database integration (Prisma)
   - Authentication middleware
   - Authorization/permissions
   - Input validation
   - Error handling
   - Logging
   - Environment configuration

3. **Database Setup**
   - Prisma schema with all tables
   - Relationships and constraints
   - Migration files

4. **Configuration Files**
   - package.json for both frontend and backend
   - tsconfig.json
   - .env.example files
   - Docker files (if applicable)

5. **Development Setup**
   - Installation instructions
   - How to run locally
   - Database setup steps
   - Environment setup

## CODE QUALITY STANDARDS

- Use TypeScript throughout
- Follow SOLID principles
- DRY (Don't Repeat Yourself)
- Clear variable and function names
- Comments on complex logic
- Proper error handling everywhere
- Input validation on all endpoints
- Security best practices:
  - No secrets in code
  - Password hashing
  - Input sanitization
  - CORS properly configured
  - Rate limiting where needed

## IMPORTANT REQUIREMENTS

✅ MUST implement ALL acceptance criteria from tickets
✅ MUST follow the exact tech stack specified
✅ MUST use the exact folder structure specified
✅ MUST match the design system (colors, typography, spacing)
✅ MUST handle all error cases as specified
✅ MUST implement all user roles and permissions
✅ MUST include database seeds (demo data)
✅ MUST include comprehensive README with setup instructions
✅ MUST be immediately runnable (npm install && npm run dev)
✅ MUST include proper logging and error tracking

## OUTPUT FORMAT

Provide the code in this order:
1. File structure overview
2. Frontend code (main files first, then components)
3. Backend code (setup, routes, controllers, services)
4. Database schema and setup
5. Configuration files
6. Installation and setup instructions

For each file, include:
- Full file path
- Complete code (not snippets)
- Brief comment on purpose

## START GENERATION

Now, please generate the complete application code following all specifications above.
Start with the folder structure, then generate each file in order.
```

---

## 📋 Quick Checklist Before Using This Prompt

- [ ] **PRD document complete** — Problem, users, features, flows defined
- [ ] **Technical Architecture document complete** — Tech stack, database, file structure
- [ ] **Security & Access document complete** — Auth, roles, error handling
- [ ] **Frontend Specification complete** — Colors, typography, components, APIs
- [ ] **Feature Tickets complete** — All tickets with acceptance criteria
- [ ] **All placeholders identified** — Know exactly what to paste
- [ ] **AI tool ready** — Have ChatGPT/Claude/Cursor open

---

## 🎯 Pro Tips

### Tip 1: Use Multiple Prompts
Don't try to generate the entire app in one go. Break it into phases:

**Prompt 1:** Frontend setup + pages
**Prompt 2:** Backend API structure + routes
**Prompt 3:** Database and authentication
**Prompt 4:** Integration with external services

### Tip 2: Iterative Refinement
If the generated code doesn't perfectly match your spec:
1. Point out the difference
2. Show the exact requirement from your docs
3. Ask the AI to fix it

Example:
```
"In my Frontend Specification, I specified the primary color as #1e3a8a. 
The button component is using #2563eb. Please update all components 
to use the exact hex colors from my specification."
```

### Tip 3: Reference by Section
When the AI gets confused, reference your docs:
```
"Per the Feature Tickets document, Ticket 3 requires that users 
cannot see other users' private updates. This is a must-have. 
Please implement row-level security for the updates table."
```

### Tip 4: Ask for Specific Files
If you want one file at a time:
```
"Generate just the updateController.ts file based on:
- The Feature Tickets: [Ticket details]
- The Database Schema: [Schema]
- The Security Rules: [Rules]

Follow the exact format and error handling specified."
```

### Tip 5: Use for Maintenance
Update your documents whenever requirements change, then regenerate:
```
"I've updated my Technical Architecture to use MongoDB instead of PostgreSQL.
Please regenerate the database layer and all database calls."
```

---

## 🔄 Complete App Development Workflow

**Day 1: Documentation**
- [ ] Fill out PRD
- [ ] Fill out Technical Architecture
- [ ] Fill out Security & Access
- [ ] Fill out Frontend Specification
- [ ] Create Feature Tickets

**Day 2: Code Generation**
- [ ] Use Master Build Prompt to generate Phase 1 code
- [ ] Review generated code against specs
- [ ] Ask AI to fix any discrepancies
- [ ] Set up locally and test

**Day 3: Refinement**
- [ ] Test all acceptance criteria
- [ ] Fix bugs found during testing
- [ ] Generate Phase 2 features
- [ ] Repeat until launch-ready

**Day 4+: Enhancement**
- [ ] Update docs as requirements change
- [ ] Regenerate code for changed features
- [ ] Add Phase 2 features
- [ ] Deploy to production

---

## ✅ What You'll Get

**Immediately after generation:**
- ✅ Complete, runnable application
- ✅ All features from PRD implemented
- ✅ Production-ready code structure
- ✅ Proper error handling and validation
- ✅ Database schema and migrations
- ✅ Authentication and authorization
- ✅ Frontend UI matching your design system
- ✅ Setup instructions to run locally

---

## 🎓 Real Example

If you were building TaskFlow, your prompt would include:

```
## PRODUCT REQUIREMENTS

Problem: Remote teams waste 5+ hours per week in status meetings
Target: Engineering managers and team leads
Features:
- User signup/login
- Post daily updates (accomplishments, blockers, next steps)
- View team dashboard with all updates
- Comment on updates
- User profiles

## TECH STACK

Frontend: React 18 + TypeScript + Redux Toolkit + Tailwind CSS
Backend: Node.js + Express + TypeScript + Prisma
Database: PostgreSQL
Auth: Firebase
...

[And so on with all your specifications]

Now generate the complete TaskFlow application...
```

---

## 🆘 If Something Goes Wrong

**AI generated wrong auth method:**
```
"My Security & Access document specifies email/password authentication 
with Firebase. The generated code uses basic auth. Please regenerate 
using Firebase Auth with email verification."
```

**AI missed a feature:**
```
"Per Ticket 5: Comments on Updates, users should be able to edit 
their own comments. This is not in the generated code. 
Please add edit functionality for comments."
```

**Code doesn't match design system:**
```
"My Frontend Specification requires Tailwind CSS with these colors:
Primary: #1e3a8a, Secondary: #f97316
The generated buttons are using default Tailwind blue. 
Please update all components to use my exact color palette."
```

---

## 📚 Next Steps After Code Generation

1. **Run Locally:** Follow setup instructions
2. **Test All Acceptance Criteria:** Go through every feature
3. **Check Error Handling:** Test edge cases
4. **Review Code Quality:** Make sure it's clean and maintainable
5. **Add to Git:** Commit generated code
6. **Deploy:** Push to your hosting platform

---

## 🎯 Remember

- Your documentation is your source of truth
- Always reference your docs when asking AI for changes
- Keep docs in sync with your code
- Update docs as requirements change
- Share docs with your team

---

**You now have everything needed to build production-ready apps without guessing.**

Good luck building! 🚀
