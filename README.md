<h1 align="center">Hi, I'm Shruti Gupta 👋</h1>

<p align="center">
  <a href="https://github.com/Shruti-3002">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&duration=3000&pause=1000&color=0A66C2&center=true&vCenter=true&width=560&lines=Backend+Engineer;Java+%7C+Spring+Boot+%7C+PostgreSQL+%7C+Redis;I+build+systems+that+survive+concurrency" alt="Backend Engineer" />
  </a>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/shruti-gupta-706b931b1/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="mailto:gshruti844@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://github.com/Shruti-3002?tab=repositories">
    <img src="https://img.shields.io/badge/Projects-181717?style=for-the-badge&logo=github&logoColor=white" alt="Projects" />
  </a>
</p>

---

### 👩‍💻 About

I build distributed backend systems in **Java** and **Spring Boot**. What interests me most
is the part that breaks under load — race conditions, transaction isolation, and the gap
between *"it works"* and *"it works when 500 people do it at the same instant."*

---

### 🔨 Featured Work

<details open>
<summary><b>⚡ Flash Sale System</b> — selling exactly 1,000 units to 5,000,000 people without selling 1,001</summary>

<br>

I wrote the naive implementation **first**, and proved it broken:

| Implementation | Oversold | Throughput |
|---|---:|---:|
| `SELECT` → check → `UPDATE` | **400** ❌ | 1,174 req/s |
| Atomic conditional `UPDATE` | 0 ✅ | 1,563 req/s |
| Unit pool + `SKIP LOCKED` | 0 ✅ | **2,110 req/s** |

> 500 concurrent buyers, 100 units, released simultaneously. The naive version sold **500 items
> out of 100 stock and threw zero errors** — two threads read `inventory = 100` and both wrote `99`.

**What's in it:** row-level inventory pool claimed with `FOR UPDATE SKIP LOCKED` · lazy reclamation
of abandoned holds via a `claimable_at` timestamp · webhook payment settlement with a
compare-and-swap fence · Redis waiting room with randomized fair queuing · Spring Cloud Gateway
rejecting unadmitted traffic at the edge · 46 Testcontainers integration tests.

<p>
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
</p>

**[→ View repository](https://github.com/Shruti-3002/Flash_Sale)**

</details>

<details>
<summary><b>🚦 Rate Limiter</b> — request throttling in Java</summary>
<br>

*(add a line here: which algorithm, and what it protects)*

**[→ View repository](https://github.com/Shruti-3002/Rate-Limiter)**
</details>

<details>
<summary><b>🛒 Marketplace Service</b> — Java backend service</summary>
<br>

*(add a line here: what it does and the interesting part)*

**[→ View repository](https://github.com/Shruti-3002/marketplace_service)**
</details>

<details>
<summary><b>🌦️ Weather Service</b> — API integration service</summary>
<br>

*(add a line here: what it integrates and how it handles failure)*

**[→ View repository](https://github.com/Shruti-3002/weather-service)**
</details>

---

### 🧰 Stack

<p>
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
<img src="https://img.shields.io/badge/SQL-025E8C?style=for-the-badge&logo=amazondynamodb&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Cloud-6DB33F?style=for-the-badge&logo=spring&logoColor=white" />
<img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white" />
<img src="https://img.shields.io/badge/REST_APIs-005571?style=for-the-badge&logo=fastapi&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" />
<img src="https://img.shields.io/badge/JUnit-25A162?style=for-the-badge&logo=junit5&logoColor=white" />
<img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" />
</p>

---

### 📊 GitHub

<p align="center">
  <img src="https://streak-stats.demolab.com?user=Shruti-3002&hide_border=true&ring=0A66C2&fire=0A66C2&currStreakLabel=0A66C2" alt="contribution streak" />
</p>

<p align="center"><i>Open to backend and distributed systems roles — <a href="mailto:gshruti844@gmail.com">say hi</a>.</i></p>
