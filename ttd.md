# Technical Design Document (TTD)

## Feature: Instagram Stories

### Overview

The Instagram Stories feature allows users to upload images and videos that automatically disappear after 24 hours. Users can view, react to, reply to, and delete their own stories.

---

## User Actions & System Responses

### Upload Story

**User Action:** User clicks the Upload Story button.

**System Response:**

* Open upload modal
* Allow media selection
* Display media preview

### Post Story

**User Action:** User clicks the Post Story button.

**System Response:**

* Validate file
* Upload media
* Save story to database
* Display success message

### View Story

**User Action:** User clicks a story avatar.

**System Response:**

* Open story viewer
* Record story view
* Start story timer

### React to Story

**User Action:** User clicks a reaction icon.

**System Response:**

* Save reaction
* Notify story owner

### Reply to Story

**User Action:** User submits a reply.

**System Response:**

* Save message
* Send notification to story owner

### Delete Story

**User Action:** User clicks the Delete Story button.

**System Response:**

* Delete media from storage
* Remove story from database

---

## Functional Requirements

* Upload image stories
* Upload video stories
* View stories
* React to stories
* Reply to stories
* Delete stories
* Automatically remove stories after 24 hours

---

## Database Structure

### User Collection

* `_id`
* `username`
* `profilePicture`

### Story Collection

* `_id`
* `userId`
* `mediaUrl`
* `mediaType`
* `createdAt`
* `expiresAt`
* `views`

---

## API Endpoints

### Create Story

`POST /api/stories`

### Get Stories

`GET /api/stories`

### View Story

`POST /api/stories/:id/view`

### React to Story

`POST /api/stories/:id/react`

### Reply to Story

`POST /api/stories/:id/reply`

### Delete Story

`DELETE /api/stories/:id`

---

## Technology Stack

### Frontend

* React.js

### Backend

* Node.js
* Express.js

### Database

* MongoDB

### Storage

* Cloudinary / Firebase

### Authentication

* JWT
