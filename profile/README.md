# AirView: Share Screen with others

<div align="center">
  <img src="https://github.com/TeleCAUm/.github/assets/25452313/913f17ae-c5ef-4791-823f-3c100480f267" alt="Mar-27-2024 11-45-26">
</div>

## Motivation
Video services like `Zoom` and `Google meet` only allow you to **share one screen at a time**, because they're **designed for video conferencing**, not screen sharing. As people increasingly share their screens to collaborate each other, this limitation has become an annoyance.

**`AirView` solves these problems.** `Airview` is a service for screen sharing! 

## Features
| ![Main](https://github.com/TeleCAUm/.github/assets/25452313/015929e5-4eb5-458a-8193-0bd14b6dd2c1) | ![Drawing](https://github.com/TeleCAUm/.github/assets/25452313/d898d3c3-63a8-49e4-9ac0-b1ddc395ed22) |
|:------------------------------------------:|:--------------------------------------------:|
|                    Main                    |                   Drawing                    |
| ![Focus view](https://github.com/TeleCAUm/.github/assets/25452313/de52ad94-44f5-4467-9f45-901c8aae68b4) | ![Tile view](https://github.com/TeleCAUm/.github/assets/25452313/733d0e8c-a8e2-4d47-a6ec-ba8a034133c4) |
|                  Focus view                |                   Tile view                  |

It supports the following features:
- __Screen Sharing__: View work on each other's devices without the need for extra monitor
- __Quick Screen Switching__: Switch screens ridply when you want to see multiple users' screens at a glance or focus on one selected screen.
- __Drawing__: Draw on the screens when you want to provide feedback.

## Architecture
![image](https://github.com/TeleCAUm/.github/assets/25452313/f0a49df4-048a-4656-9dd1-14b60cdd3e75)
* Uses `Typescript`, `React`, `WebRTC` for client screen sharing and `Java(Swing)` and `SocketIO` for drawing
* You can find how to setup the project in each repository!

## Issues
> Below are some of the challenges our TeleCAUm team faced during the development process.

* Debugging was difficult due to the large number of programs involved in the communication process
	- WebRTC: signaling server, STUN/TURN, each client
	- Socket.IO: Participant socket, Host socket
* Drawings are drawn in the wrong place.
	- One can draw on the other's screen by drawing on an HTML Canvas on top of an HTML Video, and if the Video contains margin values, the coordinate values of the Canvas and the coordinate values of the Video do not correspond one-to-one. This results in the drawing being drawn in the wrong place.
  - This is a limitation of web-based screen sharing, not native apps like Zoom.
* In order to actually deploy the project, we had to deploy all the servers of the WebRTC architecture (STUN/TURN, signaling server), so it currently only works within the LAN.

## Achievement
* Unlike other screen sharing platforms (Zoom, Google meet), you can see multiple screens at the same time and switch between screens very easily
* Collaborate by drawing on the other person's screen
> earned an A+ in Fall 2023 Capstone Design class, Chung-Ang University, South Korea.

## Contributing
> It was made as a short-term project for 2 months, so there are a lot of imperfections. However, the idea is good and it works. I hope you guys can take a look at this code and build something bigger. If you want to contribute, please see each repository :)



