# 

Clean, scalable, professional structure for:

- Frontend
- Backend
- Database
- AI/GenAI
- APIs
- Deployment

---

# Recommended Structure

```txt
project-name/
│
├── client/                     # Frontend Application
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   │   ├── ui/
│   │   │   ├── layout/
│   │   │   └── sections/
│   │   │
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── store/
│   │   ├── lib/
│   │   ├── utils/
│   │   ├── styles/
│   │   ├── assets/
│   │   ├── context/
│   │   └── types/
│   │
│   ├── package.json
│   ├── next.config.js
│   └── .env.local
│
├── server/                     # Backend Application
│   ├── src/
│   │   ├── routes/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── db/
│   │   ├── config/
│   │   ├── utils/
│   │   ├── ai/
│   │   │   ├── prompts/
│   │   │   ├── agents/
│   │   │   ├── embeddings/
│   │   │   ├── rag/
│   │   │   └── providers/
│   │   │
│   │   └── app.js
│   │
│   ├── prisma/
│   │   ├── schema.prisma
│   │   └── migrations/
│   │
│   ├── package.json
│   └── .env
│
├── shared/                     # Shared types/constants
│   ├── constants/
│   ├── schemas/
│   └── types/
│
├── docs/                       # Documentation
│
├── .gitignore
├── README.md
├── docker-compose.yml
└── package.json                # Optional root workspace