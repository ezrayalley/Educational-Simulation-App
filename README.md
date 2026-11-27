<div align="center">

# 🌍 Educational Simulation App with AI Tutor

### See it. Explore it. Ask about it. Understand it.

An interactive 3D science learning app built in **Unity**, where students experiment with **Day and Night**, **Eclipses** and **Gravity**, then get instant help from a **Gemini-powered AI Tutor**.

![Unity](https://img.shields.io/badge/Unity-3D-black?logo=unity)
![C#](https://img.shields.io/badge/C%23-Scripting-512BD4?logo=csharp&logoColor=white)
![Gemini](https://img.shields.io/badge/Google-Gemini%20API-4285F4?logo=google&logoColor=white)
![Platforms](https://img.shields.io/badge/Platforms-WebGL%20%7C%20Android%20%7C%20Desktop-success)
![Level](https://img.shields.io/badge/Level-High%20School%20Science-orange)

<img src="docs/images/banner.png" alt="Educational Simulation App main menu" width="800"/>

</div>

---

## ✨ Why this app?

Some science ideas are hard to picture from a textbook. Day and night, eclipses and orbits all depend on **3D motion**, and gravity is simply **too abstract** to grasp from static diagrams or whiteboard sketches.

This app makes those ideas **visible and interactive**, and adds an AI tutor so students can ask questions, practise and get feedback in simple language, any time.

---

## 🎮 Features

| | Feature | What it does |
|---|---|---|
| 🌗 | **Day / Night simulation** | Watch Earth's rotation create day, night, sunrise and sunset in real time. |
| 🌑 | **Eclipse simulation** | Explore how the Sun, Moon and Earth line up to form solar and lunar eclipses. |
| 🍎 | **Gravity simulation** | Experiment with gravity and falling motion to see how it behaves. |
| 💬 | **Ask AI Tutor** | Type any question and get a short, simple answer. Off-topic questions are politely redirected. |
| 📝 | **Get Practice Questions** | Pick a topic (Any, Day and Night, Eclipse, Gravity) and receive a fresh AI-generated conceptual question. |
| ✅ | **Get AI Feedback** | Answer the question and learn whether you are correct, partly correct or not yet correct, with a hint instead of a giveaway. |
| 📱 | **Cross-platform** | Runs on WebGL, Android and Desktop. |

### 📸 Screenshots

| Main menu | Celestial Mechanics (Day/Night and Eclipse) |
|:---:|:---:|
| ![Main menu](docs/images/main-menu.png) | ![Celestial Mechanics](docs/images/celestial-mechanics.png) |

| Gravity simulation | GenAI Tutor panel |
|:---:|:---:|
| ![Gravity simulation](docs/images/gravity.png) | ![AI Tutor in use: answer, practice question and feedback](docs/images/ai-tutor-panel.png) |

The **GenAI Tutor Panel** button in each simulation opens the tutor. In the screenshot above, a student asks "how does eclipse occur", generates a Day and Night practice question, and receives feedback on their answer: partly correct, the key idea to remember, and a hint to try again.

---

## 🧠 Learning Journey

```text
Select Simulation → Interact in 3D → Observe the Phenomenon → Ask AI Tutor
        → Get Practice Questions → Receive AI Feedback → Develop Understanding
```

### The pedagogy behind each feature

- **Simulations:** learning by doing lets students *see* rotation, alignment and gravity rather than imagine them, lowering mental load.
- **Ask AI Tutor:** instant, on-demand help scaffolds self-paced learning.
- **Practice Questions:** self-testing (retrieval practice) strengthens memory, and topic choice gives learners control.
- **AI Feedback:** timely formative feedback with hints keeps students thinking and trying again.
- **Cross-platform:** flexible access supports different learning environments.

---

## 🛠️ How it works

```mermaid
flowchart LR
    A[Simulation scenes<br/>Day/Night · Eclipse · Gravity] -->|opens| B[AI Tutor panel<br/>Ask · Practice · Feedback]
    B -->|prompt| C[Prompt builder<br/>AITutor.cs]
    C -->|JSON request| D[(Gemini API<br/>gemini-2.5-flash)]
    D -->|reply| E[Reply handler<br/>parse + typewriter]
    E -->|shown to student| B
```

Each tutor button builds a prompt that fixes the tutor's role, the three-topic scope and a **high school reading level**. The prompt is sent to Gemini as JSON over HTTPS, then the reply is parsed and typed onto the screen.

**Tech stack:** Unity 3D · C# · TextMeshPro · UnityWebRequest · Google Gemini API (`gemini-2.5-flash`)

---

## 🚀 Getting Started

### Prerequisites
- [Unity Hub](https://unity.com/download) and the Unity version used by this project (check `ProjectSettings/ProjectVersion.txt`)
- A free Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

### Run the project
```bash
git clone https://github.com/<your-username>/<your-repo>.git
```
1. Open the folder in **Unity Hub**.
2. Open the AI Tutor scene and select the object with the `AITutor` script.
3. Paste your key into the **Api Key** field in the Inspector.
4. Make sure each tutor button's **On Click** calls `AskQuestion()`, `GenerateQuestion()` or `SubmitAnswer()`.
5. Press **Play**.

### Build
**File → Build Settings →** add all scenes → choose **WebGL**, **Android** or **Windows** → **Build**.

> ⚠️ **Never commit your API key.** Keys pushed to a public repo can be found and disabled by Google. Leave the field empty in the committed project and add the key locally, or load it from a file excluded by `.gitignore`.

---

## ⚠️ Known Limitations

- **AI accuracy:** answers are not grounded in a syllabus and can occasionally be wrong or oversimplified, so a teacher should review them.
- **Internet required for AI features:** the simulations work offline, but the tutor, practice questions and feedback need internet, and sometimes a VPN in regions where Gemini is unavailable.
- **Rate limits:** the API can be rate-limited or slow when many students use it at once.
- **API key in the app:** a key stored in a build can be extracted. A backend proxy is needed for wide release.

---

## 🔮 Future Improvements

- 📚 **RAG** so AI answers are grounded in the syllabus
- 🧩 Additional interactive learning activities
- 🥽 Extend to **AR / VR**

---

## 👥 Team

| Member | Contribution |
|---|---|
| **Ezra Yalley** | Development, programming, UI/UX design |
| **Eva** | Development and design |
| **Alan** | Documentation |
| **Moe** | Testing and slide preparation |

---

## 📄 License

Add your license here (for example MIT) and include a `LICENSE` file.

<div align="center">

⭐ If you find this project useful, please give it a star! ⭐

</div>
