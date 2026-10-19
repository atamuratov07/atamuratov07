# Damir Atamuratov

Full-stack web developer from Tashkent. For more than two years I have been designing, building and deploying web services on my own, mostly in TypeScript and Python. My main project, GeoRally, is a real-time multiplayer game running in production.

## Projects

### GeoRally · [georally.world](https://georally.world) · [code](https://github.com/atamuratov07/georally-game)

A browser geography game with solo practice and live multiplayer rooms, including a classroom mode where the teacher controls the pace and sees every player's answer. Available in English, Russian and Uzbek.

- Restructured how the server broadcasts game state. Each update is now serialized once per room, and a player receives a small personal part only when it changes. In a 30-player room, messages per answer fell from 32 to 3, and server traffic per game fell from 62 MB to 9 MB.
- Load-tested full games with up to 930 connected clients, checking every answer and final result. With 15 rooms answering at the same moment, answer-to-reveal p95 latency fell from 259 ms to 77 ms.
- Built an offline pipeline that generates the map tiles and country data from open sources, so the game uses no paid map provider. A full rebuild went from 108 s to 9.7 s with byte-identical output.

**Stack:** TypeScript, Node.js, Express, Socket.IO, Zod, React, MapLibre GL, Vitest, Docker Compose, nginx

### Qiraa · [live](https://qiraa-lab2.onrender.com) · [code](https://github.com/atamuratov07/qiraa)

A web app for preparing for an Arabic language assessment, with timed reading and grammar quizzes, and progress tracking. Users keep private content and share common content.

- Wrote the access rules for private, shared and admin-managed content once, applied as SQL, with Postgres constraints that reject invalid ownership states.
- Kept past results unchanged when content is edited by giving each attempt its own copy, and moved existing data to it with a three-step migration.
- Implemented sign-in without an auth library: Argon2id password hashing, session tokens stored only as hashes, and no way to probe which usernames exist.

**Stack:** Python, FastAPI, SQLAlchemy, Alembic, PostgreSQL, pytest, GitHub Actions, Docker

### AI Trading Chart Analysis MVP · team project (private code)

A web app, API and Telegram bot that analyse a trading-chart screenshot and return a trade setup. I worked in a senior backend developer's codebase on tasks he assigned and presented my work at weekly reviews.

- Moved storage from Redis to PostgreSQL to give users an analysis history, and rewrote the rate limiter as a single atomic SQL statement.
- Replaced shared API keys with per-user sign-in, with session tokens verified locally on every request instead of through a call to the auth provider.
- Built the Telegram bot, which runs the same analysis pipeline on a chart photo sent in chat.

**Stack:** TypeScript, Fastify, PostgreSQL, Prisma, Clerk, grammY, Next.js, Docker Compose

## Algorithms

- National stage of Uzbekistan's informatics olympiad, 35th place.
- Yandex Algorithm Training, season 10 (2026): 170th of 1,300+ participants, top-300 certificate.

I solve problems in C++ and Python.

## Skills

- **Languages:** TypeScript, Python, C++, SQL
- **Backend:** Node.js, Express, Fastify, Socket.IO, FastAPI, SQLAlchemy, Prisma
- **Data and infrastructure:** PostgreSQL, Redis, Docker, nginx, GitHub Actions
- **Frontend:** React, Next.js, Tailwind CSS
- **Spoken:** Russian (native), English (C1, IELTS 8.0), Uzbek (B2)

## Contact

[Telegram](https://t.me/damir_atam) · [Email](mailto:atam.damir@gmail.com)
