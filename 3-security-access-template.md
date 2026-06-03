# Security & Access Document

**User Roles, Permissions, Error Handling, and Edge Cases**

This document defines who can do what inside your app, how you authenticate users, and what happens when things go wrong.

---

## 📌 Overview

Describe your security approach in one paragraph:

```
Example: "TaskFlow uses email/password authentication with optional 2FA for admins. 
Users are organized into teams with role-based access control. Admins manage users, 
Team Leads see all team updates, Team Members see only their own updates. 
All data is encrypted at rest and in transit."
```

**Your Overview:**

[Write your security approach]

---

## 🔐 Authentication Method

How do users log in?

### Primary Authentication

```
Example:
- Method: Email + Password
- Password Requirements:
  - Minimum 8 characters
  - At least 1 uppercase letter
  - At least 1 number
  - At least 1 special character
- Hash Algorithm: bcrypt with salt rounds = 10
- Session Duration: 30 days (with option to remember device)
- Password Reset: Email verification link, valid for 1 hour
```

**Your Primary Auth:**

- Method: [Email/password, OAuth, SSO, Magic link, etc.]
- Password Requirements: [If applicable]
- Session Duration: [How long users stay logged in]
- Password Reset: [How does it work?]

### Secondary Authentication (Optional)

```
Example:
- Two-Factor Authentication (2FA) for Admin users
- Method: TOTP via authenticator app (Google Authenticator, Authy)
- Backup codes: 10 single-use backup codes provided at setup
- Enforcement: Required for admins, optional for others
```

**Your Secondary Auth:**

[If you have 2FA or other secondary methods]

### Third-Party Authentication (Optional)

```
Example:
- Google OAuth for faster sign-up
- GitHub OAuth for developers
- Microsoft SSO for enterprise customers
```

**Your Third-Party Auth:**

[If allowing social login or SSO]

---

## 👥 User Roles & Permissions

Define every type of user and exactly what they can access.

### Role 1: Admin

```
Example:
Permissions:
✅ Create new teams
✅ Manage all users (invite, remove, change roles)
✅ View all updates from all teams
✅ Delete any update (if violation of policy)
✅ View billing and payments
✅ Change team settings
✅ Enable/disable features

Restrictions:
❌ Cannot delete user accounts (only deactivate)
❌ Cannot change other admin passwords (only their own)
❌ Cannot access database directly
```

**Your Admin Role:**

What admins CAN do:
- [Permission]
- [Permission]

What admins CANNOT do:
- [Restriction]
- [Restriction]

### Role 2: Team Lead

```
Example:
Permissions:
✅ View all team members' updates
✅ Comment on any team member's update
✅ Invite new team members to team
✅ Remove team members from team
✅ Post their own updates
✅ View team analytics and reports

Restrictions:
❌ Cannot change team settings
❌ Cannot delete updates
❌ Cannot manage billing
❌ Cannot see other teams' data
```

**Your Team Lead Role:**

What Team Leads CAN do:
- [Permission]
- [Permission]

What Team Leads CANNOT do:
- [Restriction]
- [Restriction]

### Role 3: Team Member

```
Example:
Permissions:
✅ Post their own daily updates
✅ Edit their own updates (within 24 hours)
✅ Comment on any team member's update
✅ View all team members' updates
✅ View team dashboard
✅ Update their own profile

Restrictions:
❌ Cannot delete updates (only edit)
❌ Cannot invite other users
❌ Cannot access team settings
❌ Cannot see billing or admin functions
```

**Your Team Member Role:**

What Team Members CAN do:
- [Permission]
- [Permission]

What Team Members CANNOT do:
- [Restriction]
- [Restriction]

### Additional Roles (if applicable)

```
Example:
- Guest: View-only access to public team updates
- Moderator: Can delete inappropriate comments
- Analyst: Can view analytics but not user data
```

**Your Additional Roles:**

[List and describe any other roles]

---

## 🔒 Row-Level Security (Data Access Rules)

