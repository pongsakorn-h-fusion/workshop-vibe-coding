# Fusion User Profile Web Application

A responsive, mobile-friendly web application for presenting a **public user profile** for **Fusion Solution**.

This document defines the product scope and implementation direction for an MVP built with:
- **Backend:** .NET 10 Web API
- **Frontend:** React (Atomic Design)
- **Data storage (MVP):** In-memory

---

## 1) Project Scope

### Primary goal
Create a clean and trustworthy user profile experience that works well across desktop and mobile devices.

### MVP features
- View user profile
- Manage contact/social links
- Configure profile visibility settings (public-facing behavior)

### Current constraints
- Public profile mode (no authentication in MVP)
- Local-first testing
- In-memory data for fast iteration

> Note: Because this MVP is public profile first and local-first, update operations are intended for controlled/demo usage.

---

## 2) Requirement Coverage

This project is designed to satisfy all requested constraints:

1. ✅ **Responsive support**
2. ✅ **Usable on mobile devices**
3. ✅ **.NET 10 backend + React frontend**
4. ✅ **Essential endpoint(s), including `/health`**
5. ✅ **Repository Pattern architecture**
6. ✅ **Frontend follows Atomic Design principles**

---

## 3) High-Level Architecture

```text
[React UI (Atomic Design)]
        |
        v
[.NET 10 Web API]
        |
        v
[Application Layer]
        |
        v
[Repository Interfaces]
        |
        v
[In-Memory Repository Implementation]
```

### Backend responsibilities (.NET 10)
- Expose REST API endpoints
- Validate and orchestrate profile operations
- Apply business rules for visibility/contact links
- Serve health status for runtime checks

### Frontend responsibilities (React)
- Render profile page with responsive layout
- Support mobile-first interaction and readability
- Consume backend endpoints for profile data
- Organize components via Atomic Design

---

## 4) Frontend Design System (Atomic Design)

Recommended structure:

```text
src/
  components/
    atoms/
      Avatar
      Button
      Label
      Text
    molecules/
      ContactItem
      SocialLinkItem
      ProfileStat
    organisms/
      ProfileHeader
      ContactSection
      VisibilitySettingsPanel
    templates/
      ProfileTemplate
    pages/
      ProfilePage
```

### Responsive design expectations
- Mobile-first layout strategy
- Flexible grid and spacing system
- Scalable typography and touch-friendly controls
- Tested at common viewport widths (small mobile, large mobile, tablet, desktop)

---

## 5) Backend Structure (Repository Pattern)

Recommended logical layers:

```text
Backend/
  Domain/
    Entities/
      UserProfile.cs
  Application/
    Interfaces/
      IUserProfileRepository.cs
    Services/
      UserProfileService.cs
  Infrastructure/
    Repositories/
      InMemoryUserProfileRepository.cs
  API/
    Endpoints/
      ProfileEndpoints.cs
      HealthEndpoints.cs
```

### Repository Pattern intent
- Decouple business logic from data access
- Keep data source swappable (in-memory now, SQL/NoSQL later)
- Improve testability and maintainability

---

## 6) API Endpoints (MVP)

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/health` | Service health check |
| GET | `/api/profile` | Get public user profile |
| PUT | `/api/profile` | Update profile content |
| PUT | `/api/profile/contact-links` | Update contact/social links |
| PUT | `/api/profile/visibility` | Update visibility settings |

### Health endpoint contract
`/health` should return:
- HTTP `200` when application is healthy
- A lightweight payload (e.g., status + timestamp)

---

## 7) Suggested Data Model (MVP)

- `id`
- `fullName`
- `headline`
- `bio`
- `avatarUrl`
- `contactLinks[]` (platform, label, url)
- `visibilitySettings` (public flags)
- `updatedAt`

---

## 8) Non-Functional Expectations

- Fast initial load on mobile networks
- Clear visual hierarchy and readability
- Stable API contracts for frontend integration
- Simple observability via `/health`

---

## 9) Future Enhancements

- Authentication and authorization
- Persistent database integration (SQL/NoSQL)
- Profile analytics
- Image/file storage integration
- CI/CD deployment target definition

---

## 10) Acceptance Checklist

Before considering MVP complete:

- [ ] Profile page renders correctly on mobile and desktop
- [ ] Atomic Design component hierarchy is respected
- [ ] .NET 10 backend serves all required endpoints
- [ ] `/health` responds reliably with HTTP 200 when healthy
- [ ] Repository Pattern is used for profile data access
- [ ] In-memory repository works for local-first testing
