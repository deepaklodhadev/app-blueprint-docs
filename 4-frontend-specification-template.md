# Frontend Specification Document

**Design System, Components, and API Integrations**

This document defines how your app looks, feels, and talks to external services.

---

## 📌 Overview

Describe your design philosophy in 1-2 sentences:

```
Example: "TaskFlow is clean, minimal, and focused. Navy blue + orange accent color. 
All buttons are large and obvious. Loading states are clear. Error messages are helpful, not scary."
```

**Your Overview:**

[Write your design philosophy]

---

## 🎨 Color Palette

Define your brand colors with hex codes:

```
Example:
Primary (Navy Blue): #1e3a8a
Secondary (Orange): #f97316
Background: #ffffff
Text Primary: #1f2937
Text Secondary: #6b7280
Success (Green): #10b981
Warning (Yellow): #f59e0b
Error (Red): #ef4444
Border: #e5e7eb
```

**Your Color Palette:**

| Color Name | Purpose | Hex Code |
|-----------|---------|----------|
| [Name] | [Usage] | [#XXXXXX] |
| [Name] | [Usage] | [#XXXXXX] |
| [Name] | [Usage] | [#XXXXXX] |

---

## ✍️ Typography

Define your fonts and how they're used:

```
Example:
Heading Font: Inter (from Google Fonts)
Body Font: Inter (from Google Fonts)

Sizes:
- H1 (Page Title): 32px, bold, color: primary
- H2 (Section Title): 24px, bold, color: primary
- H3 (Subsection): 18px, semibold, color: primary
- Body: 16px, regular, color: text-primary
- Small/Caption: 14px, regular, color: text-secondary
- Button Text: 14px, semibold, color: white

Line Height: 1.5 for body text, 1.3 for headings
Letter Spacing: Normal (default)
```

**Your Typography:**

Heading Font: [Font name]
Body Font: [Font name]

| Element | Size | Weight | Color |
|---------|------|--------|-------|
| H1 | [Size] | [Weight] | [Color] |
| H2 | [Size] | [Weight] | [Color] |
| Body | [Size] | [Weight] | [Color] |

---

## 🧩 Component Styles

Define how key UI components look:

### Buttons

```
Example:
Primary Button:
- Background: Navy blue (#1e3a8a)
- Text: White
- Padding: 12px 24px
- Border Radius: 8px
- Font Weight: Semibold
- Hover: Darker navy (#1e40af)
- Disabled: Gray (#d1d5db), cursor not-allowed
- Size: 16px font

Secondary Button:
- Background: Orange (#f97316)
- Text: White
- Padding: 12px 24px
- Border Radius: 8px
- Hover: Darker orange (#ea580c)

Danger Button:
- Background: Red (#ef4444)
- Text: White
- Padding: 12px 24px
- Border Radius: 8px
- Hover: Darker red (#dc2626)

States:
- Default: As described above
- Hover: Darker color
- Disabled: Gray, no hover effect
- Loading: Show spinner, disable interaction
```

**Your Buttons:**

[Describe your button styles]

### Input Fields

```
Example:
Text Input:
- Background: White
- Border: 1px solid #e5e7eb
- Padding: 12px
- Border Radius: 8px
- Font: 16px
- Focus: Border color changes to navy (#1e3a8a)
- Error: Border color red (#ef4444), error text below

Placeholder Text: #9ca3af, italic
```

**Your Inputs:**

[Describe your input field styles]

### Cards

```
Example:
Card Component:
- Background: White
- Border: 1px solid #e5e7eb
- Border Radius: 12px
- Padding: 24px
- Shadow: subtle (box-shadow: 0 1px 3px rgba(0,0,0,0.1))
- Hover: Slightly elevated (box-shadow: 0 4px 6px rgba(0,0,0,0.1))

Task Card:
- Title: H3 (18px bold)
- Subtitle: Body + lighter gray
- Actions: Buttons at bottom
- Status: Color-coded badge (green for done, yellow for in-progress)
```

**Your Cards:**

[Describe your card styles]

### Modals

```
Example:
Modal Dialog:
- Background: White
- Border Radius: 12px
- Padding: 32px
- Max Width: 600px
- Overlay: Dark semi-transparent (rgba(0,0,0,0.5))
- Close Button: X in top-right corner
- Title: H2 (24px bold)
- Content: Body text
- Footer: Buttons (Cancel on left, Action on right)

Animations:
- Fade in: 150ms
- Fade out: 150ms
```

**Your Modals:**

[Describe your modal styles]

### Forms

```
Example:
Form Structure:
- Label above input
- Input below label
- Helper text (small gray) below input (if needed)
- Error message (red) below input (if validation fails)
- Spacing between fields: 24px

Form Submission:
- Show loading spinner on button during submission
- Disable button while submitting
- Show success message: "Update posted successfully!"
- Show error message: "Failed to post update. Try again."
```

**Your Forms:**

[Describe your form styles]

---

## 📐 Spacing & Layout

Define how much space goes between elements:

```
Example:
Spacing Scale:
- xs: 4px
- sm: 8px
- md: 16px
- lg: 24px
- xl: 32px
- 2xl: 48px
- 3xl: 64px

Common Patterns:
- Page padding: 24px (lg)
- Card padding: 24px (lg)
- Section spacing: 48px (2xl)
- Element spacing: 16px (md)

Grid System:
- Desktop: 12-column grid
- Tablet: 8-column grid
- Mobile: 4-column grid
```

**Your Spacing:**

[Define your spacing scale]

---

## 📱 Responsive Breakpoints

How does your app look on different screen sizes?

```
Example:
Mobile (< 640px):
- Single column layout
- Full-width buttons
- Larger touch targets (48px minimum)
- Simplified navigation (hamburger menu)

Tablet (640px - 1024px):
- 2-column layout where applicable
- 90% width on main content
- Navigation in top bar

Desktop (> 1024px):
- 3-column or multi-column layouts
- 80% width on main content (centered)
- Full navigation visible
```

**Your Breakpoints:**

[Define your responsive design]

---

## 🔌 API & Integration Spec

Every external service connected to your app:

### Integration 1: Authentication Service

```
Example:
Service: Firebase Authentication
Purpose: User sign-up, login, password reset
Endpoints Used:
- POST /auth/signup (email, password)
- POST /auth/login (email, password)
- POST /auth/logout (token)
- POST /auth/password-reset (email)
- POST /auth/verify-2fa (code)

Data Sent:
{
  email: "user@example.com",
  password: "hashedPassword",
  firstName: "John",
  lastName: "Doe"
}

Data Received:
{
  userId: "user123",
  email: "user@example.com",
  token: "eyJhbGc...",
  expiresIn: 2592000
}

Error Handling:
- Wrong password: Return 401 + "Email or password incorrect"
- User not found: Return 404 + "Account not found"
- Server error: Return 500 + "Please try again"
```

**Your Integration 1:**

[Service name and details]

### Integration 2: Payment Service

```
Example:
Service: Stripe
Purpose: Handle subscription billing
Endpoints Used:
- POST /payments/create-subscription (planId, paymentMethodId)
- POST /payments/cancel-subscription (subscriptionId)
- GET /payments/invoice-history (userId)

Data Sent:
{
  planId: "plan_monthly_pro",
  paymentMethodId: "pm_1234567890",
  email: "user@example.com"
}

Data Received:
{
  subscriptionId: "sub_1234567890",
  status: "active",
  nextBillingDate: "2024-07-01",
  amount: 2999
}

Webhooks:
- invoice.payment_succeeded: Update user's subscription status
- invoice.payment_failed: Notify user, mark subscription as past due
- customer.subscription.deleted: Downgrade user to free plan
```

**Your Integration 2:**

[Service name and details]

### Integration 3: Email Service

```
Example:
Service: SendGrid
Purpose: Send transactional emails (verification, password reset, notifications)
Endpoints Used:
- POST /emails/send (to, subject, template, data)

Data Sent:
{
  to: "user@example.com",
  subject: "Verify your email",
  templateId: "d-abc123",
  dynamicData: {
    verificationLink: "https://app.com/verify?token=xyz"
  }
}

Response:
{
  messageId: "msg_12345"
}

Templates:
- Email Verification (on signup)
- Password Reset (on forgot password)
- Daily Digest (optional notification)
- Invoice (receipt for payment)
```

**Your Integration 3:**

[Service name and details]

### Integration 4: [Your Integration]

[Service name and details]

---

## 🎬 Loading States

How does the UI show that something is loading?

```
Example:
- Button Loading: Show spinner inside button, disable button
- Page Loading: Show skeleton loader (gray boxes matching content shape)
- List Loading: Show 3-5 skeleton cards while data loads
- Image Loading: Show gray placeholder, fade in actual image
- Timeout: After 30 seconds, show "Still loading..." message
```

**Your Loading States:**

[Describe how you show loading]

---

## 🚨 Empty States

What does the UI show when there's no data?

```
Example:
Empty Task List:
- Illustration (empty inbox icon)
- Message: "No updates yet"
- Helper text: "Post your first update to get started"
- Call-to-action button: "Post Update"
```

**Your Empty States:**

[Describe your empty states]

---

## 🎯 Accessibility

How do you make your app usable for everyone?

```
Example:
- Color not the only indicator (add icons, text labels)
- Minimum contrast ratio: 4.5:1 for text
- Keyboard navigation: Tab through all interactive elements
- Screen reader support: Buttons have aria-label, images have alt text
- Form labels: Every input has a <label> associated with it
- Error messages: Clear, specific (not just red highlighting)
```

**Your Accessibility:**

[Describe your accessibility approach]

---

## 📐 Dark Mode (Optional)

If supporting dark mode, define how colors change:

```
Example:
Dark Mode Colors:
- Background: #111827 (very dark gray)
- Text: #f3f4f6 (light gray)
- Card Background: #1f2937
- Border: #374151

How colors change:
- Primary blue: Lighter version (#3b82f6) for better contrast
- Text: Inverted (dark text on light, light text on dark)
- Buttons: Same color but text may invert
```

**Your Dark Mode:**

[If applicable, describe dark mode colors]

---

## 🤖 AI Prompt to Generate This Document

Use this prompt with ChatGPT, Claude, or your preferred AI tool:

```
Act as a senior UI/UX designer and frontend architect. 
Create a Frontend Specification Document for my app. It should include:

- A complete design system:
  - Color palette with hex codes for primary, secondary, backgrounds, text, success, warning, error
  - Typography choices (heading font, body font, sizes, weights, where each is used)
  - Component styles clearly defined for buttons, inputs, cards, and modals
  - Spacing and layout rules (padding, margins, grid system)
  - How the design responds to different screen sizes (mobile, tablet, desktop)

- A full API and integration spec for every third party service my app will use:
  - What each service does in my app
  - Which endpoints are called and with what data
  - What response is expected
  - How errors are handled
  
- Loading states and empty states (what shows when data is loading or missing)
- Accessibility considerations (color contrast, keyboard navigation, screen readers)

Write everything in clear, technical language suitable for a developer.

My app idea is:

[PASTE YOUR APP IDEA OR PRD HERE]
```

---

## 📝 Notes

- **Consistency is key:** Every screen should follow these specifications
- **Document every color:** Use a tool like Figma to organize your design system
- **Share with team:** Designers and developers should both read this
- **Update it:** When you change the design, update this document
- **Version it:** Keep this in Git alongside your code

---

**A consistent design system makes building faster and the product feel polished.**
