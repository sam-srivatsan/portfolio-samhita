---
title: Assignment 4
layout: doc
---
# ASSIGNMENT 4: Backend Design & Implementation

## App Definition
```
app GenSpeak

concepts
    Authenticating
    Sessioning[Authenticating.User]
    Posting[Authenticating.User]
    Replying[Posting.Post]
    CalendarEvent[Authenticating.User]
    Grouping[Authenticating.User, Posting.Post, CalendarEvent.Event]
```

## Abstract Data Models

#### 1. **Post[Post]**
**Purpose**: Allow users to share content with the community.

**Core Functionality**: Users can create posts visible to others on the platform.

**Actions**:
- `createPost(content: string, media: Media)`: Add a post with the specified content and media.
- `getUserPosts(username: string)`: Retrieve all posts by a user.
- `searchPostsByTitle(title: string)`: Find posts matching or starting with a title.
- `deletePost(postID: Post.ID)`: Remove a specific post by its ID.

**State**:
- `Posts`: A set of posts, each linked to a user.

#### 2. **Reply[Reply]**
**Purpose**: Enable users to respond to posts in organized threads.

**Core Functionality**: Users can reply to posts and view replies based on visibility.

**Actions**:
- `addReply(postID: Post.ID, content: string)`: Add a reply to a specific post.
- `viewReplies(postID: Post.ID)`: View replies for a post.

**State**:
- `Replies`: A set of replies linked to posts.
- `ReplyVisibility`: Defines which users can view replies.

#### 3. **Authenticate[User]**
**Purpose**: Handle user registration, login, and authentication.

**Core Functionality**: Users can create accounts and log in securely.

**Actions**:
- `register(username: string, password: string)`: Register a new user.
- `login(username: string, password: string)`: Authenticate a user.

**State**:
- `UserCredentials`: A set of username-password pairs.
- `AuthStatus`: Tracks whether a user is logged in.

#### 4. **Session[User]**
**Purpose**: Manage active user sessions for continuous authentication.

**Core Functionality**: Users stay logged in across different pages until their session ends.

**Actions**:
- `startSession(userID: User.ID)`: Begin a session for a user.
- `endSession(userID: User.ID)`: End a user’s session.

**State**:
- `ActiveSessions`: A set of ongoing sessions.
- `SessionTimeout`: Timer for session expiration.

#### 5. **Calendar[Event]**
**Purpose**: Schedule and manage events for users.

**Core Functionality**: Users can create, view, or delete events based on permissions.

**Actions**:
- `addEvent(userID: User.ID, event: Event)`: Add a new event.
- `deleteEvent(eventID: Event.ID)`: Remove an event.

**State**:
- `Events`: A set of scheduled events.
- `EventAccess`: Tracks which users can access specific events.

#### 6. **Groups[Group]**
**Purpose**: Facilitate group-based activities and interactions.

**Core Functionality**: Users can form groups, invite others, and share content within the group.

**Actions**:
- `createGroup(creator: User.ID, groupName: string)`: Create a new group.
- `inviteToGroup(groupID: Group.ID, memberID: User.ID)`: Invite a user to a group.

**State**:
- `GroupMembers`: Tracks which users belong to which groups.
- `GroupContent`: Posts and events accessible only to group members.
