# Feature Ticket List

**Your Build Checklist**

This document breaks down your product into individual tasks. Use these tickets to assign work and track progress. Each ticket is detailed enough to be a direct prompt for an AI coding tool.

---

## 📌 How to Use This Document

**For Teams:**
1. Read through all tickets to understand the project
2. Assign tickets to team members based on dependencies
3. Start with "Must-Have" tickets marked with 🔴
4. Move to "Should-Have" (🟡) after MVP is launched
5. Save "Nice-to-Have" (🟢) for future versions

**For AI Tools:**
Use each ticket as a prompt:
```
"Build [Feature Name] as described in this ticket. 
Follow the Technical Architecture and Frontend Specification documents.
Requirements: [List all acceptance criteria]
Acceptance Criteria:
- [Criterion 1]
- [Criterion 2]
etc."
```

---

## 📋 Ticket Template

Every ticket has the same structure:

```
Ticket #[Number]: [Feature Name]
Priority: [🔴 Must-Have / 🟡 Should-Have / 🟢 Nice-to-Have]

Description:
[What needs to be built and why. 2-3 sentences.]

Acceptance Criteria:
- [Criterion 1: User can...]
- [Criterion 2: System should...]
- [Criterion 3: Error handling...]

Dependencies:
[Other tickets that must be completed first, if any]

Estimated Time: [Your best guess]
```

---

## 🚀 PHASE 1: MVP (Must-Have) - 🔴

### Ticket 1: User Registration
**Priority: 🔴 Must-Have**

**Description:**
New users can create an account using email and password. After sign-up, they receive a verification email. They must verify before they can log in.

**Acceptance Criteria:**
- User can enter email and password on sign-up form
- Password requirements validated: minimum 8 characters, 1 uppercase, 1 number, 1 special character
- User receives verification email within 5 seconds
- Verification link expires after 24 hours
- User can resend verification email if needed
- User cannot log in with unverified email (shows helpful error message)
- Passwords are securely hashed using bcrypt
- Duplicate email accounts are prevented

**Dependencies:**
None (first task)

**Estimated Time:** 4 hours

---

### Ticket 2: User Login
**Priority: 🔴 Must-Have**

**Description:**
Users can log in with their email and password. Session stays active for 30 days. Users can log out and sessions are cleared.

