##	*Hello, Welcome I'M Tuani Putra👋*

![Tuani Putra](img/github-header-image2.png)  

<!--
**tuaniputramanurung12S21008/tuaniputramanurung12S21008** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->



- 🔭 I am a student at **Del Institute of Technology**

- 🌱 Currently, I am excited to learn and develop my skills in order to become someone who understands **data analysis**

#### *Skills*

 <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" /> <img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue" /> <img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> <img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" />


#### *Tools*

<img src="https://img.shields.io/badge/Visual_Studio-5C2D91?style=for-the-badge&logo=visual%20studio&logoColor=white" /> <img src="https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white" /> <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white" />


#### *Connect With Me*

![https://instagram.com/tuanipm](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)  ![https://[linkedin.com](https://www.linkedin.com/feed/TuaniPutra)](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white) 


#### **Play With Me**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/tuaniputramanurung12S21008/tuaniputramanurung12S21008/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/tuaniputramanurung12S21008/tuaniputramanurung12S21008/output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/tuaniputramanurung12S21008/tuaniputramanurung12S21008/output/pacman-contribution-graph.svg">
</picture>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sudoku Game</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      background: #f4f4f4;
      padding: 20px;
    }

    h1 {
      margin-bottom: 20px;
    }

    table {
      border-collapse: collapse;
    }

    td {
      width: 40px;
      height: 40px;
      text-align: center;
      border: 1px solid #999;
    }

    input {
      width: 100%;
      height: 100%;
      font-size: 18px;
      text-align: center;
      border: none;
    }

    input:focus {
      outline: none;
      background-color: #e0f7fa;
    }

    td:nth-child(3), td:nth-child(6) {
      border-right: 2px solid #000;
    }

    tr:nth-child(3) td, tr:nth-child(6) td {
      border-bottom: 2px solid #000;
    }

    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>🧠 Sudoku Game</h1>
  <table id="sudoku-board"></table>
  <button onclick="checkSolution()">✔️ Check Solution</button>

  <script>
    const puzzle = [
      [5, 3, '', '', 7, '', '', '', ''],
      [6, '', '', 1, 9, 5, '', '', ''],
      ['', 9, 8, '', '', '', '', 6, ''],
      [8, '', '', '', 6, '', '', '', 3],
      [4, '', '', 8, '', 3, '', '', 1],
      [7, '', '', '', 2, '', '', '', 6],
      ['', 6, '', '', '', '', 2, 8, ''],
      ['', '', '', 4, 1, 9, '', '', 5],
      ['', '', '', '', 8, '', '', 7, 9]
    ];

    const solution = [
      [5,3,4,6,7,8,9,1,2],
      [6,7,2,1,9,5,3,4,8],
      [1,9,8,3,4,2,5,6,7],
      [8,5,9,7,6,1,4,2,3],
      [4,2,6,8,5,3,7,9,1],
      [7,1,3,9,2,4,8,5,6],
      [9,6,1,5,3,7,2,8,4],
      [2,8,7,4,1,9,6,3,5],
      [3,4,5,2,8,6,1,7,9]
    ];

    const board = document.getElementById("sudoku-board");

    function createBoard() {
      for (let row = 0; row < 9; row++) {
        const tr = document.createElement("tr");
        for (let col = 0; col < 9; col++) {
          const td = document.createElement("td");
          const input = document.createElement("input");
          input.setAttribute("type", "text");
          input.setAttribute("maxlength", "1");

          if (puzzle[row][col] !== '') {
            input.value = puzzle[row][col];
            input.disabled = true;
            input.style.backgroundColor = "#ddd";
          }

          td.appendChild(input);
          tr.appendChild(td);
        }
        board.appendChild(tr);
      }
    }

    function checkSolution() {
      const rows = board.querySelectorAll("tr");
      let correct = true;

      rows.forEach((tr, i) => {
        const inputs = tr.querySelectorAll("input");
        inputs.forEach((input, j) => {
          if (parseInt(input.value) !== solution[i][j]) {
            input.style.backgroundColor = "#ffcccc";
            correct = false;
          } else {
            input.style.backgroundColor = "#ccffcc";
          }
        });
      });

      alert(correct ? "🎉 Correct Solution!" : "❌ Incorrect, try again.");
    }

    createBoard();
  </script>
</body>
</html>



