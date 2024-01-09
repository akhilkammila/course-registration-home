Configurations
- webpageBaseUrl in docker-compose needs to be set to the domain that the frontend is accessed at (for CORS, and for emails to work properly)
- need to build the frontend & backend images


Prev
frontend pings backend at link: http://127.0.0.1:5000 locally, need public endpoint for prod
backend has url of frontend: http://127.0.0.1:3000 locally, need public endpoint for prod
backend connects to db container with uri: postgresql://user:password@db:5432/course_registration


Setting up on ec2:

connecting: ssh -i "course-registration-1.pem" ec2-user@ec2-3-94-119-219.compute-1.amazonaws.com

In EC2 instance folder:

copy code -
scp -r -v -i /Users/akhilkammila/Desktop/"EC2 Instances"/course-registration-1.pem /Users/akhilkammila/Projects/gt-registration-home ec2-user@ec2-3-94-119-219.compute-1.amazonaws.com:/home/ec2-user

nginx files -
scp -r -v -i /Users/akhilkammila/Desktop/"EC2 Instances"/course-registration-1.pem /Users/akhilkammila/Projects/gt-registration-home/nginx/frontend.conf ec2-user@ec2-3-94-119-219.compute-1.amazonaws.com:/home/ec2-user

scp -r -v -i /Users/akhilkammila/Desktop/"EC2 Instances"/course-registration-1.pem /Users/akhilkammila/Projects/gt-registration-home/nginx/backend.conf ec2-user@ec2-3-94-119-219.compute-1.amazonaws.com:/home/ec2-user

pem: /Users/akhilkammila/Desktop/"EC2 Instances"/course-registration-1.pem
files: /Users/akhilkammila/Projects/course-registration-bot

Nginx configuration:

Bring up one service:
docker-compose up -d backend