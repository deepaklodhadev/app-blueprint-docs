# Product Requirements Document (PRD)

**Your Complete App Definition**

This document defines what your app does, who uses it, and how they use it. Fill this out before writing a single line of code.

---

## 📌 Executive Summary

Write 2-3 sentences that describe your app in plain English:

```
Example: "TaskFlow is a task management app for remote teams. 
It lets users post daily progress updates instead of attending status meetings. 
Managers get real-time visibility into team progress and blockers."
```

**Your Summary:**

[Write your 2-3 sentence summary here]

---

## 🎯 Problem Statement

### What Problem Does This App Solve?

Describe the problem your users face in their own words. Why does it matter?

```
Example: "Remote teams spend 5+ hours per week in status meetings. 
Most of that time is wasted — people waiting for their turn to speak, 
unclear priorities, and communication that gets lost in Slack."
```

**Your Problem:**

[Describe the real problem here]

### Who Faces This Problem?

List 2-3 types of people affected by this problem:

```
Example:
- Engineering managers at early-stage startups
- Team leads in distributed companies
- Individual contributors tired of meetings
```

**Your Affected Users:**

[List the people affected]

### Why Is It Important?

Why should this problem be solved now? What happens if it stays unsolved?

```
Example: "Teams lose productivity, employees get burnout from meetings, 
and critical project information never gets documented."
```

**Your Importance Statement:**

[Explain why this matters]

---

## 👥 Target Users

### Primary User Persona

Give a vivid description of the main person using your app:

```
Example:
Name: Sarah Chen
Role: Engineering Manager at Series A startup
Age: 32
Tech comfort: High (uses Slack, Jira, GitHub daily)
Goals: See team progress without meetings
Frustrations: Spending 2 hours/day in meetings, unclear blockers
```

**Your Primary Persona:**

Name: [Name]
Role: [Their job title]
Age: [Age range]
Tech comfort: [Low/Medium/High]
Goals: [What they want to accomplish]
Frustrations: [What annoys them]

### Secondary User Persona (if applicable)

If other types of people use your app, describe them:

**Your Secondary Persona:**

[Same format as above]

### How Many Users?

- **Startup phase:** [Estimate for first 3 months]
- **Year 1:** [Estimate by end of year 1]
- **Long-term:** [Where do you want to be?]

---

## 💡 Product Vision

### What Will This App Ultimately Become?

Write 1-2 sentences describing your long-term vision. This is your North Star.

```
Example: "TaskFlow becomes the communication layer for distributed teams, 
replacing status meetings entirely while creating a searchable record of all team progress."
```

**Your Vision:**

[Write your vision here]

### What Are You Deliberately NOT Building in Version 1?

List features that are tempting but out of scope for launch:

```
Example:
- AI-powered blocker detection
- Calendar integration with Outlook
- Custom reporting dashboards
- Mobile app (web-only for v1)
```

**Your Out-of-Scope Items:**

