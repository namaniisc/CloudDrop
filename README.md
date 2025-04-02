# File Sharing Web App

A file-sharing application that lets users upload any file, generates a unique download link, and optionally sends the link via email.

## Overview

- **File Upload & Sharing:**  
  Upload files to generate a unique, shareable download link.
  
- **Email Integration:**  
  Option to email the download link to a recipient.

## Features

- **Upload Endpoint:**  
  Accepts file uploads (using middleware like multer), generates a unique UID (using UUID), and stores the file in a designated folder.
  
- **Download Endpoint:**  
  Retrieves the file using its UID. Constructs the file path dynamically and serves it via methods such as `response.download()`.
  
- **Email Sharing:**  
  Validates email inputs and sends download links using Nodemailer with SMTP configuration.
  
- **Static Files & Front-End:**  
  Serves static assets (HTML/CSS/JS) from a public folder. The front-end provides an interface for uploading and downloading files.

- **Database Integration:**  
  Connects to a MongoDB instance (using Mongoose) to store file details (file name, path, size, UID, sender, receiver, and timestamps).

- **Scheduled Cleanup:**  
  A scheduled task (using cron jobs or Heroku Scheduler) automatically deletes files and their records once they expire.

## Project Structure

- **models/**  
  Contains the file model (e.g., `file.js`) with schema definitions.

- **routes/**  
  Defines API endpoints for uploading and downloading files.

- **public/**  
  Contains static assets (HTML, CSS, JS) for the front-end.

- **config/**  
  Holds configuration files for database connection and environment variables (using `.env` for sensitive data).
