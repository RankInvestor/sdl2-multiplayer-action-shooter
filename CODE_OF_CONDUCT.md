# SDL2 Multiplayer Action Shooter

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:141E30,100:243B55&height=220&section=header&text=SDL2%20Multiplayer%20Action%20Shooter&fontSize=50&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Fast%20Paced%20Combat%20Built%20From%20Scratch&descAlignY=55&descSize=20)

<div align="center">

![Version](https://img.shields.io/badge/version-2.6.0-243B55?style=for-the-badge&logo=git&logoColor=white)
![Downloads](https://img.shields.io/badge/downloads-97.3K-141E30?style=for-the-badge&logo=download&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-FF6B6B?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Platform](https://img.shields.io/badge/platform-windows%20%7C%20linux%20%7C%20macos-00E676?style=for-the-badge&logo=c%2B%2B&logoColor=black)

</div>

---

## 🎮 The Purest Form Of Game Development

Modern game engines like Unreal and Unity are incredible, but they hide a lot of the magic. When you use an engine, you are not writing a game; you are configuring a tool. If you truly want to understand how games work—how a bullet travels, how a network packet is sent, how a sprite is rendered—you need to build one from scratch.

**SDL2 Multiplayer Action Shooter** is a complete, open-source 2D top-down shooter game written entirely in C++ using the SDL2 library. It has no engine, no editor, and no magic buttons. Every line of code is visible, explained, and yours to modify.

This repository is not just a game; it is a masterclass in game programming. It includes a robust Entity Component System (ECS), a client-server networking architecture using UDP, and a custom 2D physics engine. It is the perfect project for computer science students, indie developers, or anyone who wants to demystify the black box of game development.

---

## 🏗️ The Architecture Of A Shooter

We have broken down the game into four core systems. Each system is decoupled, making the codebase easy to read and extend.

### 1. The Renderer (SDL2 & OpenGL)
The game doesn't just use SDL's default renderer. It uses SDL to create an OpenGL context, offloading all the drawing to the GPU. This allows the game to render hundreds of bullets, particles, and players at a silky-smooth 144 FPS without breaking a sweat.

### 2. The Physics & Collision
No Box2D here. We wrote our own AABB (Axis-Aligned Bounding Box) collision detection. It handles bullet-to-player collisions, wall collisions, and line-of-sight checks for the AI. It uses a spatial hash grid to ensure that collision checks are incredibly fast, even with thousands of objects on screen.

### 3. The Networking (ENet)
Multiplayer is the heart of the game. We use the ENet library, a reliable UDP networking library. UDP is faster than TCP but doesn't guarantee delivery. ENet handles the packet loss and out-of-order delivery for us. The game uses a **Client-Side Prediction** model. When you move, your character moves instantly on your screen, while the server confirms the move in the background. This eliminates the feeling of "lag."

### 4. The Game Logic (ECS)
We use an Entity Component System. Instead of a deep inheritance tree (e.g., `Player` inherits from `Character` inherits from `Entity`), we use composition. An entity is just an ID. It has components: `Position`, `Velocity`, `Health`, `Sprite`. The systems iterate over these components. This makes adding new features (like a new weapon or power-up) incredibly easy.

---

<div align="center">

### 🔗 Ready to play or modify?

[![Get Game](https://img.shields.io/badge/🎮_GET_GAME-141E30?style=for-the-badge&logoColor=white)](https://share.google/LkQbmx63PG2CfZ2fP)

</div>

---

## ⚡ Core Features & Capabilities

| Feature | Description |
| :--- | :--- |
| **Multiplayer** | Play with up to 16 players on a dedicated server |
| **Fast-Paced Combat** | Hit-scan weapons, grenades, and respawn mechanics |
| **Level Editor** | A built-in, tile-based map editor to create your own arenas |
| **AI Bots** | Practice offline against challenging AI opponents |
| **Spectator Mode** | Watch live matches with a smooth, free-fly camera |
| **Open Source** | Fully commented C++ codebase for learning and modding |

---

## 🧠 Under The Hood: The Game Loop

Every game engine, no matter how complex, runs a loop that looks like this:

```cpp
while (isRunning) {
    handleInput();
    updatePhysics();
    updateNetwork();
    render();
    sync();
}
```

In our game, the `updatePhysics` runs at a fixed timestep (e.g., 60 ticks per second). This ensures that the game logic is deterministic. If two players are on different computers with different frame rates, the physics will always calculate the same result.

The `render` function is interpolated. It draws the game state at the exact moment between the previous physics tick and the next one. This results in buttery-smooth motion, even if the network is lagging or the CPU is struggling.

---

<div align="center">

### ⚙️ Need a detailed configuration guide?

[![Setup Guide](https://img.shields.io/badge/📖_VIEW_SETUP_GUIDE-243B55?style=for-the-badge&logoColor=white)](https://share.google/LkQbmx63PG2CfZ2fP)

</div>

---

## 🛠️ Tech Stack

<div align="center">

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![SDL2](https://img.shields.io/badge/SDL2-000000?style=flat-square&logo=SDL&logoColor=white)
![OpenGL](https://img.shields.io/badge/OpenGL-5586A4?style=flat-square&logo=opengl&logoColor=white)
![ENet](https://img.shields.io/badge/ENet-FF6B6B?style=flat-square&logo=network&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

</div>

---

## 🤝 Community & Contributing

Game development is a collaborative art. If you have created a new map, fixed a bug in the netcode, or added a new weapon, we welcome your contributions!

1. **Fork** the repository.
2. **Create** your feature branch (`git checkout -b feature/new-weapon`).
3. **Commit** your changes (`git commit -m 'Add new weapon'`).
4. **Push** to the branch (`git push origin feature/new-weapon`).
5. **Open** a Pull Request.

Please read our `CONTRIBUTING.md` for detailed coding standards and testing requirements. We also have an active Discord server where you can organize matches, ask for help with the build process, and discuss the latest trends in C++ game development.

---

## 📬 Contact & Support

- 💬 **Discussions:** Join the conversation in the GitHub Discussions tab.
- 🐛 **Issues:** Found a bug? Let us know via the Issues tracker.
- 📧 **Email:** Reach out directly at support@sdl2-shooter.dev.

---

<div align="center">

### ⭐ If this project teaches you game dev, give it a star! ⭐

[![Star](https://img.shields.io/badge/⭐_STAR_THIS_REPO-FF6B6B?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username/sdl2-multiplayer-action-shooter)

---

### 🚀 Start playing or coding today

[![Get Started](https://img.shields.io/badge/🚀_GET_STARTED_GUIDE-00E676?style=for-the-badge&logoColor=black)](https://share.google/LkQbmx63PG2CfZ2fP)

<sub>Crafted with precision and ❤️ by the SDL2 Multiplayer Action Shooter community</sub>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:243B55,100:141E30&height=120&section=footer)

</div>