Who can see whose data? Define the rule for each data type:

```
Example:
Users Table:
- Admin users can see: All user records
- Team Lead users can see: Only their team members
- Team Member users can see: Only their own record and team members
- No one can see: Password hashes, login tokens, admin flags (except admins)

Updates Table:
- Admin users can see: All updates from all teams
- Team Lead users can see: All updates from their team
- Team Member users can see: All updates from their team
- Team Member users cannot see: Updates from other teams
- Users cannot see: Draft updates that belong to others

Comments Table:
- Visible to: Anyone who can see the parent update
- Deletable by: The comment author or an admin
- Editable by: The comment author (within 24 hours)
```

**Your Row-Level Security Rules:**

[Define access for each table/data type]

---

## ⚠️ Error Handling

What happens when something goes wrong? Define every major failure point:

### Authentication Errors

```
Example:
Error: User enters wrong password
Response: "Email or password is incorrect"
Why this message: Don't reveal if email exists or not (security best practice)
HTTP Status: 401 Unauthorized

Error: User tries to log in with unverified email
Response: "Please verify your email first. Resend verification link?"
HTTP Status: 403 Forbidden

Error: Account is locked (too many failed login attempts)
Response: "Account is temporarily locked. Try again in 15 minutes."
HTTP Status: 429 Too Many Requests

Error: User token has expired
Response: "Session expired. Please log in again."
HTTP Status: 401 Unauthorized
```

**Your Auth Errors:**

[Define your authentication error handling]

### Permission Errors

```
Example:
Error: User tries to view another team's updates
Response: "You don't have permission to view this team"
HTTP Status: 403 Forbidden

Error: Team Member tries to delete an update
Response: "You can only edit your own updates. Contact a Team Lead if this is incorrect."
HTTP Status: 403 Forbidden

Error: User tries to access admin panel
Response: "Admin access required"
HTTP Status: 403 Forbidden
```

**Your Permission Errors:**

[Define your permission error handling]

### Data Validation Errors

```
Example:
Error: User submits empty update
Response: "Update cannot be empty. Please write at least one sentence."
HTTP Status: 400 Bad Request

Error: User enters invalid email format
Response: "Please enter a valid email address"
HTTP Status: 400 Bad Request

Error: User's password is too short
Response: "Password must be at least 8 characters"
HTTP Status: 400 Bad Request
```

**Your Validation Errors:**

[Define your data validation error handling]

### Server Errors

```
Example:
Error: Database connection fails
Response: "Something went wrong. Our team has been notified. Please try again in a few minutes."
HTTP Status: 500 Internal Server Error

Error: Third-party API (like Stripe) is down
Response: "Payments are temporarily unavailable. Please try again shortly."
HTTP Status: 503 Service Unavailable

Error: File upload fails
Response: "Upload failed. File might be too large or in an unsupported format. Max file size: 10MB"
HTTP Status: 400 Bad Request
```

**Your Server Errors:**

[Define your server error handling]

### Network/Timeout Errors

```
Example:
Error: User on slow connection and request times out
Response: "Connection timed out. Please check your internet and try again."
HTTP Status: 408 Request Timeout

Error: User closes browser during file upload
Response: [No error shown] Upload resumes when connection restored
```

**Your Network Errors:**

[Define your timeout/network error handling]

---

## 🌊 Edge Cases

Weird scenarios that can break your app if not handled:

### Edge Case 1: User with Multiple Roles

```
Example:
Scenario: Jane is both a Team Lead in Team A and a Team Member in Team B
Solution: Use their role for the team they're currently viewing.
Show a "Switch team" selector at the top.
```

**Your Edge Case 1:**

[Describe and solve]

### Edge Case 2: User Deleted While Logged In

```
Example:
Scenario: Admin removes a user's account, but that user still has a browser tab open
Solution: Next API call fails with 401 error. Show "Your account no longer exists"
and force logout.
```

**Your Edge Case 2:**

[Describe and solve]

### Edge Case 3: User's Role Changes

