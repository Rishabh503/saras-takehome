# Vue Frontend Project

## About

This is a small Vue frontend project created to demonstrate a basic movie search suggestions using the api https://api.tvmaze.com/search/shows
interface and interaction using Vue.

## Requirements

Before running the project, make sure you have:

- Node.js installed
- npm installed

You can check this with:

node -v npm -v

## Running the Project Locally

1. Clone the repository
   repository link :https://github.com/Rishabh503/saras-takehome

git clone `<repository-link>`{=html}

2. Move into the project folder

cd `<project-folder>`{=html}

3. Install project dependencies

npm install

4. Start the development server

npm run dev

5. Open the project

After running the command, the terminal will show a local address such
as:

http://localhost:5173

Open it in your browser to see the application.

## Scaling or Performance Improvements

If this project needs to grow or handle more users, a few improvements
can be made:

- Use a proper state management tool such as Pinia
- Implement lazy loading for routes if we have any
- Separate API calls into service files
- Use build optimization for production
