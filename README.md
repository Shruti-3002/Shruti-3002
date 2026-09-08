<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0A66C2,100:1e3a8a&height=140&section=header&animation=fadeIn" alt="" />

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

Recently: a flash-sale system that survives a 500-way race, a six-service microservices platform
on Kafka and Neo4j, and a real-time chat app running on AWS.

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
<summary><b>🔗 LinkedIn Microservices</b> — a social platform as six independent Spring Boot services</summary>

<br>

Six services behind a **Spring Cloud Gateway**, discovering each other through **Netflix Eureka**:

```
api-gateway ──▶ user-service        auth, JWT issuing
            ├─▶ posts-service       content + engagement
            ├─▶ connection-service  social graph in Neo4j
            └─▶ notification-service consumes Kafka events
                discovery-server    Eureka registry
```

**What made it interesting:** the social graph lives in **Neo4j** rather than PostgreSQL, because
first-degree connection traversal is what graph databases are actually for. Posts, likes and
connection requests publish **Kafka** events that the notification service consumes asynchronously,
so a slow notification never blocks a post. JWT validation happens once, at the gateway.

<p>
<img src="https://img.shields.io/badge/Java_21-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white" />
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
<img src="https://img.shields.io/badge/Neo4j-4581C3?style=flat-square&logo=neo4j&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Eureka-6DB33F?style=flat-square&logo=spring&logoColor=white" />
</p>

**[→ View repository](https://github.com/Shruti-3002/linkedInApp)**

</details>

<details>
<summary><b>💬 Cirql (TripChat)</b> — real-time group chat for travellers, full stack and deployed</summary>

<br>

**React 19 + TypeScript** front end, **Spring Boot** back end, real-time messaging over
**WebSocket/STOMP**. Designed for 1,000 daily active users with sub-100ms delivery.

**What made it interesting:** messages are persisted through a **Kafka outbox pattern**, so a
message is never acknowledged to the sender unless it is durably stored — no lost messages if a
consumer dies mid-flight. Redis backs presence and unread counts. Runs on **AWS ECS Fargate**
behind CloudFront and an ALB, with RDS, ElastiCache and MSK Serverless, deployed by GitHub Actions.
Includes load testing and written system-design docs.

<p>
<img src="https://img.shields.io/badge/React_19-61DAFB?style=flat-square&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white" />
</p>

**[→ View repository](https://github.com/Shruti-3002/cirql)**

</details>

---

### 📦 Also on my profile

**[Rate Limiter](https://github.com/Shruti-3002/Rate-Limiter)** · request throttling in Java &nbsp;•&nbsp;
**[Marketplace Service](https://github.com/Shruti-3002/marketplace_service)** · Java backend service &nbsp;•&nbsp;
**[Weather Service](https://github.com/Shruti-3002/weather-service)** · API integration &nbsp;•&nbsp;
**[Budget Manager](https://github.com/Shruti-3002/budget-manager)** &nbsp;•&nbsp;
**[Movie Recommendation](https://github.com/Shruti-3002/Movie-Recommendation-)** · Python

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
<img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white" />
<img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white" />
<img src="https://img.shields.io/badge/REST_APIs-005571?style=for-the-badge&logo=fastapi&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white" />
<img src="https://img.shields.io/badge/Neo4j-4581C3?style=for-the-badge&logo=neo4j&logoColor=white" />
<img src="https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white" />
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" />
</p>

<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" />
<img src="https://img.shields.io/badge/JUnit-25A162?style=for-the-badge&logo=junit5&logoColor=white" />
<img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" />
</p>

---

### 🐍 Contributions

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Shruti-3002/Shruti-3002/output/github-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Shruti-3002/Shruti-3002/output/github-snake.svg" />
    <img alt="contribution snake" src="https://raw.githubusercontent.com/Shruti-3002/Shruti-3002/output/github-snake.svg" />
  </picture>
</p>

---

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=18&duration=4000&pause=800&color=0A66C2&center=true&vCenter=true&width=520&lines=Open+to+backend+%26+distributed+systems+roles;Let's+build+something+that+survives+load" alt="" />
</p>

<p align="center">
  <a href="mailto:gshruti844@gmail.com">
    <img src="https://img.shields.io/badge/Say_hi-0A66C2?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
</p>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:1e3a8a,100:0A66C2&height=120&section=footer" alt="" />
