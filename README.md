# RafBook-Android

An Android application that enables students to communicate via text, images, videos, and audio messages. The app features organized channels for different courses, departments, and academic years, along with notifications and optional video/audio calling capabilities. This app is built with Kotlin and connects to a Java Spring backend.

---
## Features
- **Real-Time Messaging**: Send and receive text, image, and video messages instantly.
- **Organized Channels**: Communication channels for specific courses, departments, and academic years.
- **Notifications**: Broadcast notifications for important updates.
- **User Management**: Role-based access control with roles for admin, professor, and student.
- **Optional Video/Audio Calls**: Supports video and audio calls between users.
- **JWT Authentication**: Secure authentication using JSON Web Tokens (JWT).
- **MAC Address Verification**: Required for user registration to verify device identity.

---

## Technologies
- **Kotlin** (Android Development)
- **Jetpack Compose** / **XML** (for the UI)
- **Firebase** (for push notifications)
- **WebSocket** (for real-time messaging)
- **ExoPlayer** (for media playback)
- **Room** (for local data caching if needed)

## Requirements
- Android 7.0 (Nougat) and above
- Android Studio Bumblebee or higher

---

## Features and Usage

### 1. **Authentication**
   - **Register**: Users register with a username, password, and MAC address (for device-specific verification).
   - **Login**: Authenticate using a username and password to obtain a JWT token for secure access.

### 2. **User Interface**
   - **Channels Screen**: Displays all channels available to the user, organized based on user roles (e.g., courses, departments).
   - **Chat Screen**: Shows real-time messages in the selected channel, with options to send text, images, and videos.
   - **Notification Screen**: Lists broadcast notifications sent to the user for important updates.

### 3. **Messaging**
   - **Send Messages**: Allows users to send text, image, and video messages in real time to specific channels.
   - **Receive Messages**: Provides real-time updates in the active channel via WebSocket.
   - **Caching**: Locally caches recent messages for offline viewing, allowing users to access conversation history even without internet.

### 4. **Notifications**
   - **View Notifications**: Displays all system-wide notifications broadcasted to the user.
   - **Push Notifications**: Enables users to receive updates via push notifications, even when the app is in the background.

### 5. **Optional Video/Audio Communication**
   - **Initiate Call**: Allows users to start a video or audio call with other users (if supported).
   - **Receive Call**: Accept incoming calls with video and audio options.

### 6. **Settings**
   - **User Profile**: Allows users to update profile information.
   - **Logout**: Clears the JWT token and logs the user out, ensuring secure access.

---

## Security

- **JWT Authentication**: Ensures secure access to API endpoints, requiring users to authenticate and obtain a JWT token.
- **Role-Based Access Control**:
   - **Admin**: Full access, including managing users and channels.
   - **Professor**: Access to manage channels related to their courses.
   - **Student**: Access to view and interact within allowed channels.
- **MAC Address Verification**: Required during registration to verify the device, adding an additional layer of security.

---

## Testing

### Unit Tests
- **Testing Framework**: JUnit and Mockito.
- Tests for individual components, such as network requests, view models, and repository functions, to ensure isolated functionality works as expected.

### UI Tests
- **Testing Framework**: Espresso.
- Automated UI testing for essential user flows, including login, sending messages, and receiving notifications to ensure a seamless user experience.

### Integration Tests
- **Testing Framework**: Cucumber (if behavior-driven testing is needed).
- Tests API calls and WebSocket connections for end-to-end functionality, ensuring smooth interaction across the app's various components.
