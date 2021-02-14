# Multiple Minecraft Bedrock server using docker-compose
Run multiple Minecraft Bedrock servers using Docker

This is an addon to the Docker implementation by itzg enabling multiple Minecraft Bedrock servers, all on the default port (19132).
Begin by reading itzg/minecraft-bedrock-server: https://hub.docker.com/r/itzg/minecraft-bedrock-server

Now, in stead of using the docker run, we'll be using docker-compose. 
A docker macvlan network will be created which will allow the containers to each get their own ip-address. This trick will allow the servers to have the default port, allowing them to show up in Minecraft-clients.

Create the following folders:
minecraft
minecraft\minecraft1
minecraft\minecraft2
etc. (depending on the number of servers you're looking for)

Save the docker-compose.yml to the minecraft-folder and customize:
- choose random mac-addresses (generate, or be creative)
- choose the IP-addresses you want the containers to have. These should be free on your router.  
- choose environment variables to customize the Minecraft-server

now use:
docker-compose up -d

If you want you can still make changes to the server.properties (Minecraft file), stop the containers, edit en rerun. 
