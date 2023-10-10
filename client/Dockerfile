#Use Node Alpine as Base Image
FROM node:alpine3.18

# Specify Working directory
   #Create The directory
RUN mkdir -p /moringa/devops04/ip2/ui
   #point to the Working directory
WORKDIR /moringa/devops04/ip2/ui

# Copy Everything to the working directory
COPY  . /moringa/devops04/ip2/ui/
# Installing the dependencies
RUN npm install 




#  Run the application on docker run 
CMD ["npm", "start"]