**Acceptance Criteria:**
- User can enter email and password on login form
- Correct credentials: User is logged in and redirected to dashboard
- Incorrect credentials: Show "Email or password is incorrect" (don't reveal if email exists)
- Failed login attempt: Account locks after 5 attempts, unlocks after 15 minutes
- Session expires after 30 days of inactivity
- User can log out and session is cleared
- Logged-in status is stored securely (no sensitive data in local storage)

**Dependencies:**
Ticket 1: User Registration

**Estimated Time:** 3 hours

---

### Ticket 3: Dashboard - View Team Updates
**Priority: 🔴 Must-Have**

**Description:**
After logging in, users see a dashboard showing all team members' latest updates. Updates are displayed in chronological order (newest first). Each update shows who posted it and when.

**Acceptance Criteria:**
- Dashboard loads immediately after login
- All team members' updates visible in a feed
- Each update shows: author name, timestamp, update content
- Updates are sorted by newest first
- Users can scroll to see older updates
- Empty state message shown if no updates posted yet
- Page shows loading spinner while data is being fetched
- Error message shown if dashboard fails to load

**Dependencies:**
Ticket 2: User Login

**Estimated Time:** 3 hours

---

### Ticket 4: Post Daily Update
**Priority: 🔴 Must-Have**

**Description:**
Team members can write and post their daily update. Updates include what they accomplished, blockers, and next steps. Posted updates immediately appear on the team dashboard.

**Acceptance Criteria:**
- User sees a form with text area for updates
- Form has fields: Accomplishments, Blockers, Next Steps
- User can write multi-line text in each field
- Submit button is disabled until at least one field has text
- Clicking submit: Update is saved and appears in dashboard immediately
- Success message shown: "Update posted successfully"
- Update shows the current date and user's name
- Users cannot post completely empty updates
- Validation error shows if form is invalid

**Dependencies:**
Ticket 3: Dashboard - View Team Updates

**Estimated Time:** 4 hours

---

### Ticket 5: Comments on Updates
**Priority: 🔴 Must-Have**

**Description:**
Team members can comment on other team members' updates to ask questions or provide feedback. Comments appear below the update.

**Acceptance Criteria:**
- User can click on an update to view full details and comments
- User sees a text input for adding comments
- Comment submit button is disabled until text is entered
- Clicking submit: Comment is saved and appears immediately
- Comments show author name and timestamp
- Comments are sorted by oldest first
- Users can comment on any team member's update
- Empty comment input shown after submitting
- Error message shown if comment fails to post

**Dependencies:**
Ticket 4: Post Daily Update

**Estimated Time:** 3 hours

---

### Ticket 6: User Profile
**Priority: 🔴 Must-Have**

**Description:**
Users have a profile page where they can view and edit their name, email, and profile picture. Profile information is displayed on updates.

**Acceptance Criteria:**
- User can navigate to their profile page
- Profile shows: name, email, profile picture
- User can edit name field
- User can upload or change profile picture
- Clicking save: Changes are persisted and show immediately
- User cannot change their email (removed from MVP)
- Profile picture is displayed on all their updates in dashboard
- Error message shown if profile update fails
- Show confirmation message: "Profile updated successfully"

**Dependencies:**
Ticket 2: User Login

**Estimated Time:** 3 hours

---

### Ticket 7: Basic Team Management
**Priority: 🔴 Must-Have**

**Description:**
Admin users can create teams and invite team members via email. Team members receive an invitation email and can join.

**Acceptance Criteria:**
- Admin can create a new team with a name
- Admin can invite team members by entering their email address
- Invited users receive email with invitation link
- Invitation link is valid for 7 days
- Clicking invitation link: User joins team (if they have account) or redirected to sign-up
- Team members list shows all people in the team
- Admin can remove team members from team
- Removed members can no longer see team updates
- Error messages for invalid emails or duplicate invitations

**Dependencies:**
Ticket 2: User Login

**Estimated Time:** 5 hours

---

### Ticket 8: Edit & Delete Updates
**Priority: 🔴 Must-Have**

**Description:**
Users can edit their own updates within 24 hours of posting. Users cannot delete updates (only admins can, if needed). Edited updates show "Edited" label with timestamp.

**Acceptance Criteria:**
- User sees an "Edit" button on their own updates only
- Clicking edit: Update text appears in form, user can make changes
- Clicking save: Changes are persisted immediately
- Users can only edit their own updates (no other user's updates)
- Users can only edit updates posted within the last 24 hours
- Edited updates show "Edited [timestamp]" label
- Other users cannot see the edit button on updates
- Attempting to edit after 24 hours: "Edit window has closed" message

**Dependencies:**
Ticket 4: Post Daily Update

**Estimated Time:** 2 hours

---

## 🎯 PHASE 2: Enhancement (Should-Have) - 🟡

### Ticket 9: Email Notifications
**Priority: 🟡 Should-Have**

**Description:**
Users receive optional email notifications when someone comments on their update. Users can toggle notifications on/off in settings.

**Acceptance Criteria:**
- When someone comments on user's update: Email sent within 1 minute
- Email includes: Commenter's name, comment text, link to update
- User can disable notifications in Settings page
- Default: Notifications are ON
- User can choose: All comments or only first comment per day
- Email template is professional and branded
- Users can unsubscribe from emails

**Dependencies:**
Ticket 5: Comments on Updates

**Estimated Time:** 3 hours

---

### Ticket 10: Search Updates
**Priority: 🟡 Should-Have**

**Description:**
Users can search team updates by keyword. Search results show matching updates and highlights search term.

**Acceptance Criteria:**
- Search box appears in top navigation
- User can type keywords to search
- Search results show updates matching the keyword
- Results show: author name, update date, snippet of matching text
- Search is case-insensitive
- Empty results message shown if no matches
- Search works across team (only current team, not other teams)
- Search results load within 2 seconds

**Dependencies:**
Ticket 3: Dashboard - View Team Updates

**Estimated Time:** 3 hours

---

### Ticket 11: Dark Mode
**Priority: 🟡 Should-Have**

**Description:**
App supports dark mode. Users can toggle between light and dark themes in settings. Theme preference is saved and persists across sessions.

**Acceptance Criteria:**
- Settings page has dark mode toggle
- Clicking toggle: All colors switch to dark theme immediately
- Theme is saved to user preferences
- Dark mode persists when user logs back in
- All components (buttons, inputs, cards) have dark mode styles
- Text contrast meets accessibility standards in dark mode
- Images and icons look good in both themes

**Dependencies:**
Ticket 6: User Profile

**Estimated Time:** 2 hours

---

### Ticket 12: Analytics Dashboard
**Priority: 🟡 Should-Have**

**Description:**
Managers can view team analytics: number of daily updates posted, team participation rate, most active team members.

**Acceptance Criteria:**
- Analytics page shows: total updates posted (this week/month/all-time)
- Shows participation rate: % of team posting updates
- Shows most active team members (ranked by updates)
- Shows trends: graph of updates over time
- Data is accurate and updates in real-time
- Managers can filter by date range
- Export analytics to CSV (optional)

**Dependencies:**
Ticket 3: Dashboard - View Team Updates

**Estimated Time:** 5 hours

---

## ✨ PHASE 3: Nice-to-Have - 🟢

### Ticket 13: Mobile App
**Priority: 🟢 Nice-to-Have**

**Description:**
Build native mobile app (iOS/Android) with core functionality: login, view updates, post updates, comments.

**Acceptance Criteria:**
- Available on iOS App Store and Google Play Store
- Core features work: login, updates, comments, dashboard
- Push notifications for comments
- Offline mode: Allow posting updates that sync when online

**Dependencies:**
All Phase 1 tickets

**Estimated Time:** 40+ hours

---

### Ticket 14: AI-Powered Blocker Detection
**Priority: 🟢 Nice-to-Have**

**Description:**
AI analyzes updates to detect potential blockers and highlights them for managers.

**Acceptance Criteria:**
- When user posts update: AI scans for blocker keywords
- Detected blockers are highlighted in dashboard
- Manager can view all blockers across team
- Shows which team member is blocked and by what

**Dependencies:**
Ticket 4: Post Daily Update

**Estimated Time:** 6 hours

---

### Ticket 15: Calendar Integration
**Priority: 🟢 Nice-to-Have**

**Description:**
Integrate with Google Calendar and Outlook. Show team members' calendars and meeting times on dashboard for context.

**Acceptance Criteria:**
- Users can connect their Google Calendar or Outlook
- Dashboard shows team members' busy times
- Updates posted during meetings are highlighted differently
- Helps managers understand when people are available

**Dependencies:**
Ticket 3: Dashboard - View Team Updates

**Estimated Time:** 8 hours

---

## 📊 Dependency Map

```
Ticket 1: User Registration
└── Ticket 2: User Login
    ├── Ticket 3: Dashboard
    │   ├── Ticket 4: Post Update
    │   │   ├── Ticket 5: Comments
    │   │   └── Ticket 8: Edit Updates
    │   ├── Ticket 9: Email Notifications (Ticket 5)
    │   ├── Ticket 10: Search
    │   └── Ticket 12: Analytics
    ├── Ticket 6: User Profile
    │   └── Ticket 11: Dark Mode
    └── Ticket 7: Team Management
```

---

## 🎯 Suggested Build Order

**Week 1:**
1. Ticket 1: User Registration
2. Ticket 2: User Login
3. Ticket 3: Dashboard
4. Ticket 4: Post Update

**Week 2:**
5. Ticket 5: Comments
6. Ticket 8: Edit Updates
7. Ticket 6: User Profile
8. Ticket 7: Team Management

**Week 3:**
9. Polish and testing
10. Launch MVP

**After Launch (Phase 2):**
11. Ticket 9: Email Notifications
12. Ticket 10: Search
13. Ticket 11: Dark Mode
14. Ticket 12: Analytics

---

## 🤖 AI Prompt to Generate This Document

Use this prompt with ChatGPT, Claude, or your preferred AI tool:

```
Act as a senior engineering lead who breaks down products into buildable tasks. 
Based on my PRD, create a complete Feature Ticket List for my app. 

For each feature from the PRD, write a ticket that includes:
- A ticket number
- Feature name
- Clear description (1-2 sentences) of what needs to be built
- Detailed acceptance criteria (5-10 items) that define when task is done
  Each criterion should be testable: "User can...", "System should...", etc.
- Any dependencies on other features that must be completed first
- Estimated time to build (for a single developer)
- Priority label: 🔴 Must-Have for launch, 🟡 Should-Have after launch, 🟢 Nice-to-Have for future

Organize tickets into phases:
- PHASE 1: MVP (Must-have for launch)
- PHASE 2: Enhancement (After launch)
- PHASE 3: Nice-to-Have (Future)

Write each ticket so it can be directly used as a prompt for an AI coding tool (like GitHub Copilot).

My PRD is:

[PASTE YOUR COMPLETE PRD HERE]
```

---

## 📝 Notes

- **Dependencies matter:** Don't start a ticket until its dependencies are done
- **Acceptance criteria are gold:** Clear criteria = clear progress
- **Estimate conservatively:** Most tasks take longer than expected
- **Update as you go:** Mark tickets complete, and check off acceptance criteria
- **Share with team:** Everyone should see the full ticket list

---

**A clear ticket list means everyone knows what to build and when it's done.**
