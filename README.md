<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1.0" />
  <title>MR NITHISH K - Portfolio</title>
  <style>
    /* --- Global Styles --- */
    * { box-sizing: border-box; }
    body { margin:0; font-family: Arial, sans-serif; background:#f9f9f9; color:#333; }
    header { background:#333; color:#fff; padding:1rem; }
    nav.navbar { display:flex; justify-content:space-between; align-items:center; }
    .nav-links { list-style:none; display:flex; gap:1rem; margin:0; padding:0; }
    .nav-links li a { color:white; text-decoration:none; }
    .menu-toggle { display:none; cursor:pointer; }

    section { padding:40px 20px; }
    h2 { margin-bottom:20px; }

    /* Hero */
    .hero { background:#222; color:white; text-align:center; padding:80px 20px; }
    .hero h1 span { color:#22c55e; }
    .btn { display:inline-block; margin-top:20px; padding:10px 20px; background:#22c55e; color:#fff; text-decoration:none; border-radius:8px; }

    /* About */
    .about-content { display:flex; align-items:center; gap:20px; flex-wrap:wrap; }
    .about-content img { width:150px; border-radius:50%; }

    /* Projects */
    .project-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:20px; }
    .project-card { background:#fff; padding:20px; border-radius:8px; box-shadow:0 0 5px rgba(0,0,0,0.1); }

    /* Quiz */
    .quiz-container { max-width:800px; margin:0 auto; color:#e5e7eb; background:#0f172a; padding:20px; border-radius:12px; }
    .controls { display:flex; gap:10px; flex-wrap:wrap; margin-bottom:10px; }
    button { border:0; padding:10px 14px; border-radius:8px; cursor:pointer; font-weight:600; }
    button.secondary { background:#60a5fa; color:#fff; }
    button.ghost { background:#334155; color:#fff; }
    button.primary { background:#22c55e; color:#0a0a0a; }
    .card { background:#111827; border:1px solid #1f2937; border-radius:12px; padding:18px; margin-bottom:10px; }
    .q-title { font-weight:700; margin-bottom:8px; }
    .options { display:grid; gap:8px; }
    label.option { display:flex; gap:10px; padding:10px; border-radius:8px; background:#0b1220; border:1px solid #1f2937; cursor:pointer; }
    .correct { outline:2px solid #22c55e; }
    .incorrect { outline:2px solid #ef4444; }
    .meta { display:flex; gap:12px; flex-wrap:wrap; font-size:.9rem; }

    /* Blog */
    .container { max-width:800px; margin:0 auto; }
    .post { background:white; padding:15px; margin-bottom:20px; border-radius:8px; box-shadow:0 0 5px rgba(0,0,0,0.1); }

    /* Contact */
    form { display:grid; gap:10px; max-width:400px; margin:auto; }
    input, textarea { padding:10px; border:1px solid #ccc; border-radius:6px; width:100%; }
    form button { background:#22c55e; color:#fff; }

    footer { text-align:center; padding:20px; background:#333; color:#fff; margin-top:40px; }
  </style>
</head>
<body>
  <!-- Navbar -->
  <header>
    <nav class="navbar">
      <div class="logo">MyPortfolio</div>
      <ul class="nav-links" id="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#quiz">Quiz</a></li>
        <li><a href="#blog">Blog</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <div class="menu-toggle" id="menu-toggle">&#9776;</div>
    </nav>
  </header>

  <!-- Hero -->
  <section id="home" class="hero">
    <h1>Hello, I'm <span>MR NITHISH K</span></h1>
    <p>I am a STUDENT</p>
    <a href="#projects" class="btn">View My Work</a>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About Me</h2>
    <div class="about-content">
      <img src= "IMG_20250217_165531398_HDR.jpg" alt="Profile Photo">
      <p>I am a student enthusiastic about technology and design. I love building interactive, user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card"><h3>Project 1</h3><p>A simple responsive website.</p></div>
      <div class="project-card"><h3>Project 2</h3><p>JavaScript-based quiz app.</p></div>
      <div class="project-card"><h3>Project 3</h3><p>Personal blog with CMS.</p></div>
    </div>
  </section>

  <!-- Quiz -->
  <section id="quiz">
    <h2>Quiz App</h2>
    <div class="quiz-container">
      <div class="controls">
        <button id="newQuizBtn" class="ghost">New Quiz</button>
        <button id="submitBtn" class="secondary">Submit Answers</button>
        <button id="resetBtn" class="primary">Reset</button>
      </div>
      <div id="quizBox"></div>
      <div class="card meta">
        <span>Questions: <strong id="qCount">0</strong></span>
        <span>Answered: <strong id="answered">0</strong></span>
        <span>Score: <strong id="score">0</strong></span>
        <span id="resultText"></span>
      </div>
    </div>
  </section>

  <!-- Blog -->
  <section id="blog">
    <h2>My Blog</h2>
    <div class="container" id="postsContainer"></div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" id="name" name="user_name" placeholder="Your Name" required>
      <input type="email" id="email" name="user_email" placeholder="Your Email" required>
      <textarea id="message" name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MR NITHISH K | All rights reserved</p>
  </footer>

  <!-- EmailJS SDK -->
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <script>
    (function(){ emailjs.init("YOUR_PUBLIC_KEY"); })();
  </script>

  <!-- Scripts -->
  <script>
    /* -------- Quiz Logic -------- */
    const QUESTION_POOL = [
      { q: "Which HTML tag is used to define a hyperlink?", options: ["<a>", "<link>", "<href>", "<url>"], answer: 0 },
      { q: "Which property is used in CSS to change the text color?", options: ["text-color", "font-color", "color", "fgcolor"], answer: 2 },
      { q: "Inside which HTML element do we put JavaScript?", options: ["<js>", "<javascript>", "<script>", "<code>"], answer: 2 },
      { q: "Which array method adds an item to the end in JavaScript?", options: ["push()", "pop()", "shift()", "unshift()"], answer: 0 },
      { q: "What does CSS stand for?", options: ["Colorful Style Sheets", "Cascading Style Sheets", "Computer Style Sheets", "Creative Styling System"], answer: 1 },
      { q: "Which HTML attribute provides alternative text for images?", options: ["src", "title", "alt", "aria-label"], answer: 2 }
    ];

    const quizBox = document.getElementById('quizBox');
    const submitBtn = document.getElementById('submitBtn');
    const resetBtn = document.getElementById('resetBtn');
    const newQuizBtn = document.getElementById('newQuizBtn');
    const qCountEl = document.getElementById('qCount');
    const answeredEl = document.getElementById('answered');
    const scoreEl = document.getElementById('score');
    const resultText = document.getElementById('resultText');

    let currentQuestions = [];
    function shuffle(arr){for(let i=arr.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[arr[i],arr[j]]=[arr[j],arr[i]];}return arr;}
    function pickRandom(){return shuffle([...QUESTION_POOL]).slice(0,5).map(q=>({...q}));}
    function renderQuiz(){
      quizBox.innerHTML=''; currentQuestions.forEach((item,idx)=>{
        const indexed=item.options.map((t,i)=>({t,i})); shuffle(indexed);
        item._shuffled=indexed.map(o=>o.t); item._correct=indexed.findIndex(o=>o.i===item.answer);
        const div=document.createElement('div'); div.className="card";
        div.innerHTML=`<div class="q-title">Q${idx+1}. ${item.q}</div>
          <div class="options">${item._shuffled.map((opt,oi)=>`
            <label class="option"><input type="radio" name="q${idx}" value="${oi}"><span>${opt}</span></label>`).join('')}</div>`;
        quizBox.appendChild(div);
      });
      qCountEl.textContent=currentQuestions.length; updateAnswered(); scoreEl.textContent='0'; resultText.textContent='';
    }
    function updateAnswered(){answeredEl.textContent=document.querySelectorAll('#quizBox input[type="radio"]:checked').length;}
    function evaluate(){let score=0;quizBox.querySelectorAll('.card').forEach((block,idx)=>{
      const chosen=block.querySelector('input:checked'); const labels=block.querySelectorAll('label.option');
      labels.forEach(l=>l.classList.remove('correct','incorrect')); if(!chosen)return;
      const sel=Number(chosen.value); if(sel===currentQuestions[idx]._correct){score++;labels[sel].classList.add('correct');}
      else{labels[sel].classList.add('incorrect');labels[currentQuestions[idx]._correct].classList.add('correct');}});
      scoreEl.textContent=score; resultText.textContent=`You scored ${score}/${currentQuestions.length}`;}
    function reset(){document.querySelectorAll('#quizBox input:checked').forEach(el=>el.checked=false);
      document.querySelectorAll('#quizBox .option').forEach(l=>l.classList.remove('correct','incorrect')); updateAnswered();scoreEl.textContent='0';resultText.textContent='';}
    document.addEventListener('change',e=>{if(e.target.matches('#quizBox input[type="radio"]')) updateAnswered();});
    submitBtn.addEventListener('click',evaluate); resetBtn.addEventListener('click',reset);
    newQuizBtn.addEventListener('click',()=>{currentQuestions=pickRandom();renderQuiz();});
    currentQuestions=pickRandom(); renderQuiz();

    /* -------- Blog -------- */
    function loadPosts(){
      const posts=JSON.parse(localStorage.getItem("blogPosts"))||[];
      const container=document.getElementById("postsContainer"); container.innerHTML="";
      posts.reverse().forEach(post=>{
        const el=document.createElement("div"); el.className="post";
        el.innerHTML=`<h3>${post.title}</h3><small>${new Date(post.date).toLocaleString()}</small><p>${post.content}</p>`;
        container.appendChild(el);
      });
    }
    loadPosts();
  </script>
</body>
</html>
