# The Project's Code  

The system is designed by dividing it into three logical components:

1. A **Client** user-agent desktop application.
2. A server that is responsible for authenticating users and starting online games that we call the **Auth Service Server.**
3. A server that is responsible for keeping track of the game’s current state and forwarding messages between users playing a game called the **Tracker.**

These can be found in the following links:

1. [Client](https://github.com/a-elhawary/distributed_car_game_client)
1. [Auth Service Server](https://github.com/AhmedOssamaAhmed/race_game)
1. [Tracker](https://github.com/Ziad-Nasr/2DRacing---Server)

# Why seperate repos?

Since each repo is not dependant on the other repos to exist on the same file.

# Project Description

We have to support different user-agents playing our game. As such each client node should have his/her own car to control. The cars’ and as such game’s state should be distributed over multiple nodes in such a way such that the failure of one node does not affect the game play for the other nodes. It should be possible to recover a node’s state after a crash to be able to continue playing the game where it left off.

As such the simple game, although not that amazing in terms of game play or graphics rendering, starts to become an interesting distributed system.

A user needs to have access to some game GUI. To login/register and to start or join a game. After the user starts a game he would need to send his messages for processing and the results of this processing should be forwarded to all users playing in the same game.

An example for the server-side processing is when a client wants to update his car’s position using the WASD keys. The client simply sends a message such as RIGHT to the server that then processes the new x and y coordinates and sends it over to all interested clients.
