---
title: "Week #2"
---

# **Week #2**

## Detailed Requirements Elaboration

### Detailed User Stories for MVP

Based on the high-level user stories from Week 1 and aligned with our microservices architecture, we have expanded them into detailed, actionable user stories:

#### **Authentication and User Management (Auth Service + Users Service)**

- **User 01**: As a new user, I want to register into platform so that I can securely access the all the materials
  - *Acceptance Criteria*: Auth Service validates credentials, generates JWT tokens, API Gateway validates tokens for all requests
  - *Technical Implementation*: Auth Service handles registration/login, Users Service stores profile data
  - *Priority*: High

- **User 02**: As a user, I want to manage my profile (for e.g. credentials) through the Users Service so that I can update my information and maintain accurate account details
  - *Acceptance Criteria*: CRUD operations for user profiles, data persistence in Users DB
  - *Technical Implementation*: Frontend → API Gateway → Users Service → Users DB
  - *Priority*: High

- **User 03**: As a user, I want my authentication state to persist across all services so that I don't need to re-login when accessing different modules
  - *Acceptance Criteria*: JWT tokens validated by API Gateway, user context passed to microservices via gRPC
  - *Technical Implementation*: API Gateway middleware validates JWT, passes user ID to services
  - *Priority*: High

#### **Labs Management (Labs Service + File Storage)**

- **User 04**: As a student, I want to browse and search available labs through the Labs Service so that I can find relevant assignments
  - *Acceptance Criteria*: Labs Service provides REST API for lab listing
  - *Technical Implementation*: Frontend → API Gateway → Labs Service → Labs DB
  - *Priority*: High

- **User 05**: As a student, I want to view detailed lab instructions stored in the Labs Service and download resources from the platform
  - *Acceptance Criteria*: Labs Service returns lab metadata, file URLs point to MinIO storage
  - *Technical Implementation*: Labs Service provides signed URLs for file access
  - *Priority*: High

- **User 06**: As a student, I want to submit lab solutions by uploading files to the platform
  - *Acceptance Criteria*: File upload to MinIO, submission metadata stored in Labs DB
  - *Technical Implementation*: Frontend uploads to S3/MinIO, Labs Service stores file references and metadata
  - *Priority*: High

- **User 07**: As an educator, I want to create lab assignments through Labs Service with file attachments stored in the platform
  - *Acceptance Criteria*: Labs Service API for CRUD operations, file uploads to MinIO, lab publishing workflow
  - *Technical Implementation*: Rich editor uploads resources to MinIO, Labs Service stores lab structure
  - *Priority*: High

#### **Articles Management (Articles Service + File Storage)**

- **User 08**: As a researcher, I want to publish articles through Articles Service with supporting documents stored in the platform
  - *Acceptance Criteria*: Articles Service handles article CRUD, file references to MinIO
  - *Technical Implementation*: Frontend → API Gateway → Articles Service → Articles DB
  - *Priority*: High

- **User 09**: As a user, I want to browse published articles through Articles Service
  - *Acceptance Criteria*: Articles Service provides REST API for articles listing
  - *Technical Implementation*: Frontend → API Gateway → Articles Service → Articles DB
  - *Priority*: High

#### **Feedback and Review System (Feedback Service)**

- **User 10**: As a student, I want to receive structured feedback on lab submissions through
  - *Acceptance Criteria*: Feedback Service stores reviews linked to lab submissions
  - *Technical Implementation*: Feedback Service connects to Labs Service via gRPC for submission data
  - *Priority*: High

- **User 11**: As a reviewer, I want to provide feedback on articles and labs
  - *Acceptance Criteria*: Comment systems, reviewer assignment logic
  - *Technical Implementation*: Feedback Service handles review workflows and notifications
  - *Priority*: High

- **User 12**: As a platform user, I want to track feedback history and respond to reviews
  - *Acceptance Criteria*: Feedback threads, notification system, response tracking, review status management
  - *Technical Implementation*: Feedback Service manages review conversations and state
  - *Priority*: Medium

### Prioritized backlog

Can be found by this [(link)](https://github.com/orgs/IU-Capstone-Project-2025/projects/6/views/1)

## Project specific progress

### Frontend

*...*

### Backend

*...*

### ML

*...*

# Weekly commitments

## Individual contribution of each participant

- **Kirill Efimovich (PM / DevOps):**

**Kanban board (clickable):** [link](link) \
**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Summary of TA feedback:** Good project idea, a little bit behind of other groups due to lack of meetings efficiency. Clear previous report, but more artifacts required for the future. \
**Weekly contribution:** text here

- **Mikhail Trifonov (Backend):**

**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Weekly contribution:** text here
  
- **Nikita Maksimenko (Backend):**

**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Weekly contribution:** text here

- **Timur Salakhov (Backend):**

**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Weekly contribution:** text here

- **Ravil Kazeev (Backend):**

**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Weekly contribution:** text here

- **Kirill Shumskiy (ML):**

**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \
**Weekly contribution:** text here

- **Aleliya Turushkina (Designer / Frontend):**

**Figma board (clickable):** [link](link) \
**Closed issues (clickable):** [Issue](link), [Issue](link), [Issue](link) \
**Closed PR's (clickable):** [PR](link), [PR](link), [PR](link) \

## Plan for Next Week

With all preparation work and documentation completed, our team is ready to focus entirely on developing the MVP over the next week.

### Tasks to be tackled

- **Backend Development:**
  - Implement core API endpoints for user authentication and study materials management
  - Set up database schema and data models
  - Implement basic CRUD operations for study materials and user profiles

- **Frontend Development:**
  - Create main user interface components based on finalized designs
  - Implement projected user authentication flows (login/register)
  - Develop study materials browsing functionality
  - Build projected basic user profile management interface

- **ML Integration:**
  - Deploy trained recommendation model
  - Create API endpoints for model inference
  - Test model performance with user data

### Expected Deliverables

- **Functional MVP** with core features implemented
- **Deployed application** accessible via Docker image
- **Complete API documentation** for all implemented endpoints
- **Updated project documentation** reflecting current implementation status

## Confirmation of the code's operability

We confirm that the code in the main branch:

  ☑️ In working condition. \
  ☑️ Run via docker-compose (or another alternative described in the `README.md`).
