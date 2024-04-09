# Rocket.Chat_ES_Natali_Flores

Username: natali.regina@outlook.com
Password: 220717Hs@

How to Install and Setup your RocketChat by Docker.

First download Docker, using this link:

https://www.docker.com/products/docker-desktop/

![image](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/8c49c3f4-5371-49ff-a35a-542b88a43a5d)

After downloading, run the file. Don't forget to enable virtualization in your BIOS. ( In my case I used the default configuration in Docker.)

After downloading and configuring Docker, you will open Windows PowerShell:

![image](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/936c2148-2630-4c76-b02a-1876e169208c)

The first command will be to create a Docker network:

docker network create rocketchat-network

The second will be used to get the Rocket.chat and MongoDB images, run them one at a time:

docker pull rocketchat/rocket.chat:preview
docker pull mongo:7

The next command will let you start a MongoDB container called mongo on the rocketchat-network:

docker run -d --name mongo --network rocketchat-network mongo:7

![rocketchat](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/8f1de8c6-fc6d-44ab-8fed-fe702e2bac75)

The next command will start the Rocket.chat container, linking it to the MongoDB container:

docker run -d --name rocketchat --network rocketchat-network -p 3000:3000 `

--env MONGO_URL="mongodb://mongo:27017/rocketchat" `

--env ROOT_URL="http://localhost:3000" `

rocketchat/rocket.chat:latest `

After following these steps, open your CMD and run the following command:

docker run -it --rm -p 3000:3000 rocketchat/rocket.chat.preview


Now your CMD should look like the image below:

![image](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/166e18a6-8447-42fb-8e9a-6d6dd387cd39)


And finally let's access Rocket.chat using this URL:

http://localhost:3000

After creating the user you can access this link where you will be redirected to this page:

![image](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/353aa5b7-49c2-44fb-8b62-4d41db6132ab)



APIs Test:

1. Create a new user via an API endpoint:

![Resposta API User](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/26cd7e40-1968-483f-be4d-c839bdb6bdb2)

2. Get the room information via an API endpoint:

![Request API Rooms](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/af3c869a-9241-4241-868d-98c1e1524675)

3. Get a list of all user roles in the system via an API endpoint:

![Request API Roles](https://github.com/NataliRegina/Rocket.Chat_ES_Natali_Flores/assets/166416048/32e54a48-1633-476b-897c-9ce9c72a26b8)

Thank you for reading,

             Bye Bye.












