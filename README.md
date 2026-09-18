# EV-olution 🚗⚡

A modern and responsive electric vehicle landing page built with **React.js** and **Vite**.

The project focuses on creating a visually engaging EV website using React components, background videos/images, automatic background transitions, navigation controls, and CSS animations.

---

## 📸 Screenshots

### The Landing-Page

![EV-olution Home Page](../screenshots/homePage.png)
![EV-olution Home Page video](../screenshots/homePageVideo.png)

---

## ✨ Features

- ⚡ Modern electric vehicle themed landing page
- 🎬 Full-screen background video
- 🖼️ Background image transitions
- ⏱️ Automatic background change every 3 seconds
- 🎨 Smooth background transition animation
- ▶️ Play/Pause video functionality
- 🔘 Background navigation dots
- 🧭 Navigation bar
- 📱 Responsive design
- ⚛️ Component-based React architecture
- 🚀 Built using Vite for fast development

---

## 🛠️ Tech Stack

- **React.js**
- **Vite**
- **JavaScript (ES6+)**
- **HTML5**
- **CSS3**

---

## 📂 Project Structure

```text
EV-WEBSITE/
│
├── node_modules/
│
├── public/
│
├── screenshots/
│   └── home.png
│
├── src/
│   │
│   ├── assets/
│   │
│   ├── Components/
│   │   │
│   │   ├── Background/
│   │   │   ├── Background.css
│   │   │   └── Background.jsx
│   │   │
│   │   ├── Hero/
│   │   │   ├── Hero.css
│   │   │   └── Hero.jsx
│   │   │
│   │   └── Navbar/
│   │       ├── Navbar.css
│   │       └── Navbar.jsx
│   │
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
│
├── .gitignore
├── eslint.config.js
├── index.html
├── package-lock.json
├── package.json
└── README.md
```

> `node_modules/` is generated automatically after installing dependencies and is not pushed to GitHub because it is included in `.gitignore`.

---

## 🧩 Project Components

### Background

The `Background` component handles the visual background of the landing page.

It is responsible for:

- Displaying background images/video
- Changing backgrounds automatically
- Handling background transitions
- Controlling the active background
- Managing the video play/pause state

---

### Hero

The `Hero` component contains the main content of the landing page.

It includes:

- Hero heading
- Main description/content
- Explore button
- Background navigation indicators
- Video control button

---

### Navbar

The `Navbar` component contains the website navigation.

It provides navigation links for different sections of the website.

---

## ⚙️ How the Background Slider Works

The background is controlled using React's `useState` and `useEffect`.

A state variable keeps track of the currently selected background:

```jsx
const [heroCount, setHeroCount] = useState(0);
```

The value of `heroCount` determines which background is displayed.

For example:

```text
heroCount = 0 → Background 1
heroCount = 1 → Background 2
heroCount = 2 → Background 3
```

---

## ⏱️ Automatic Background Change

The background automatically changes every 3 seconds using `setInterval()`.

```jsx
useEffect(() => {
  const interval = setInterval(() => {
    setHeroCount((prev) => (prev === 2 ? 0 : prev + 1));
  }, 3000);

  return () => clearInterval(interval);
}, []);
```

### How it works

```text
Component loads
      ↓
useEffect runs
      ↓
setInterval starts
      ↓
Wait 3 seconds
      ↓
heroCount changes
      ↓
Background changes
      ↓
Wait another 3 seconds
      ↓
Repeat
```

---

## 🧹 Why `clearInterval()` Is Used

The following line is the cleanup function:

```jsx
return () => clearInterval(interval);
```

`setInterval()` creates a timer that continues running repeatedly.

When the React component is removed from the page, the timer should also be stopped.

Therefore:

```jsx
setInterval();
```

starts the timer, while:

```jsx
clearInterval();
```

stops the timer.

The cleanup function prevents unnecessary timers from continuing to run after the component has been unmounted.

### Simple Example

```text
setInterval()
     ↓
Start timer
     ↓
Run every 3 seconds
     ↓
Component removed
     ↓
clearInterval()
     ↓
Timer stopped
```

