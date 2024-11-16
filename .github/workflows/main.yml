```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Career Challenge Game</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Career Challenge Game</h1>
        <div id="quiz-container">
            <h2 id="question"></h2>
            <div id="answer-buttons" class="btn-container">
                <button class="btn" onclick="selectAnswer(0)"></button>
                <button class="btn" onclick="selectAnswer(1)"></button>
                <button class="btn" onclick="selectAnswer(2)"></button>
                <button class="btn" onclick="selectAnswer(3)"></button>
            </div>
            <button id="next-button" class="btn" onclick="nextQuestion()">Next</button>
        </div>
        <div id="score-container" class="score-container">
            <h2>Your Score: <span id="score"></span></h2>
            <button onclick="restartGame()" class="btn">Restart Game</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### CSS Styling (styles.css)
```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    text-align: center;
}

.container {
    width: 50%;
    margin: auto;
    padding: 20px;
}

.btn-container {
    margin: 20px 0;
}

.btn {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.btn:hover {
    background-color: #218838;
}

.score-container {
    display: none;
}

#next-button {
    display: none;
}
```

### JavaScript Logic (script.js)
```javascript
const questions = [
    {
        question: "Choose the best opening line for your cover letter.",
        answers: [
            "I am applying for the position...",
            "I hope this email finds you well...",
            "I'm the best candidate for this job...",
            "I found this job on your website."
        ],
        correct: 1
    },
    {
        question: "How do you respond when asked about your weaknesses?",
        answers: [
            "I never make mistakes.",
            "I can be too detail-oriented.",
            "I don't have any weaknesses.",
            "I usually work alone."
        ],
        correct: 1
    },
    {
        question: "What’s an effective way to follow up after a networking event?",
        answers: [
            "Send a generic email.",
            "Connect on LinkedIn with a personalized message.",
            "Call them immediately.",
            "Forget about it."
        ],
        correct: 1
    },
    {
        question: "Which scenario requires teamwork?",
        answers: [
            "Completing a solo project.",
            "Collaborating on a group task.",
            "Taking a test alone.",
            "Writing a report by yourself."
        ],
        correct: 1
    }
];

let currentQuestionIndex = 0;
let score = 0;

function startGame() {
    currentQuestionIndex = 0;
    score = 0;
    document.getElementById('score-container').style.display = 'none';
    document.getElementById('quiz-container').style.display = 'block';
    nextQuestion();
}

function nextQuestion() {
    resetState();
    showQuestion(questions[currentQuestionIndex]);
}

function showQuestion(question) {
    document.getElementById('question').innerText = question.question;
    question.answers.forEach((answer, index) => {
        const button = document.getElementById('answer-buttons').children[index];
        button.innerText = answer;
        button.classList.remove('correct', 'wrong');
    });
    document.getElementById('next-button').style.display = 'none';
}

function selectAnswer(index) {
    const question = questions[currentQuestionIndex];
    const button = document.getElementById('answer-buttons').children[index];
    
    if (index === question.correct) {
        score++;
        button.classList.add('correct');
    } else {
        button.classList.add('wrong');
    }

    Array.from(document.getElementById('answer-buttons').children).forEach((btn, idx) => {
        if (idx === question.correct) {
            btn.classList.add('correct');
        }
    });

    document.getElementById('next-button').style.display = 'block';
}

function resetState() {
    document.getElementById('next-button').style.display = 'none';
}

function restartGame() {
    document.getElementById('score-container').style.display = 'none';
    startGame();
}

document.addEventListener('DOMContentLoaded', startGame);
```
