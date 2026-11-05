Avarren Showcase

Built and maintained by Austin Alberts.

Avarren is an original multiplayer RPG I am building in Java. It runs on its own engine: a game server that owns every decision, an OpenGL client, a world editor, and the tools behind them. The game is still in development, and no beta or release date has been announced.

This repository shares short videos of the game and selected pieces of its code. The project repository itself stays private.

Language: Java 21
Build: Maven, ten modules (core, protocol, server, client, plugin API, world editor, asset studio, launcher and more)
Graphics: OpenGL 3.3 through LWJGL
Testing: JUnit 5, 1,227 automated tests

**The Game**



**Lands**



Four places in the game: the first city with its castle on a rock above the market square, a royal castle, a village at the foot of the mountains, and a desert city.

https://github.com/user-attachments/assets/398417dc-87f9-428b-aac1-92b78a65082d



**Creatures**

Creatures with their own skeletons and animations, played as they are stored in the game's files: idle, walking, attacking, flinching and dying.

https://github.com/user-attachments/assets/7946963b-e622-4b9e-b218-d33e53f017b7




**Skills**

Skills are built to depend on one another. Ore is smelted into bars and forged into armour, logs feed the fire that cooks the fish, and grain is milled, mixed and baked into bread.

https://github.com/user-attachments/assets/4976ee23-e51b-49e2-8701-d6de053ce1d7




**Staff and Moderation**

Four ranks: player, moderator, admin and owner. Staff can only act on ranks below their own, staff accounts must use an authenticator, reports stay private, and every staff action is written to a signed log.

https://github.com/user-attachments/assets/4300ec45-92a7-4d3c-896d-db842d508d6f



**Two Players, Chat and Trading**

Recorded in the game on a local test world with two test accounts. Two players meet in the market square, talk in public chat, and trade a hammer for a net. Both offers show side by side, any change resets acceptance, and a final screen shows exactly what each player gives and receives before anything moves.

https://github.com/user-attachments/assets/f2e7acc1-a724-4239-b4d7-1cf9da5dfc63




**Under the Hood**

Code shown in these videos is taken from the project as written. Long lines are wrapped so they can be read on screen.

Part one: The 100 ms server tick, per-connection request limits, trades that save both players in one step, password hashing, map updates that never undo hand edits, and a trade test.

https://github.com/user-attachments/assets/39b44748-8bb1-45c4-997f-2eae7c3342b7



Part two: Game content running on the server's clock, distance and combat checks before a trade, and tests that step the real game one tick at a time.

https://github.com/user-attachments/assets/b2b3aa64-a969-44e3-aebb-00d55307e993



**How It Works**

A few of the decisions behind the game:

The server owns every decision. The client sends requests. Movement, combat, gathering, banking and trading are checked and carried out by the server on a fixed 100 ms tick.
Items can't be duplicated or lost in a trade. Items stay in each player's inventory until both confirm. Both players are then saved together, and if the server stops partway, it recovers from a journal when it starts again.
Requests are limited per connection. Each type of request has its own limit, checked before the rest of the request is read.
Passwords are never stored. Accounts keep a salted PBKDF2 hash. Players can add an authenticator app, and staff must.
The editor and the game share one world. The world editor saves the same map files the server loads, and a running server picks up saved changes within a few seconds.
Tests run the real game. Tests step the same tick the live server runs, so results are exact and repeatable.
About This Repository

This repository shares selected videos and code from Avarren. The game's source code, art and assets remain private.

Avarren website: avarren.com (not yet live)
Other work: retail-platform-showcase
Contact: info@trippyhippie.org

Copyright

Copyright © 2026 Austin Alberts and Trippy Hippie Wholesale LLC. All rights reserved.

Avarren™, its name, world, characters, art, music and code are not licensed for reuse, redistribution or derivative works. Viewing this repository does not grant any rights to its contents. Third-party materials used in the game remain subject to their own licenses.