```
Example:
Scenario: User is Team Member, gets promoted to Team Lead
Solution: User sees new permissions immediately (if using websockets) or after page refresh.
```

**Your Edge Case 3:**

[Describe and solve]

### Edge Case 4: Offline User Makes Changes

```
Example:
Scenario: User writes an update, internet disconnects, reconnects 5 minutes later
Solution: App queues the update, tries to sync when connection returns.
Show status: "Syncing..." then "Synced" or "Failed to sync"
```

**Your Edge Case 4:**

[Describe and solve]

### Edge Case 5: Simultaneous Edits

```
Example:
Scenario: Two team members comment on the same update at the exact same time
Solution: Both comments save. Show them in order by timestamp. No conflicts.
```

**Your Edge Case 5:**

[Describe and solve]

### Edge Case 6: Slow/Unreliable Network

```
Example:
Scenario: User is on slow 3G connection
Solution:
- Show loading states clearly
- Don't let user submit while request is pending
- If request is still pending after 30 seconds, show "Still loading..."
- Allow cancel after 60 seconds
```

**Your Edge Case 6:**

[Describe and solve]

---

## 🛡️ Data Protection

How is sensitive data protected?

```
Example:
- Encryption at Rest: PostgreSQL transparent data encryption (TDE)
- Encryption in Transit: All API calls use HTTPS (TLS 1.3)
- Password Hashing: bcrypt with salt
- API Keys: Stored in AWS Secrets Manager, never in code
- Database Backups: Daily encrypted backups to S3
- User Data Deletion: Hard delete after 30 days of account closure (GDPR compliance)
- PII Masking: Admin logs never show passwords, email addresses, or tokens
```

**Your Data Protection:**

[Describe your data protection measures]

---

## 🚨 Security Incidents

What's your plan if something goes wrong?

```
Example:
- Data breach: Immediately notify affected users, change all API keys
- DDoS attack: Auto-scaling for servers, WAF (Web Application Firewall) rules
- Malicious user account: Lock account, review all actions, delete malicious data
- Unplanned downtime: Status page updated, automated alerts to team
```

**Your Incident Response:**

[Describe your plan]

---

## 📋 Compliance & Legal

What regulations do you need to follow?

```
Example:
- GDPR (Europe): Support data export, deletion requests
- CCPA (California): Support opt-out of data sales
- HIPAA (Healthcare): If handling health data, full HIPAA compliance
- SOC 2: If enterprise customers required, pursue SOC 2 Type II certification
```

**Your Compliance:**

[List relevant regulations]

---

## 🤖 AI Prompt to Generate This Document

Use this prompt with ChatGPT, Claude, or your preferred AI tool:

```
Act as a senior security engineer who specializes in early-stage product security. 
Create a Security and Access Document for my app. It should cover:

- The authentication method that best fits my use case 
  (email/password, OAuth, 2FA, magic link, SSO, etc.)
- All user roles in the app and exactly what each role can and cannot do
- Row-level security rules for the database 
  (who can read whose data, who can modify what)
- A complete error handling guide for all major failure points:
  - Authentication errors (wrong password, expired session, locked account)
  - Permission errors (unauthorized access)
  - Data validation errors (empty fields, invalid formats)
  - Server errors (database down, API failure)
  - Network errors (timeout, slow connection)
- A list of edge cases I need to handle before launch:
  - Users with multiple roles
  - Users deleted while logged in
  - Simultaneous edits
  - Offline users
  - Users on slow connections

Write everything in plain English so a non-technical founder can understand it.

My app idea is:

[PASTE YOUR APP IDEA OR PRD HERE]
```

---

## 📝 Notes

- **Security isn't optional:** Handle authentication, permissions, and errors before launch
- **Test edge cases:** Have users test on slow networks and with weird scenarios
- **Share with your team:** Everyone should understand the security model
- **Update regularly:** As you add features, update this document
- **Version it:** Keep this in Git like code

---

**A secure app is a trustworthy app. Users will use your product only if they trust it.**
