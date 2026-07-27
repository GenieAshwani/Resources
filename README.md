<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="A practical 6-month Java backend developer roadmap with free, clickable resources." />
  <title>6-Month Java Developer Roadmap | Genie Ashwani First</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Manrope:wght@600;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #070a12;
      --panel: rgba(17, 23, 39, .78);
      --panel-2: rgba(255,255,255,.055);
      --text: #f7f8ff;
      --muted: #aab2c8;
      --line: rgba(255,255,255,.1);
      --primary: #8b5cf6;
      --primary-2: #22d3ee;
      --green: #34d399;
      --yellow: #fbbf24;
      --shadow: 0 22px 70px rgba(0,0,0,.38);
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      color: var(--text);
      font-family: Inter, system-ui, sans-serif;
      background:
        radial-gradient(circle at 8% 0%, rgba(139,92,246,.22), transparent 34%),
        radial-gradient(circle at 92% 15%, rgba(34,211,238,.16), transparent 28%),
        linear-gradient(180deg, #070a12 0%, #090e1b 52%, #070a12 100%);
      min-height: 100vh;
    }
    a { color: inherit; }
    .grid-glow {
      position: fixed; inset: 0; pointer-events:none; opacity:.22;
      background-image: linear-gradient(rgba(255,255,255,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.04) 1px, transparent 1px);
      background-size: 48px 48px;
      mask-image: linear-gradient(to bottom, black, transparent 72%);
    }
    .container { width: min(1180px, calc(100% - 32px)); margin: auto; position: relative; }
    nav {
      position: sticky; top: 12px; z-index: 50; margin-top: 12px;
      display:flex; align-items:center; justify-content:space-between; gap:20px;
      padding: 13px 16px; border:1px solid var(--line); border-radius:18px;
      background: rgba(7,10,18,.72); backdrop-filter: blur(16px); box-shadow: 0 10px 35px rgba(0,0,0,.2);
    }
    .brand { display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:-.02em; }
    .brand-mark { width:34px; height:34px; display:grid; place-items:center; border-radius:11px; background:linear-gradient(135deg,var(--primary),var(--primary-2)); box-shadow:0 8px 24px rgba(139,92,246,.35); }
    .navlinks { display:flex; flex-wrap:wrap; gap:6px; }
    .navlinks a { text-decoration:none; color:var(--muted); padding:8px 10px; border-radius:10px; font-size:.84rem; }
    .navlinks a:hover { color:white; background:var(--panel-2); }
    header { padding: 88px 0 54px; text-align:center; }
    .eyebrow { display:inline-flex; align-items:center; gap:8px; padding:7px 11px; border:1px solid rgba(139,92,246,.35); background:rgba(139,92,246,.1); color:#d8ccff; border-radius:999px; font-size:.8rem; font-weight:700; }
    h1 { font-family:Manrope, sans-serif; font-size:clamp(2.45rem,7vw,5.35rem); line-height:.98; letter-spacing:-.06em; margin:24px auto 20px; max-width:940px; }
    .gradient { background:linear-gradient(90deg,#fff 10%,#c4b5fd 48%,#67e8f9); -webkit-background-clip:text; color:transparent; }
    .lead { max-width:770px; margin:0 auto; color:var(--muted); font-size:clamp(1rem,2vw,1.17rem); line-height:1.75; }
    .hero-actions { margin-top:30px; display:flex; justify-content:center; flex-wrap:wrap; gap:12px; }
    .btn { display:inline-flex; align-items:center; gap:9px; text-decoration:none; padding:13px 18px; border-radius:14px; font-weight:700; border:1px solid var(--line); transition:.2s ease; }
    .btn-primary { background:linear-gradient(135deg,var(--primary),#6d5dfc); border-color:transparent; box-shadow:0 15px 35px rgba(139,92,246,.28); }
    .btn:hover { transform:translateY(-2px); }
    .stats { margin:42px auto 0; max-width:850px; display:grid; grid-template-columns:repeat(4,1fr); border:1px solid var(--line); border-radius:20px; background:var(--panel); overflow:hidden; box-shadow:var(--shadow); }
    .stat { padding:20px 12px; border-right:1px solid var(--line); }
    .stat:last-child { border:0; }
    .stat strong { display:block; font-size:1.35rem; }
    .stat span { color:var(--muted); font-size:.78rem; }
    .section { padding:55px 0; }
    .section-head { display:flex; justify-content:space-between; gap:24px; align-items:end; margin-bottom:24px; }
    .section-head h2 { font-family:Manrope,sans-serif; font-size:clamp(1.8rem,4vw,3rem); margin:0; letter-spacing:-.04em; }
    .section-head p { margin:0; max-width:590px; color:var(--muted); line-height:1.65; }
    .rule-card { padding:24px; border:1px solid rgba(52,211,153,.25); border-radius:22px; background:linear-gradient(135deg,rgba(52,211,153,.09),rgba(34,211,238,.05)); display:grid; grid-template-columns:repeat(3,1fr); gap:16px; }
    .rule { padding:18px; border-radius:16px; background:rgba(255,255,255,.04); }
    .rule b { display:block; margin-bottom:7px; }
    .rule span { color:var(--muted); font-size:.9rem; line-height:1.55; }
    .timeline { display:grid; gap:24px; }
    .month { scroll-margin-top:100px; position:relative; display:grid; grid-template-columns:190px 1fr; gap:24px; padding:28px; border:1px solid var(--line); border-radius:26px; background:linear-gradient(160deg,rgba(255,255,255,.068),rgba(255,255,255,.025)); box-shadow:var(--shadow); overflow:hidden; }
    .month::after { content:""; position:absolute; width:180px; height:180px; border-radius:50%; right:-80px; top:-80px; background:var(--accent); filter:blur(75px); opacity:.19; }
    .month-meta { position:relative; z-index:1; }
    .month-number { font-family:Manrope,sans-serif; font-size:3.8rem; font-weight:800; line-height:1; color:transparent; -webkit-text-stroke:1px rgba(255,255,255,.34); }
    .month-meta h3 { font-family:Manrope,sans-serif; margin:12px 0 7px; font-size:1.25rem; }
    .focus { color:var(--muted); font-size:.84rem; line-height:1.5; }
    .hours { display:inline-block; margin-top:13px; color:#dbeafe; background:rgba(255,255,255,.06); border:1px solid var(--line); border-radius:999px; padding:6px 9px; font-size:.72rem; }
    .month-body { position:relative; z-index:1; }
    .topics { display:grid; grid-template-columns:repeat(2,minmax(0,1fr)); gap:12px; }
    .topic { border:1px solid var(--line); border-radius:17px; padding:16px; background:rgba(5,8,15,.35); }
    .topic-top { display:flex; gap:10px; align-items:flex-start; }
    .check { width:20px; height:20px; accent-color:var(--primary); flex:0 0 auto; margin-top:1px; cursor:pointer; }
    .topic h4 { margin:0 0 6px; font-size:.98rem; }
    .topic p { margin:0; color:var(--muted); font-size:.83rem; line-height:1.5; }
    .links { display:flex; flex-wrap:wrap; gap:7px; margin-top:12px; }
    .resource { text-decoration:none; border:1px solid var(--line); background:rgba(255,255,255,.045); border-radius:10px; padding:7px 9px; font-size:.76rem; color:#e8eaff; transition:.18s ease; }
    .resource:hover { background:rgba(139,92,246,.18); border-color:rgba(139,92,246,.5); }
    .priority { border-color:rgba(251,191,36,.35); background:rgba(251,191,36,.08); color:#fde68a; }
    .deliverable { margin-top:15px; padding:15px 16px; border-left:3px solid var(--accent); border-radius:6px 14px 14px 6px; background:rgba(255,255,255,.045); color:#e8eaff; font-size:.87rem; line-height:1.55; }
    .deliverable b { color:white; }
    .project-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:16px; }
    .project { padding:22px; border:1px solid var(--line); border-radius:20px; background:var(--panel); }
    .project .tag { display:inline-block; padding:6px 9px; border-radius:999px; background:rgba(34,211,238,.09); color:#a5f3fc; font-size:.72rem; font-weight:700; }
    .project h3 { margin:16px 0 9px; }
    .project p { color:var(--muted); line-height:1.55; font-size:.88rem; }
    .project ul { padding-left:18px; color:#dbe2f3; font-size:.84rem; line-height:1.65; }
    .progress-wrap { position:fixed; right:18px; bottom:18px; z-index:40; width:190px; padding:13px; border:1px solid var(--line); border-radius:16px; background:rgba(7,10,18,.84); backdrop-filter:blur(16px); box-shadow:var(--shadow); }
    .progress-top { display:flex; justify-content:space-between; font-size:.76rem; margin-bottom:8px; }
    .bar { height:7px; border-radius:999px; background:rgba(255,255,255,.08); overflow:hidden; }
    .fill { height:100%; width:0; background:linear-gradient(90deg,var(--primary),var(--primary-2)); transition:.25s ease; }
    .note { border:1px solid rgba(251,191,36,.25); background:rgba(251,191,36,.07); border-radius:18px; padding:20px; color:#fef3c7; line-height:1.6; }
    footer { padding:55px 0 90px; color:var(--muted); text-align:center; font-size:.82rem; }
    footer a { color:#c4b5fd; }
    @media (max-width:850px) {
      .navlinks { display:none; }
      .stats, .rule-card, .project-grid { grid-template-columns:1fr 1fr; }
      .month { grid-template-columns:1fr; }
      .month-number { font-size:2.8rem; }
    }
    @media (max-width:600px) {
      header { padding-top:60px; }
      .stats, .rule-card, .project-grid, .topics { grid-template-columns:1fr; }
      .stat { border-right:0; border-bottom:1px solid var(--line); }
      .month { padding:20px; border-radius:20px; }
      .section-head { display:block; }
      .section-head p { margin-top:10px; }
      .progress-wrap { left:16px; right:16px; width:auto; bottom:12px; }
    }
    @media print {
      .grid-glow, nav, .progress-wrap, .hero-actions { display:none; }
      body { background:white; color:#111827; }
      .lead,.section-head p,.focus,.topic p,.project p,footer { color:#4b5563; }
      .month,.project,.rule-card,.stats { box-shadow:none; background:white; border-color:#d1d5db; }
      .topic { background:#f9fafb; border-color:#e5e7eb; }
      .resource { color:#111827; }
    }
  </style>
</head>
<body>
  <div class="grid-glow"></div>
  <div class="container">
    <nav>
      <div class="brand"><span class="brand-mark">☕</span> Java Roadmap</div>
      <div class="navlinks">
        <a href="#month-1">M1</a><a href="#month-2">M2</a><a href="#month-3">M3</a>
        <a href="#month-4">M4</a><a href="#month-5">M5</a><a href="#month-6">M6</a>
        <a href="#projects">Projects</a>
      </div>
    </nav>

    <header>
      <span class="eyebrow">✦ Free resources • Genie Ashwani prioritized</span>
      <h1><span class="gradient">Become a Java Developer</span><br>in 6 Months</h1>
      <p class="lead">A focused, project-first roadmap for a beginner targeting Java backend internships and entry-level roles. Learn for 2–3 hours daily, code every day, and publish every project on GitHub.</p>
      <div class="hero-actions">
        <a class="btn btn-primary" href="#month-1">Start Month 1 →</a>
        <a class="btn" href="https://www.youtube.com/@GenieAshwani" target="_blank" rel="noopener">Open Genie Ashwani ↗</a>
        <button class="btn" onclick="window.print()" style="cursor:pointer;color:white;background:transparent">Save as PDF</button>
      </div>
      <div class="stats">
        <div class="stat"><strong>6</strong><span>Focused months</span></div>
        <div class="stat"><strong>2–3h</strong><span>Daily commitment</span></div>
        <div class="stat"><strong>3</strong><span>Portfolio projects</span></div>
        <div class="stat"><strong>150+</strong><span>DSA problems</span></div>
      </div>
    </header>

    <section class="section">
      <div class="section-head"><h2>How to follow it</h2><p>Do not binge-watch. For every hour of learning, spend at least one hour writing, debugging or improving code.</p></div>
      <div class="rule-card">
        <div class="rule"><b>60% Build</b><span>Type code yourself, break it, fix it, and commit progress.</span></div>
        <div class="rule"><b>25% Learn</b><span>Use videos and documentation only for the current milestone.</span></div>
        <div class="rule"><b>15% Revise</b><span>Keep short notes and revisit interview questions weekly.</span></div>
      </div>
    </section>

    <main class="section timeline">
      <article class="month" id="month-1" style="--accent:#8b5cf6">
        <aside class="month-meta"><div class="month-number">01</div><h3>Java Foundations</h3><div class="focus">Syntax, logic, JVM basics and developer setup</div><span class="hours">Weeks 1–4</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Setup + Java basics</h4><p>JDK, IntelliJ, JVM/JRE/JDK, variables, data types, operators, input and output.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/watch?v=D5Z3mOFmR2w" target="_blank">★ Genie: Java/DSA Lecture 1</a><a class="resource priority" href="https://www.youtube.com/watch?v=ptJ8BL7bhWk" target="_blank">★ Genie: JVM Explained</a><a class="resource" href="https://dev.java/learn/" target="_blank">Dev.java Learn</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Control flow + methods</h4><p>if/else, switch, loops, arrays, strings, methods, scope and basic debugging.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/videos" target="_blank">★ Genie: Free Java Lectures</a><a class="resource" href="https://dev.java/learn/language-basics/" target="_blank">Official Java Basics</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Problem solving</h4><p>Dry runs, patterns, number problems, arrays and strings; solve 30 easy questions.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/watch?v=D5Z3mOFmR2w" target="_blank">★ Genie DSA Series</a><a class="resource" href="https://www.hackerrank.com/domains/java" target="_blank">HackerRank Java</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Git + GitHub basics</h4><p>Repository, add, commit, push, pull, branches and a clean README.</p></div></div><div class="links"><a class="resource" href="https://github.com/skills/introduction-to-github" target="_blank">GitHub Skills</a><a class="resource" href="https://git-scm.com/book/en/v2" target="_blank">Pro Git</a></div></div>
          </div>
          <div class="deliverable"><b>Month-end deliverable:</b> Console-based Student Grade Manager with methods, arrays, validation and a public GitHub repository.</div>
        </div>
      </article>

      <article class="month" id="month-2" style="--accent:#22d3ee">
        <aside class="month-meta"><div class="month-number">02</div><h3>Core Java Mastery</h3><div class="focus">OOP, collections, exceptions and modern Java</div><span class="hours">Weeks 5–8</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>OOP deeply</h4><p>Classes, objects, constructors, encapsulation, inheritance, polymorphism, abstraction and interfaces.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=OOPS" target="_blank">★ Genie: OOP videos</a><a class="resource" href="https://dev.java/learn/classes-objects/" target="_blank">Dev.java Classes</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Collections framework</h4><p>List, Set, Map, Queue, generics, Comparable, Comparator, iteration and complexity.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=collections" target="_blank">★ Genie: Collections</a><a class="resource" href="https://dev.java/learn/api/collections-framework/" target="_blank">Java Collections Guide</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Exceptions + files</h4><p>Checked/unchecked exceptions, custom exceptions, try-with-resources and file I/O.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=exception%20handling" target="_blank">★ Genie: Exceptions</a><a class="resource" href="https://dev.java/learn/exceptions/" target="_blank">Official Exceptions</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Java 8+</h4><p>Lambdas, functional interfaces, streams, Optional, method references and date/time API.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Java%208" target="_blank">★ Genie: Java 8</a><a class="resource" href="https://dev.java/learn/lambdas/" target="_blank">Official Lambdas</a></div></div>
          </div>
          <div class="deliverable"><b>Month-end deliverable:</b> Library Management System using OOP, collections, custom exceptions, file persistence and unit-friendly design.</div>
        </div>
      </article>

      <article class="month" id="month-3" style="--accent:#34d399">
        <aside class="month-meta"><div class="month-number">03</div><h3>Database & Quality</h3><div class="focus">SQL, JDBC, Maven and automated testing</div><span class="hours">Weeks 9–12</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>SQL + MySQL</h4><p>DDL/DML, filters, joins, grouping, subqueries, indexes, normalization and transactions.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=SQL" target="_blank">★ Genie: SQL search</a><a class="resource" href="https://sqlbolt.com/" target="_blank">SQLBolt Interactive</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>JDBC</h4><p>Connections, PreparedStatement, ResultSet, CRUD, transactions, DAO pattern and connection safety.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/watch?v=eXZhZNZkjtQ" target="_blank">★ Genie: JDBC Full Course</a><a class="resource" href="https://docs.oracle.com/javase/tutorial/jdbc/" target="_blank">Oracle JDBC Tutorial</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Maven + project structure</h4><p>pom.xml, dependencies, lifecycle, plugins, profiles and standard package structure.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Maven" target="_blank">★ Genie: Maven</a><a class="resource" href="https://maven.apache.org/guides/getting-started/" target="_blank">Maven Getting Started</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Testing</h4><p>JUnit 5, assertions, lifecycle, parameterized tests, Mockito mocks and service-layer testing.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=JUnit%20Mockito" target="_blank">★ Genie: JUnit/Mockito</a><a class="resource" href="https://junit.org/junit5/docs/current/user-guide/" target="_blank">JUnit 5 Guide</a><a class="resource" href="https://site.mockito.org/" target="_blank">Mockito</a></div></div>
          </div>
          <div class="deliverable"><b>Month-end deliverable:</b> Expense Tracker backed by MySQL/JDBC, Maven, DAO pattern and at least 20 meaningful unit tests.</div>
        </div>
      </article>

      <article class="month" id="month-4" style="--accent:#f59e0b">
        <aside class="month-meta"><div class="month-number">04</div><h3>Spring Boot APIs</h3><div class="focus">Production-style REST APIs with persistence</div><span class="hours">Weeks 13–16</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Spring Core + Boot</h4><p>IoC, DI, beans, configuration, auto-configuration, starters, profiles and layered architecture.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/watch?v=ATmGLbfiuxA" target="_blank">★ Genie: Spring Boot One Video</a><a class="resource priority" href="https://www.youtube.com/watch?v=gHl_FwTSDVc" target="_blank">★ Genie: Boot + Project</a><a class="resource" href="https://spring.io/guides/gs/" target="_blank">Spring Guides</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>REST APIs</h4><p>Controllers, DTOs, CRUD, HTTP methods/status codes, validation and global exception handling.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/watch?v=U16dAUw5iGA" target="_blank">★ Genie: REST API</a><a class="resource" href="https://spring.io/guides/gs/rest-service/" target="_blank">Official REST Guide</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Spring Data JPA</h4><p>Entities, relationships, repositories, pagination, JPQL, transactions, auditing and N+1 awareness.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Spring%20Data%20JPA" target="_blank">★ Genie: Spring Data JPA</a><a class="resource" href="https://spring.io/guides/gs/accessing-data-jpa/" target="_blank">Official JPA Guide</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>API tooling</h4><p>Postman, Swagger/OpenAPI, logging, configuration, pagination and consistent API responses.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Swagger%20Postman" target="_blank">★ Genie: Swagger/Postman</a><a class="resource" href="https://springdoc.org/" target="_blank">Springdoc OpenAPI</a></div></div>
          </div>
          <div class="deliverable"><b>Month-end deliverable:</b> Job Portal REST API with users, jobs, applications, validation, pagination, API docs and MySQL.</div>
        </div>
      </article>

      <article class="month" id="month-5" style="--accent:#ef4444">
        <aside class="month-meta"><div class="month-number">05</div><h3>Security & Deployment</h3><div class="focus">Authentication, Docker and microservices basics</div><span class="hours">Weeks 17–20</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Spring Security + JWT</h4><p>Authentication, authorization, password encoding, filters, roles, JWT access and refresh flow.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/playlists" target="_blank">★ Genie: Spring Security Playlist</a><a class="resource" href="https://docs.spring.io/spring-security/reference/" target="_blank">Official Security Docs</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Docker</h4><p>Images, containers, Dockerfile, volumes, networks and Docker Compose for app + database.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Docker" target="_blank">★ Genie: Docker</a><a class="resource" href="https://docs.docker.com/guides/java/" target="_blank">Docker Java Guide</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Microservices fundamentals</h4><p>Service boundaries, REST communication, config, discovery, gateway, resilience and distributed trade-offs.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/playlist?list=PLciPu9FabM_7JnZ58z6Df4--bFDAEbH88" target="_blank">★ Genie: Microservices Project</a><a class="resource" href="https://spring.io/microservices" target="_blank">Spring Microservices</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Deployment basics</h4><p>Environment variables, Linux commands, build JAR, logs, health checks and one free/cloud deployment.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=AWS%20deployment" target="_blank">★ Genie: AWS/Deployment</a><a class="resource" href="https://docs.github.com/en/actions" target="_blank">GitHub Actions</a></div></div>
          </div>
          <div class="deliverable"><b>Month-end deliverable:</b> Secure the Job Portal with JWT and roles, containerize it with MySQL, add health checks and deploy a live demo.</div>
        </div>
      </article>

      <article class="month" id="month-6" style="--accent:#ec4899">
        <aside class="month-meta"><div class="month-number">06</div><h3>Job-Ready Sprint</h3><div class="focus">Capstone, DSA, design and interview preparation</div><span class="hours">Weeks 21–24</span></aside>
        <div class="month-body">
          <div class="topics">
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Capstone project</h4><p>Build one polished backend with auth, database, tests, Docker, docs, logging and deployment.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=project" target="_blank">★ Genie: Project videos</a><a class="resource" href="#projects">Project choices below</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>DSA interview set</h4><p>Arrays, strings, hashing, linked lists, stacks, queues, recursion, sorting, binary search and trees basics.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/videos" target="_blank">★ Genie: Free DSA Batch</a><a class="resource" href="https://leetcode.com/problemset/" target="_blank">LeetCode</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>LLD + design patterns</h4><p>SOLID, Factory, Strategy, Observer, Builder and one design such as Parking Lot.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/c/GenieAshwani/playlists" target="_blank">★ Genie: Design Patterns</a><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=Parking%20Lot" target="_blank">★ Genie: Parking Lot LLD</a></div></div>
            <div class="topic"><div class="topic-top"><input class="check" type="checkbox"><div><h4>Resume + interview practice</h4><p>One-page resume, GitHub cleanup, project explanation, Java/Spring/SQL questions and mock interviews.</p></div></div><div class="links"><a class="resource priority" href="https://www.youtube.com/@GenieAshwani/search?query=interview%20questions" target="_blank">★ Genie: Interview Questions</a><a class="resource" href="https://roadmap.sh/java" target="_blank">Java Skill Checklist</a></div></div>
          </div>
          <div class="deliverable"><b>Final outcome:</b> 3 pinned repositories, 1 live capstone, 150+ DSA questions, a focused resume and the ability to explain every major technical decision.</div>
        </div>
      </article>
    </main>

    <section class="section" id="projects">
      <div class="section-head"><h2>Capstone choices</h2><p>Choose only one. Depth, tests, documentation and deployment matter more than building many incomplete projects.</p></div>
      <div class="project-grid">
        <div class="project"><span class="tag">Recommended</span><h3>Job Portal API</h3><p>A practical domain that demonstrates roles, workflows and database relationships.</p><ul><li>Recruiter and candidate roles</li><li>Jobs, applications and status workflow</li><li>JWT, search, pagination and email events</li></ul></div>
        <div class="project"><span class="tag">Strong portfolio</span><h3>E-commerce Backend</h3><p>Shows transactional thinking and separation of business concerns.</p><ul><li>Products, cart, orders and inventory</li><li>Idempotent checkout simulation</li><li>Admin APIs, validation and tests</li></ul></div>
        <div class="project"><span class="tag">Advanced</span><h3>Course Platform</h3><p>Excellent for demonstrating access control and modular backend design.</p><ul><li>Courses, lessons and enrollments</li><li>Student/instructor/admin roles</li><li>Progress tracking and reviews</li></ul></div>
      </div>
    </section>

    <section class="section">
      <div class="note"><b>Keep the scope realistic:</b> Kafka, Kubernetes, Redis, Elasticsearch and advanced system design are valuable, but they are not required before the first Java backend role. Add them after the core roadmap or only when your capstone genuinely needs them.</div>
    </section>

    <footer>
      Built as a free learning roadmap. Resource order gives first priority to <a href="https://www.youtube.com/@GenieAshwani" target="_blank">Genie Ashwani</a>; official Java, Spring, GitHub, SQL and Docker documentation fills topic gaps. Links were checked in July 2026.
    </footer>
  </div>

  <div class="progress-wrap">
    <div class="progress-top"><span>Your progress</span><strong id="progressText">0%</strong></div>
    <div class="bar"><div class="fill" id="progressFill"></div></div>
  </div>

  <script>
    const checks = [...document.querySelectorAll('.check')];
    const key = 'java-roadmap-progress-v1';
    const saved = JSON.parse(localStorage.getItem(key) || '[]');
    checks.forEach((box, i) => {
      box.checked = Boolean(saved[i]);
      box.addEventListener('change', update);
    });
    function update(){
      const state = checks.map(c => c.checked);
      localStorage.setItem(key, JSON.stringify(state));
      const done = state.filter(Boolean).length;
      const pct = Math.round(done / checks.length * 100);
      document.getElementById('progressText').textContent = pct + '%';
      document.getElementById('progressFill').style.width = pct + '%';
    }
    update();
  </script>
</body>
</html>
