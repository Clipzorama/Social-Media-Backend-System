# Social-Media-Backend-System

## Overview

This project is a backend system for a social media platform developed using Spring Boot, Hibernate, and Spring Data JPA. It is designed to manage and persist data related to users, profiles, posts, comments, likes, and follower relationships. The application offers a robust set of RESTful APIs tested with Postman and utilizes a MySQL database for data storage.

## Features

- **User Management**: Create and manage user accounts.
- **Profile Management**: Create and update user profiles.
- **Posts and Comments**: Create, retrieve, and manage posts and comments.
- **Likes**: Like and unlike posts and comments.
- **Followers**: Follow and unfollow users.
- **Security**: Password hashing and user authentication.
- **API Documentation**: Detailed API documentation using OpenAPI.

## Technologies Used

- **Spring Boot**: Framework for building the application.
- **Spring Data JPA**: Abstraction over JPA to work with different databases.
- **Hibernate**: ORM tool for mapping Java objects to database tables.
- **MySQL**: Database for storing user, profile, post, comment, and relationship data.
- **Postman**: Tool for testing RESTful APIs.

## Project Structure

src/main/java
│
├── edu.lawrence.media
│ ├── MediaApplication.java
│ ├── entities
│ │ ├── Comment.java
│ │ ├── Like.java
│ │ ├── Post.java
│ │ ├── Profile.java
│ │ └── User.java
│ ├── interfaces
│ │ ├── CommentController.java
│ │ ├── LikeController.java
│ │ ├── PostController.java
│ │ ├── ProfileController.java
│ │ └── UserController.java
│ ├── interfaces.dtos
│ │ ├── CommentDTO.java
│ │ ├── LikeDTO.java
│ │ ├── PostDTO.java
│ │ ├── ProfileDTO.java
│ │ └── UserDTO.java
│ ├── repositories
│ │ ├── CommentRepository.java
│ │ ├── LikeRepository.java
│ │ ├── PostRepository.java
│ │ ├── ProfileRepository.java
│ │ └── UserRepository.java
│ └── services
│ ├── CommentService.java
│ ├── DuplicateException.java
│ ├── LikeService.java
│ ├── PasswordService.java
│ ├── PostService.java
│ ├── ProfileService.java
│ └── UserService.java
│
├── resources
│ └── application.properties


## Database Schema

The database schema includes the following tables:

- **users**: Stores user account information.
- **profiles**: Stores profile details for users.
- **posts**: Stores posts made by users.
- **comments**: Stores comments on posts.
- **likes**: Stores likes on posts and comments.
- **profiles_followers**: Stores follower relationships between profiles.
- **profiles_following**: Stores following relationships between profiles.

## API Endpoints

### User Endpoints

- `POST /users` - Create a new user.
- `POST /users/login` - Login a user.

### Profile Endpoints

- `POST /profiles/{id}` - Create a new profile.
- `GET /profiles/{username}` - Get a profile by username.
- `POST /profiles/archive/{profileid}/{userid}` - Archive a profile.
- `POST /profiles/follow/{followerid}/{username}` - Follow a user.
- `POST /profiles/unfollow/{followerid}/{username}` - Unfollow a user.

### Post Endpoints

- `POST /posts` - Create a new post.
- `GET /posts/{postid}` - Get a post by ID.
- `GET /posts/user/{username}` - Get posts by username.
- `POST /posts/archive/{postid}/{userid}` - Archive a post.

### Comment Endpoints

- `POST /comments` - Create a new comment.
- `GET /comments/{postid}` - Get comments by post ID.
- `POST /comments/archive/{commentid}/{userid}` - Archive a comment.

### Like Endpoints

- `POST /likes` - Like a post or comment.
- `GET /likes/{postid}/quantity` - Get like count by post ID.
- `GET /likes/{postid}/dislikes` - Get dislike count by post ID.
- `GET /likes/{postid}/likes` - Get likes by post ID.
- `GET /likes/{postid}/dislikes` - Get dislikes by post ID.

## Getting Started

### Prerequisites

- Java/JDK 22 or higher
- Maven
- MySQL

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/Social-Media-Backend-System.git
   cd Social-Media-Backend-System

## Testing
Use Postman to test the APIs. Import the provided Postman collection to get started quickly.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue to discuss your ideas.
