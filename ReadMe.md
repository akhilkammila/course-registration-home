Configurations
- webpageBaseUrl in docker-compose needs to be set to the domain that the frontend is accessed at (for CORS, and for emails to work properly)
- need to build the frontend & backend images


Prev
frontend pings backend at link: http://127.0.0.1:5000 locally, need public endpoint for prod
backend has url of frontend: http://127.0.0.1:3000 locally, need public endpoint for prod
backend connects to db container with uri: postgresql://user:password@db:5432/course_registration