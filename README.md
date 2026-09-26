# 🃏 Rummy Family

A simple browser-based **Rummy Family Score Tracker** built using HTML, CSS, and JavaScript.

## 🌐 Live Demo

### ▶️ Open in Browser

**[🃏 Rummy Family – Open App](https://ri2111.github.io/Rummy_Family/Home.html)**

> If GitHub Pages is enabled for this repository, the above link opens the actual application directly in the browser.

### 📄 Source Code

**[View Home.html](https://github.com/ri2111/Rummy_Family/blob/main/Home.html)**

### ⚡ Raw HTML

**[View Raw Home.html](https://raw.githubusercontent.com/ri2111/Rummy_Family/refs/heads/main/Home.html)**

---

## ✨ Features

* 🃏 Rummy family score tracking
* 👥 Multiple player support
* ✏️ Editable player names
* 🔢 Raw score entry for each round
* 🧮 Automatic score calculation
* 🏆 Automatic player ranking
* 🥇🥈🥉 Medal display for rankings
* 📱 Responsive browser layout
* 🌙 Dark-themed interface
* 💾 No database required
* ⚡ Runs directly in a web browser

---

## 👥 Players

Players can be configured in `Home.html`.

```javascript
let players = ["APPA","AMMA","AKKA","THAMBI"];
```

To change the players, edit this line:

```javascript
let players = ["PLAYER 1","PLAYER 2","PLAYER 3","PLAYER 4"];
```

The score table automatically adjusts to the number of players.

---

## 🎯 Rounds

Round scores are stored in the `rounds` array.

Example:

```javascript
let rounds = [
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0]
];
```

Each row represents one round.

Example:

```text
Round 1 → APPA AMMA AKKA THAMBI
Round 2 → APPA AMMA AKKA THAMBI
Round 3 → APPA AMMA AKKA THAMBI
```

---

## 🧮 Score Calculation

The application automatically calculates the total score for every player.

The first and last rounds are automatically multiplied by `2`.

```javascript
function multiplier(r){
  return (r===0 || r===rounds.length-1) ? 2 : 1;
}
```

The total score is calculated using:

```javascript
function computeTotals(){
  return players.map((_,pi)=>
    rounds.reduce(
      (sum,r,ri)=>sum + r[pi]*multiplier(ri),
      0
    )
  );
}
```

---

## 🏆 Ranking

Players are automatically sorted by their total score.

```javascript
const order = players
  .map((n,i)=>({n, t:totals[i]}))
  .sort((a,b)=>a.t-b.t);
```

The lowest score appears first.

The application displays:

```text
🥇 1st
🥈 2nd
🥉 3rd
4. 4th
...
```

---

## 📊 Tables

The application contains two score tables.

### 1. Calculated Scores

Shows the calculated score after applying the round multiplier.

### 2. Raw Score Entry

Allows players to enter their original round scores.

---

## 🛠️ Technology

| Technology   | Usage                         |
| ------------ | ----------------------------- |
| HTML5        | Page structure                |
| CSS3         | Design and responsive layout  |
| JavaScript   | Score calculation and ranking |
| Google Fonts | Inter / JetBrains Mono        |
| GitHub Pages | Web hosting                   |

---

## 📁 Project Structure

```text
Rummy_Family/
│
├── Home.html
└── README.md
```

---

## 🚀 Run Locally

No installation is required.

Simply download the repository and open:

```text
Home.html
```

in a modern browser such as:

* Google Chrome
* Microsoft Edge
* Firefox

---

## 🌐 GitHub Pages

To host the project using GitHub Pages:

1. Open the GitHub repository.
2. Go to **Settings**.
3. Open **Pages**.
4. Select the `main` branch.
5. Select `/ (root)`.
6. Save.
7. GitHub will generate a website URL.

The expected URL is:

```text
https://ri2111.github.io/Rummy_Family/Home.html
```

---

## 📝 Customization

### Change Player Names

Edit:

```javascript
let players = ["APPA","AMMA","AKKA","THAMBI"];
```

### Change Initial Scores

Edit:

```javascript
let rounds = [
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0],
  [0,0,0,0]
];
```

For example:

```javascript
let rounds = [
  [10,20,30,40],
  [5,15,25,35],
  [0,10,20,30],
  [20,10,5,15],
  [15,20,10,5],
  [5,0,15,10],
  [10,5,20,15]
];
```

---

## 📜 License

This project is intended for personal/family use.

---

## ❤️ Rummy Family

**Simple scores. Automatic calculation. Easy ranking.**

### 🃏 Play Now

**[OPEN RUMMY FAMILY →](https://ri2111.github.io/Rummy_Family/Home.html)**