[List what you're deliberately skipping]

---

## 🎁 Core Features

List every feature your app will have. Mark each as **Must-Have** (needed for launch) or **Nice-to-Have** (can wait).

### Must-Have Features (for MVP)

```
Example:
1. User Registration & Login
   - Users sign up with email/password
   - Users can log in and stay logged in

2. Daily Update Posting
   - Team members post text updates on what they accomplished
   - Updates include: completed tasks, blockers, next steps

3. Team Dashboard
   - Managers see all team members' updates in one place
   - Updates are timestamped and show who posted them

4. Comments on Updates
   - Team members can ask questions in comments
   - Comment threads keep conversations organized
```

**Your Must-Have Features:**

1. [Feature name]
   - [What it does]
   - [Key details]

2. [Feature name]
   - [What it does]
   - [Key details]

[Add more as needed]

### Nice-to-Have Features (after launch)

```
Example:
1. Notifications via email or Slack
2. Recurring update templates
3. Team chat feature
4. Mobile app
5. Analytics dashboard
```

**Your Nice-to-Have Features:**

1. [Feature name]
2. [Feature name]
[Add more as needed]

---

## 📊 User Flows

Describe how users move through your app from start to finish. Walk through the most important journeys step-by-step.

### Flow 1: New User Signs Up and Posts First Update

```
Step 1: User lands on homepage
Step 2: User clicks "Sign Up"
Step 3: User enters email, creates password
Step 4: User receives verification email and clicks link
Step 5: User logs in
Step 6: User sees onboarding screen explaining updates
Step 7: User posts first daily update
Step 8: Update appears in their team's dashboard
```

**Your Flow 1:**

[Describe step-by-step]

### Flow 2: Manager Reviews Team Updates

```
Step 1: Manager logs in
Step 2: Manager sees dashboard with all team members' latest updates
Step 3: Manager clicks on a team member's update
Step 4: Manager sees full update with comments
Step 5: Manager adds a comment asking about a blocker
Step 6: Team member sees comment and replies
```

**Your Flow 2:**

[Describe step-by-step]

### Flow 3: [Your Important Flow]

**Your Flow 3:**

[Describe step-by-step]

---

## 🏆 Success Metrics

How do you know this app is working? Define 3-5 concrete metrics:

```
Example:
- 80% of target users adopt the app in first 3 months
- Average team saves 4+ hours per week by reducing meetings
- Daily active users reach 500 by end of year 1
- Net Promoter Score (NPS) above 50
- User retention: 70% of month 1 users still active in month 3
```

**Your Success Metrics:**

1. [Metric name]: [Target]
2. [Metric name]: [Target]
3. [Metric name]: [Target]
4. [Metric name]: [Target]
5. [Metric name]: [Target]

---

## 💰 Business Model (if applicable)

How will this app make money?

```
Example:
- Freemium: Free for up to 5 team members, paid plan for larger teams
- Pricing: $10/user/month
- Projected ARR at 1000 teams: $1.2M
```

**Your Business Model:**

[Describe your monetization strategy]

---

## 📱 MVP Definition

What's the *minimum* you need to ship to get user feedback?

```
Example:
For TaskFlow MVP:
- User authentication (email/password)
- Post daily updates (text only)
- View team dashboard (all updates in one place)
- Comment on updates
- No email notifications (yet)
- No mobile app (yet)
- No advanced features (yet)
```

**Your MVP:**

[List the absolute minimum features needed to launch]

---

## 🎬 Next Steps

1. **Share this document with your team** — Get alignment before building
2. **Use in Technical Architecture doc** — Engineers will design around these features
3. **Reference during development** — Keep the vision clear
4. **Update when things change** — Treat this like code in version control

---

## 🤖 AI Prompt to Generate This Document

Use this prompt with ChatGPT, Claude, or your preferred AI tool:

```
Act as a senior product manager with experience in early-stage startups. 
I am building an app and I need you to create a detailed Product Requirements 
Document for it. The document should cover:

- What the app does and the problem it solves
- Who it is for (target users and personas)
- What problem it solves and why it matters
- All core features with must-have vs nice-to-have classification
- How a user flows through the app from start to finish (3-4 different user journeys)
- What the MVP looks like
- How success will be measured (concrete metrics)
- What we are deliberately NOT building in version one
- Business model/monetization (if applicable)

Write each section in plain English so a non-technical founder can understand it.

My app idea is:

[PASTE YOUR 2-3 SENTENCE APP IDEA HERE]
```

---

## 📝 Notes

- **Keep it concise:** This should be 3-5 pages, not 50
- **Write in plain English:** No jargon. Assume the reader is smart but not technical
- **Be specific:** "Make users happy" is not a metric. "80% of users say they spend 4+ fewer hours in meetings" is
- **Update it:** When your understanding changes, update this document like you'd update code
- **Share it:** Your team should read this before they start building

---

**This document is your product. Get it right, and building is easy.**
