wiref# Pitch
### GenSpeak: Bridging Generations Through Shared Stories and Cultures

GenSpeak is designed to bring together family members and friends across generations, especially those separated by language or cultural differences. Aimed at multi-generational and immigrant families, GenSpeak goes beyond traditional social media by offering a platform that focuses on deep, meaningful connections. Unlike apps that divide users by demographic or language, GenSpeak empowers communication through intuitive design and multimedia tools like photos, videos, and voice memos.

Key features include the **Cultural Celebration Calendar**, which highlights holidays and traditions across cultures and generations, and **Story Swap**, where users can share personal memories and cultural insights. **Language Mentor Match** pairs older and younger generations to teach each other their native languages, while the **Wisdom Wall** allows older users to share life lessons and advice in a community format.

With seamless voice-to-text translation and interactive time capsules, GenSpeak ensures that everyone, regardless of age or language, can stay connected and engaged. It’s a tool not just for communication but for learning, collaboration, and preserving heritage across generations.

---

# Concepts

Define the app-level actions as synchronizations of concept actions, and instantiate generic concepts with appropriate types. Draw a dependency diagram showing the possible subsets.

## 1. Post
- **Purpose:** Users can share their thoughts with the greater platform. They can post on community forums for features such as Language Mentor Match (to find people who speak the same language) or Skills Exchange.
- **Operational Principle:** The app sidebar has a "Forums" feature. Click on the forum. Click on a specific forum such as Mentor Match or Skills Exchange. Enter title. Click the plus sign to create a post. Can type text or attach photos. Click post. Anyone else who clicks on that specific forum can view it.
- **State:**
  - `Posts`: a set of posts linked to users.
  - `Visibility`: a set indicating which users can see the post.
- **Actions:**
  - `Create Post`: allows users to enter text and attach multimedia.
  - `View Post`: enables users to see the contents of a post.

## 2. Reply
- **Purpose:** Users can reply to other items.
- **Operational Principle:** Anyone (poster or other users) who clicks on the item can see the item and the comments. Users can engage in modular conversations about a certain topic without having to repost every time.
- **State:**
  - `Replies`: a set of replies linked to each post.
  - `Thread Visibility`: indicating which replies are visible to users.
- **Actions:**
  - `Add Reply`: allows users to respond to a post.
  - `View Replies`: enables users to see responses to a post.

## 3. Authenticate
- **Purpose:** Authenticate users so that app users correspond to real people.
- **Operational Principle:** After a user registers with a username and password pair, they can authenticate as that user by providing the pair.
- **State:**
  - `User Credentials`: a set of username and password pairs.
  - `Authentication Status`: indicating whether a user is authenticated.
- **Actions:**
  - `Register`: allows new users to create an account.
  - `Login`: enables users to authenticate their credentials.

## 4. Session
- **Purpose:** Enable authenticated actions for a period of time.
- **Operational Principle:** After a session starts for a user, and as long as it is active, we can identify that user as associated with the session.
- **State:**
  - `Active Sessions`: a set of currently active user sessions.
  - `Session Timeout`: a timer indicating when a session will expire.
- **Actions:**
  - `Start Session`: initiates a session for the authenticated user.
  - `End Session`: terminates the session after inactivity.

## 5. Calendar
- **Purpose:** Scheduling events with other users such as cultural celebrations, language practice sessions, skill exchange calls, or just family hangouts/events.
- **Operational Principle:** Users can add an item to an integrated Google Calendar (or a simple in-app calendar feature, undecided yet) and make it public to other users.
- **State:**
  - `Events`: a set of scheduled events that users can see.
  - `User Access`: indicating which users have access to specific events.
- **Actions:**
  - `Add Event`: allows users to create new events.
  - `Delete Event`: enables users to remove existing events.

## 6. Groups
- **Purpose:** Increasing privacy and fostering tight-knit communities of family and friends makes a language or generational barrier more approachable to overcome.
- **Operational Principle:** The creator of a group can invite up to 10 people. These 10 people have access to all features to interact with each other.
- **State:**
  - `Group Membership`: a set indicating which users belong to which groups.
  - `Group Content`: a set of posts and calendar events accessible only to group members.
- **Actions:**
  - `Create Group`: allows users to form a new group and invite members.
  - `Invite Members`: enables the creator to send invitations to potential group members.

# Dependency Diagram & Synchronizations

Users can only see the calendars and posts of the groups that they are in. Users must be authenticated and in a valid session to be able to access features and other people in their group.

If using Google Calendar integration, the calendar concept will be synced to Google login. If using an in-app calendar, users will be able to link forum conversations (i.e., planning an event) to the calendar feature.

A session is the amount of time for which a user is authenticated. All other concepts are synced and only viewable during a valid, ongoing session.

 A user must be authenticated to enter a valid session. Authentication is also synced to other concepts such as posts.

 Users can add replies to the post concept as seen in the forums feature.

Users can add replies to the post concept as seen in the forums feature.

# Wireframes
### Here is a link to my Figma wireframe! Below is a screenshot of the flows between different frames.
Link: https://www.figma.com/design/IsYOPFe29EHQsblz2lNcdw/genspeak?node-id=0-1&t=WvlEejT9MctX4iCc-1
This wireframe demonstrates all six concepts: authentication (and session, which is connected), post, reply, groups, and calendar.
![wireframe.png](wireframe.png)



# Design tradeoffs.
(300 words total)
## Decision 1: [pithy title here]
Various options:
Why I chose this option over others:
## Decision 2 [pithy title here]
Various options:
Why I chose this option over others:
## Decision 3 [pithy title here]
Various options:
Why I chose this option over others:
