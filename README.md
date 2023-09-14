# Instagram-Clone

 Instagram-Like Database Schema

This repository contains the SQL database schema for an Instagram-like social media platform. The schema defines the structure of the database, including tables, relationships, and key attributes.

## Tables

### Users
- `id` (Primary Key): Unique identifier for each user.
- `username`: The username of the user.
- `created_at`: Timestamp indicating the user's registration date.

### Photos
- `id` (Primary Key): Unique identifier for each photo.
- `image_url`: URL of the image associated with the photo.
- `user_id` (Foreign Key): References the user who posted the photo.
- `created_dat`: Timestamp indicating the photo's creation date.

### Comments
- `id` (Primary Key): Unique identifier for each comment.
- `comment_text`: The text of the comment.
- `user_id` (Foreign Key): References the user who left the comment.
- `photo_id` (Foreign Key): References the photo the comment is on.
- `created_at`: Timestamp indicating the comment's creation date.

### Likes
- `user_id` (Foreign Key): References the user who liked a photo.
- `photo_id` (Foreign Key): References the liked photo.
- `created_at`: Timestamp indicating when the like was made.
- Composite Primary Key: `(user_id, photo_id)` to prevent duplicate likes.

### Follows
- `follower_id` (Foreign Key): References the user who is following.
- `followee_id` (Foreign Key): References the user being followed.
- `created_at`: Timestamp indicating when the follow action occurred.
- Composite Primary Key: `(follower_id, followee_id)` to represent follower-followee relationships.

### Tags
- `id` (Primary Key): Unique identifier for each tag.
- `tag_name` (Unique): The name of the tag.
- `created_at`: Timestamp indicating when the tag was created.

### Junction Table: Photo_Tags
- `photo_id` (Foreign Key): References a photo associated with a tag.
- `tag_id` (Foreign Key): References a tag associated with a photo.
- Primary Key: `(photo_id, tag_id)` to establish a many-to-many relationship between photos and tags.

## Relationships

- Users can post multiple photos, leave multiple comments, like multiple photos, and follow other users.
- Photos can have multiple comments, likes, and tags associated with them.
- Tags can be associated with multiple photos.

## Usage

This database schema serves as the foundation for an Instagram-like social media platform. It allows users to create accounts, post photos, leave comments, like photos, follow other users, and associate tags with photos.

## Contributing

If you wish to contribute to this project, feel free to fork the repository, make changes, and submit pull requests. Contributions and improvements are welcome!
