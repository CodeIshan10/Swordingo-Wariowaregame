# Swordingo-Wariowaregame

A rapid-fire, **WarioWare-inspired microgame collection** set in a side-scrolling fantasy world. Face an onslaught of 5-second minigames where you must hack, slash, dodge, and spell-cast your way through danger before the timer runs out!

## 🚀 Key Features

* **Rapid Action:** Randomly generated microgames that must be solved in under 5 seconds.
* **Fantasy Aesthetic:** Inspired by classic platformers with dungeons, magical spells, and swordplay.
* **Dynamic Escalation:** The game loops continuously, scaling up the speed and difficulty as your score climbs.
* **Robust Core Loop:** Built using an state-driven manager to effortlessly handle live tracking, speed shifts, and dynamic game spawning.

---

## 🕹️ Sample Microgames

| Microgame | Prompt | Action Required |
| :--- | :--- | :--- |
| **Slash!** | *ATTACK!* | Time your swing perfectly to defeat the incoming Corrupted Blob. |
| **Heal Up** | *DRINK!* | Rapidly mash the interact key to chug a health potion. |
| **Dungeon Dodge** | *DODGE!* | Jump over a rolling spike trap or duck under a flying bat. |
| **Mage Shield** | *DEFEND!* | Cast a magical barrier at the exact frame a fire spell strikes. |

---

## 🛠️ Architecture & Core Logic

The project utilizes a centralized **Game Manager** approach to separate game states from individual microgame logic:

1. **The Manager Object:** Tracks global variables such as remaining player lives, current game speed, and win/loss scoring streaks. 
2. **State Machine:** Rotates the game through sequential phases (`Intro Banner` ➡️ `Spawn Microgame` ➡️ `Win/Loss Fanfare` ➡️ `Speed Up Transition`).
3. **Dynamic Spawning:** Microgames are loaded cleanly into memory as independent scenes or objects. The manager listens for a boolean output (`is_won`) from the active microgame instance before destroying it and moving to the next level.

---

## ⚙️ Installation & Setup

### Prerequisites
* Ensure you have your game engine or runtime environment installed (e.g., Node.js, Godot, Unity, or GameMaker Studio).

### Getting Started
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com
   ```
2. Open the project folder inside your chosen editor or Game Engine.
3. Locate the `Main` or `TitleScreen` scene inside the project directory.
4. Press **Play** or run your start script to test the game!

## ⌨️ Controls

* **A / D** or **Left / Right Arrow:** Move Left/Right
* **Spacebar / W:** Jump
* **J / Left Click:** Attack / Slash
* **K / Right Click:** Cast Spell / Interact

---

## 🤝 Contributing

We welcome custom microgame additions! To add your own game:
1. Fork the project repository.
2. Create a new microgame scene inside the `/Microgames` directory.
3. Inherit from the base microgame script (`BaseMicrogame`) so your code naturally reports its win/loss state back to the central manager.
4. Open a Pull Request detailing your microgame design!

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