This is an important React practice when working with timers, event listeners, subscriptions, or other external resources.

---

## 🎨 Background Transition

CSS animations are used to make the background transition smoother.

The animation prevents the background from changing abruptly and provides a more visually appealing experience.

The project also uses a background color to avoid an unwanted white flash while the background transition is taking place.

---

## ▶️ Video Control

The project includes a play/pause control for the background video.

The video state is controlled using React state.

Conceptually:

```text
User clicks Play/Pause
        ↓
React updates state
        ↓
Video state changes
        ↓
Video plays or pauses
```

---

## 🔘 Background Navigation

The project also provides navigation indicators that allow the user to manually select a background.

For example:

```text
● ○ ○
```

The active indicator represents the currently selected background.

Clicking another indicator changes the active background.

---

## ⚛️ React Concepts Used

This project was created to practice several important React concepts.

### Components

The UI is divided into reusable components such as:

```text
Navbar
Hero
Background
```

---

### `useState`

Used to store values that can change during the lifetime of the application.

For example:

```jsx
const [heroCount, setHeroCount] = useState(0);
```

The state controls which background is currently active.

---

### `useEffect`

Used for side effects such as creating the automatic background-changing interval.

```jsx
useEffect(() => {
  // side effect
}, []);
```

---

### Event Handling

React event handlers are used to respond to user interactions such as:

- Button clicks
- Navigation clicks
- Video controls

---

### Conditional Rendering

Different content or backgrounds can be displayed depending on the current state.

For example:

```text
heroCount === 0
heroCount === 1
heroCount === 2
```

---

### Component Communication

Different React components communicate using props and state.

This helps keep the application modular and easier to maintain.

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```

### 2. Navigate to the Project

```bash
cd EV-WEBSITE
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Development Server

```bash
npm run dev
```

Vite will provide a local development URL in the terminal.

Open that URL in your browser to view the application.

---

## 🏗️ Build for Production

To create a production-ready build:

```bash
npm run build
```

To preview the production build locally:

```bash
npm run preview
```

---

## 📜 Available Scripts

| Command           | Description                   |
| ----------------- | ----------------------------- |
| `npm run dev`     | Starts the development server |
| `npm run build`   | Creates a production build    |
| `npm run preview` | Previews the production build |
| `npm run lint`    | Runs ESLint                   |

---

## 🎯 Learning Objectives

This project was created as a practical React project to understand:

- React project structure
- React components
- JSX
- Props
- State management
- `useState`
- `useEffect`
- Event handling
- Conditional rendering
- Component communication
- Timers with `setInterval`
- Cleanup with `clearInterval`
- CSS animations
- Background images
- Background videos
- Responsive layouts
- Vite development workflow

---

## 🔄 Application Flow

The basic application flow is:

```text
index.html
     ↓
main.jsx
     ↓
createRoot()
     ↓
App.jsx
     ↓
React Components
     ↓
Navbar + Background + Hero
     ↓
Browser UI
```

The browser ultimately receives the rendered HTML, CSS, and JavaScript generated/handled by the React application.

---

## 🌐 Deployment

The project is currently maintained on GitHub.

Deployment can be done later using platforms such as Netlify or Vercel.

The project can be built using:

```bash
npm run build
```

The generated production files are placed inside the `dist` folder.

---

## 🔮 Future Improvements

Possible future improvements include:

- [ ] Add more website sections
- [ ] Add detailed EV information
- [ ] Add About section
- [ ] Add Explore section
- [ ] Add Contact section
- [ ] Improve mobile navigation
- [ ] Add more animations
- [ ] Improve accessibility
- [ ] Optimize images and videos
- [ ] Improve loading performance
- [ ] Add more interactive elements
- [ ] Deploy the finished project

---

## 👨‍💻 Author

**Sayan**

B.Tech CSE Student & Aspiring Software Engineer

---

## ❤️ Acknowledgement

This project was created as part of my journey of learning and building projects with **React.js**.

---

## ⭐ Support

If you found this project interesting, consider giving the repository a ⭐ on GitHub.

---

**Built with ❤️ using React.js and Vite.**
