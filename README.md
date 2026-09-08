## Hi, I'm Shruti Gupta

Backend engineer. I build distributed systems in Java and Spring Boot, and I'm
most interested in the parts that break under concurrency — race conditions,
transaction isolation, and the gap between "it works" and "it works when 500
people do it at once."

📫 gshruti844@gmail.com · [LinkedIn](https://www.linkedin.com/in/shruti-gupta-706b931b1/)

---

### 🔨 What I've been building

**[Flash Sale System](https://github.com/Shruti-3002/Flash_Sale)** — selling exactly 1,000 units to 5,000,000 people without selling 1,001.
> I wrote the naive implementation first and proved it broken: **500 concurrent buyers reserved 100 items — 400 oversold, with zero errors thrown.** Fixed it with atomic SQL claims and a row-level unit pool using `SELECT … FOR UPDATE SKIP LOCKED`, bringing oversells to **zero while raising throughput 80%**. Adds a Redis waiting room with fair randomized queuing and a Spring Cloud Gateway that rejects unadmitted traffic at the edge.
>
> `Java` `Spring Boot` `PostgreSQL` `Redis` `Spring Cloud Gateway` `Docker` `Testcontainers`

**[Rate Limiter](https://github.com/Shruti-3002/Rate-Limiter)** — request throttling in Java.

**[Marketplace Service](https://github.com/Shruti-3002/marketplace_service)** — Java backend service.

**[Weather Service](https://github.com/Shruti-3002/weather-service)** — API integration service.

---

### 🧰 Stack

**Languages** &nbsp;Java · Python · JavaScript · SQL

**Backend** &nbsp;Spring Boot · Spring Data JPA · Spring Cloud Gateway · REST APIs · Hibernate

**Data** &nbsp;PostgreSQL · Redis · Flyway

**Tools** &nbsp;Docker · Maven · Testcontainers · JUnit · Git · Postman

---

### 📊 GitHub

<img src="https://github-readme-stats.vercel.app/api?username=Shruti-3002&show_icons=true&hide_border=true" alt="stats" height="150" />
<img src="https://github-readme-stats.vercel.app/api/top-langs?username=Shruti-3002&layout=compact&hide_border=true" alt="languages" height="150" />
