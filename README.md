# Task description

## Annotation

The aim of the task is to create a multithread server for TCP/IP communication and implement a communication protocol according to a given specification. Attention, implementation of the client part is not part of the task! The client part is realized by the test environment.

## Assignment

Create a server for automatic control of remote robots. The robots themselves apply to the server and guide them to the center of the coordinate system. For testing, each robot starts at random coordinates and tries to reach the coordinate [0.0]. The robot must pick up the secret at the target coordinate. On the way to the goal, robots may come across obstacles that they have to bypass. The server can navigate multiple robots at a time and implement the communication protocol flawlessly.

## Detailed specification

Communication between the server and robots is realized by a fully text protocol. Each command ends with a pair of special symbols "\a\b". (They are two characters '\a' and '\b'.

### Server Messages:

|  Name | Message | Description |
|---|---|---|
| SERVER_CONFIRMATION | <16-bit number in decimal notation>\a\b | Message with confirmation code. It can contain a maximum of 5 numbers and the termination sequence\a\b. |
| SERVER_MOVE | 102 MOVE\a\b | Command to move by one field forward |
| SERVER_TURN_LEFT | 103 TURN LEFT\a\b | Command to turn left |
| SERVER_TURN_RIGHT | 104 TURN RIGHT\a\b | Command to turn right |
| SERVER_PICK_UP | 105 GET MESSAGE\a\b | A message to pick up a message |
| SERVER_LOGOUT | 106 LOGOUT\a\b | Communication command after successful collection of message |
| SERVER_KEY_REQUEST | 107 KEY REQUEST\a\b | Server request for Key ID for communication |
| SERVER_OK | 200 OK\a\b | Positive confirmation |
| SERVER_LOGIN_FAILED | 300 LOGIN FAILED\a\b | Failed authentication |
| SERVER_SYNTAX_ERROR | 301 SYNTAX ERROR\a\b | Incorrect Message Syntax |
| SERVER_LOGIC_ERROR | 302 LOGIC ERROR\a\b | A message sent in a bad situation |
| SERVER_KEY_OUT_OF_RANGE_ERROR | 303 KEY OUT OF RANGE\a\b | Key ID is not in the expected extent |

# Job title: Multithreaded server for TCP/IP
