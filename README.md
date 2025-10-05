<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lama Naser - Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* Basic Reset */
    * {margin:0;padding:0;box-sizing:border-box;}
    body {font-family:'Roboto', sans-serif; background: #0f0c29; background: linear-gradient(to right, #24243e, #302b63, #0f0c29); color:white; scroll-behavior: smooth;}
    a {text-decoration:none; color: inherit;}

    /* Hero Section */
    .hero {height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; position:relative; overflow:hidden;}
    .hero h1 {font-size:3rem; background: linear-gradient(90deg,#ff6ec4,#7873f5,#4ade80); background-clip: text; -webkit-background-clip:text; color:transparent; animation: gradient 5s infinite alternate;}
    @keyframes gradient {0% {background-position:0%}100%{background-position:100%}}
    .typing {font-size:1.5rem; margin-top:1rem; color:#FFD700;}
    
    /* Sections */
    section {padding:80px 20px;}
    h2 {font-size:2rem; text-align:center; margin-bottom:40px; background: linear-gradient(90deg,#ff6ec4,#7873f5); -webkit-background-clip:text; color:transparent;}
    
    /* Skills */
    .skills {display:flex; justify-content:center; flex-wrap:wrap; gap:20px;}
    .skill {width:150px; text-align:center;}
    .skill-bar {height:10px; width:100%; background:#444; border-radius:5px; margin-top:5px; overflow:hidden;}
    .skill-fill {height:100%; background: linear-gradient(90deg,#ff6ec4,#7873f5); width:0; border-radius:5px; transition: width 2s ease;}
    
    /* Projects */
    .projects {display:flex; flex-wrap:wrap; justify-content:center; gap:20px;}
    .project-card {background:#1c1c2e; padding:20px; border-radius:10px; width:250px; text-align:center; transition: transform 0.3s, box-shadow 0.3s;}
    .project-card:hover {transform: translateY(-10px); box-shadow:0 0 20px #ff6ec4;}
    .project-card h3 {margin-bottom:10px;}
    .project-card a {color:#FFD700;}
    
    /* Contact */
    .contact {display:flex; justify-content:center; gap:20px;}
    .contact a {padding:10px 20px; border:2px solid #FFD700; border-radius:5px; color:#FFD700; transition:0.3s;}
    .contact a:hover {background:#FFD700; color:#1c1c2e;}
  </style>
</head>
<body>

  <!-- Hero -->
  <div class="hero">
    <h1>Lama Naser</h1>
    <div class="typing" id="typing"></div>
  </div>

  <!-- Skills Section -->
  <section id="skills">
    <h2>Skills</h2>
    <div class="skills">
      <div class="skill">
        <h3>React</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:95%"></div></div>
      </div>
      <div class="skill">
        <h3>TypeScript</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div>
      </div>
      <div class="skill">
        <h3>JavaScript</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div>
      </div>
      <div class="skill">
        <h3>HTML/CSS</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div>
      </div>
      <div class="skill">
        <h3>Python</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:75%"></div></div>
      </div>
      <div class="skill">
        <h3>C++</h3>
        <div class="skill-bar"><div class="skill-fill" style="width:70%"></div></div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="projects">
      <div class="project-card">
        <h3>QuizPlus Frontend</h3>
        <p>React + TypeScript</p>
        <a href="#">View Project</a>
      </div>
      <div class="project-card">
        <h3>Sensor Data Reader</h3>
        <p>C++ + OpenCV</p>
        <a href="#">View Project</a>
      </div>
      <div class="project-card">
        <h3>Full-Stack App</h3>
        <p>Flask + React</p>
        <a href="#">View Project</a>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <h2>Contact Me</h2>
    <div class="contact">
      <a href="mailto:Lamazahi40@gmail.com">Email</a>
      <a href="https://www.linkedin.com/in/lamanaser/" target="_blank">LinkedIn</a>
      <a href="https://github.com/LamaNaser" target="_blank">GitHub</a>
    </div>
  </section>

  <script>
    // Typing Effect
    const roles = ["Full-Stack Developer", "Frontend Focus", "AI Explorer"];
    let i = 0;
    let j = 0;
    let currentRole = '';
    let isDeleting = false;
    const typingElement = document.getElementById('typing');

    function type() {
      if(i >= roles.length) i = 0;
      const fullText = roles[i];
      if(isDeleting) {
        currentRole = fullText.substring(0,j--);
      } else {
        currentRole = fullText.substring(0,j++);
      }
      typingElement.textContent = currentRole;
      if(!isDeleting && j === fullText.length+1) {isDeleting=true; setTimeout(type,1000);}
      else if(isDeleting && j===0){isDeleting=false;i++;setTimeout(type,500);}
      else setTimeout(type,150);
    }
    type();
  </script>

</body>
</html>
