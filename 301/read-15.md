
- [What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html){:target="_blank"}

(vid 1 recap, scroll down)
- [Authorization and Authentication flows](https://auth0.com/docs/flows){:target="_blank"}
-vid 2 scroll down

## Videos

<!-- PLACEHOLDER -->

## Bookmark and Review

- [Auth0 for single page apps](https://auth0.com/docs/libraries/auth0-react){:target="_blank"}
It's difficult to objectively say that a specific company "needs DEI," since that is a value judgment and companies vary in their current initiatives and workforce data. A more accurate statement is that any organization can benefit from improving diversity, equity, inclusion, and accessibility (DEIA) if it has representation gaps or barriers to opportunity.

Here are examples of industries where DEI efforts are often discussed because they have historically had lower representation of certain groups:

Industry	Common DEI Focus
Technology	Increase representation of women and underrepresented racial/ethnic groups in engineering and leadership
Construction	Recruit more women and diverse talent into skilled trades
Manufacturing	Expand hiring and advancement opportunities
Finance & Banking	Improve leadership diversity and equitable promotion
Healthcare	Build culturally competent care and a diverse workforce
Law	Increase diversity among attorneys, judges, and firm leadership
Engineering	Encourage broader participation in STEM careers
Video Games	Improve representation in development teams and leadership
Artificial Intelligence	Reduce bias in AI systems through diverse teams and testing
Government	Ensure public services reflect the communities they serve
Why Companies Invest in DEI
Better problem-solving
More innovation
Improved employee retention
Broader customer understanding
Better accessibility and inclusive product design
Stronger collaboration across teams
Examples of Companies Recognized for DEI Efforts

These companies have been widely recognized for investing in inclusion initiatives (though like all large organizations, they continue to evolve):

Microsoft
Salesforce
Accenture
Adobe
IBM
Cisco

For a class discussion, it's usually better to frame the topic as "Which industries have historically faced diversity challenges, and what are companies doing to address them?" rather than labeling specific companies as needing DEI. That approach is more evidence-based and encourages constructive discussion.

list those
# Companies That Have Historically Faced Diversity Challenges

> **Note:** These companies have publicly discussed or reported diversity challenges and have invested in DEI initiatives. This does **not** mean they are "bad" companies—many are actively working to improve representation and inclusion.

## Technology

- Google
- Meta (Facebook)
- Apple
- Microsoft
- Amazon
- Intel
- Cisco
- IBM
- Oracle
- Salesforce
- Adobe
- Uber
- Airbnb
- Netflix

---

## Finance & Banking

- JPMorgan Chase
- Goldman Sachs
- Bank of America
- Wells Fargo
- Citigroup
- Morgan Stanley

---

## Engineering & Manufacturing

- Boeing
- General Motors (GM)
- Ford
- Caterpillar
- Siemens
- General Electric (GE)

---

## Video Games

- Activision Blizzard
- Electronic Arts (EA)
- Ubisoft
- Riot Games
- Epic Games

---

## Retail & Consumer Products

- Walmart
- Target
- Nike
- Starbucks
- Costco

---

## Healthcare & Pharmaceuticals

- Johnson & Johnson
- Pfizer
- Merck
- CVS Health
- Kaiser Permanente

---

## Consulting

- Accenture
- Deloitte
- PwC
- EY (Ernst & Young)
- KPMG

---

# Common DEI Goals Across These Companies

- Increase representation of women
- Increase representation of underrepresented racial and ethnic groups
- Improve accessibility for employees and customers
- Reduce hiring and promotion bias
- Increase diversity in leadership
- Create inclusive workplace cultures
- Improve equal pay practices
- Expand mentorship and career development programs
act as a coding student making notes in md form # Readings: Authentication

Below you will find some reading material, code samples, and some additional resources that support the topic for this class and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

- [What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)
(see below)
## Videos

## Bookmark and Review

- [Auth0 for single page apps](https://auth0.com/docs/libraries/auth0-react){:target="_blank"}



# 📚 Authentication Notes

## What is Authentication?

- **Authentication** = Proves **who you are**.
- Verifies a user's identity before allowing access.

**Examples:**
- Username & password
- Sign in with Google
- Sign in with GitHub
- Face ID
- Fingerprint

---

## What is Authorization?

- **Authorization** = Determines **what you're allowed to do** after logging in.

**Example:**
- Student can view grades.
- Teacher can edit grades.
- Admin can manage users.

> **Easy to remember:**
>
> - Authentication = **Who are you?**
> - Authorization = **What can you access?**

---

# OAuth

## What is OAuth?

OAuth (Open Authorization) is a secure way to let users sign in using another trusted account **without sharing their password**.

Examples:
- Sign in with Google
- Sign in with GitHub
- Sign in with Facebook
- Sign in with Microsoft

---

## Example of OAuth

Instead of creating a new account:

1. Click **Continue with Google**.
2. Google asks for permission.
3. Click **Allow**.
4. You're logged into the app.

The app never sees your Google password.

---

## How OAuth Works

1. User clicks **Login with Google**.
2. App redirects user to Google.
3. User signs in.
4. Google asks for permission.
5. User approves access.
6. Google sends an authorization code or token.
7. App verifies the token.
8. User is logged in.

---

## What is OpenID?

OpenID Connect (OIDC) is built on top of OAuth.

- OAuth = Authorization
- OpenID Connect = Authentication + User identity

OpenID tells the app **who the user is**.

---

# Authentication vs Authorization

| Authentication | Authorization |
|---------------|---------------|
| Confirms identity | Grants permissions |
| "Who are you?" | "What can you do?" |
| Happens first | Happens after login |

---

# OAuth Flows

## Authorization Code Flow

**Best for:**
- Traditional web applications

How it works:
- User logs in.
- Server receives an authorization code.
- Server exchanges it for an access token.

---

## Authorization Code Flow with PKCE

**Best for:**
- React
- Mobile apps
- Single Page Applications (SPAs)

PKCE adds extra security by preventing authorization code interception.

---

## Implicit Flow with Form Post

- Older authentication flow.
- Returns the token directly.
- Less secure than Authorization Code + PKCE.
- Rarely recommended for new apps.

---

## Client Credentials Flow

Used when **one application talks to another**.

No user logs in.

Example:
- Backend server requests data from another API.

---

## Device Authorization Flow

Used on devices without a keyboard.

Examples:
- Smart TVs
- Gaming consoles

User enters a code on another device to log in.

---

## Resource Owner Password Flow

User enters username and password directly into the app.

- Not recommended today.
- Mostly used for older (legacy) applications.

---

# Auth0

Auth0 is an authentication service that helps developers:

- Log users in
- Manage user accounts
- Handle OAuth
- Handle OpenID Connect
- Secure applications

Instead of building authentication from scratch.

---

# Real-World Examples

## Google

- Sign in with Google
- Uses OAuth + OpenID Connect

---

## GitHub

- Sign in with GitHub
- Common for developer websites

---

## Spotify

- Login with Google, Facebook, or Apple

---

## Discord

- Sign in using Discord account

---

## Code Fellows Projects

Later React apps may use Auth0 to:

- Sign users in
- Protect routes
- Display user profiles
- Restrict access to logged-in users

---

# Quick Reference

| Term | Meaning |
|------|---------|
| Authentication | Verify identity |
| Authorization | Grant permissions |
| OAuth | Secure authorization |
| OpenID Connect | User authentication built on OAuth |
| Auth0 | Authentication platform |

---

# Authentication Flow

```text
User
   │
   ▼
Clicks "Login with Google"
   │
   ▼
Google Login
   │
   ▼
User Signs In
   │
   ▼
Google Verifies User
   │
   ▼
Authorization Code / Token
   │
   ▼
Application Verifies Token
   │
   ▼
User Logged In
```

---

# Key Takeaways

- Authentication = Verify identity.
- Authorization = Determine permissions.
- OAuth allows secure login without sharing passwords.
- OpenID Connect adds user identity to OAuth.
- PKCE is the recommended flow for React and mobile apps.
- Auth0 simplifies authentication in web applications.

vid 1 # What is OAuth? – Notes

## What is OAuth?

- **OAuth (Open Authorization)** is a standard that allows users to give an app limited access to their account **without sharing their password**.

---

## Why Use OAuth?

- Keeps passwords private.
- Improves security.
- Lets users sign in quickly with existing accounts.

---

## Common Examples

- Sign in with Google
- Sign in with GitHub
- Sign in with Microsoft
- Sign in with Facebook

---

## How OAuth Works

1. User clicks **"Sign in with Google"**.
2. User logs into Google (if needed).
3. Google asks if the app can access certain information.
4. User grants permission.
5. Google sends an **access token** to the app.
6. The app uses the token to access approved data.

> The app never sees the user's password.

---

## OAuth Components

- **User** – Person logging in.
- **Application (Client)** – App requesting access.
- **Authorization Server** – Verifies the user (e.g., Google).
- **Resource Server** – Stores the user's data.

---

## What is an Access Token?

- A temporary digital "key."
- Gives limited access to approved resources.
- Can expire for security.

---

## OAuth vs Password Login

| Traditional Login | OAuth |
|-------------------|--------|
| Share password with every app | Password stays with provider |
| Less secure | More secure |
| Separate account for each app | One account can sign into many apps |

---

## Benefits

- More secure
- Faster login
- Better user experience
- Users control what data is shared

---

## Key Takeaways

- OAuth provides **authorization**, not authentication.
- It allows apps to access specific user data without exposing passwords.
- Commonly used for **"Continue with Google"** or **"Sign in with GitHub."**

###Vid 2 
# Auth0 Authentication & Authorization Flows

## Authentication vs Authorization

| Authentication | Authorization |
|---------------|---------------|
| Confirms **who** the user is | Determines **what** the user can access |

---

## OAuth Flows

### Authorization Code Flow
- Used for **traditional web apps**.
- Server exchanges an authorization code for an access token. :contentReference[oaicite:0]{index=0}

### Authorization Code Flow + PKCE ⭐ (Recommended)
- Best for **React, mobile apps, and Single Page Apps (SPAs)**.
- Adds extra security to protect the authorization code.
- Recommended by Auth0 for most modern applications. :contentReference[oaicite:1]{index=1}

### Implicit Flow
- Older browser-based flow.
- Less secure.
- Not recommended for new applications. :contentReference[oaicite:2]{index=2}

### Client Credentials Flow
- Used for **server-to-server (Machine-to-Machine)** communication.
- No user login required. :contentReference[oaicite:3]{index=3}

### Device Authorization Flow
- Used for devices with limited input.
- Examples:
  - Smart TVs
  - Gaming consoles
  - IoT devices :contentReference[oaicite:4]{index=4}

### Resource Owner Password Flow
- User enters username and password directly into the application.
- Only for highly trusted applications.
- Generally **not recommended** today. :contentReference[oaicite:5]{index=5}

---

# Which Flow Should I Use?

| Application Type | Recommended Flow |
|------------------|------------------|
| React / SPA | Authorization Code + PKCE |
| Mobile App | Authorization Code + PKCE |
| Traditional Web App | Authorization Code Flow |
| Backend Service | Client Credentials Flow |
| Smart TV / Console | Device Authorization Flow |
| Legacy App | Resource Owner Password Flow |

---

# Key Takeaways

- **PKCE** is the preferred flow for modern React applications.
- Use **Authorization Code Flow** for traditional server-side apps.
- Use **Client Credentials** when no user is involved.
- Avoid **Implicit Flow** and **Resource Owner Password Flow** for new projects when possible. :contentReference[oaicite:6]{index=6}
---