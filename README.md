# ⚽ Cabana Cup Legends 2026

Plataforma oficial de avaliação de jogadores da **Cabana Cup**, com ranking, Hall da Fama e prêmios especiais — estilo EA FC Ultimate Team.

---

## 🚀 Deploy

Este projeto é um **site estático** (HTML + Firebase). Sem build, sem dependências, sem servidor.

### Vercel (recomendado)

1. Faça fork ou importe este repositório no [Vercel](https://vercel.com)
2. Em **Framework Preset**, selecione **Other**
3. Clique em **Deploy** — pronto ✅

O arquivo `vercel.json` já está configurado corretamente.

---

## 🔥 Firebase

O projeto usa **Firebase** para banco de dados e autenticação.

As credenciais já estão configuradas no `index.html`. Certifique-se de que o projeto Firebase está com as seguintes configurações:

### Firestore — Regras (modo desenvolvimento)

No [Firebase Console](https://console.firebase.google.com) → Firestore → Regras:

```
rules_version = '2';
service cloud.firestore.default_database {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

### Firebase Storage — Regras

No Firebase Console → Storage → Regras:

```
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read, write: if true;
    }
  }
}
```

> ⚠️ As regras acima são para desenvolvimento. Em produção, implemente autenticação adequada.

---

## 🧩 Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| 🔐 Login / Cadastro | Username + Telefone (sem email) |
| 🃏 Cards de Jogadores | Estilo EA FC Ultimate Team |
| ⭐ Sistema de Avaliação | Nota geral + 7 skills com estrelas |
| 🏆 Craque da Partida | Calculado automaticamente |
| 🏛️ Hall da Fama | Pódio visual + ranking completo |
| 🎖️ Prêmios | 10 prêmios divertidos (Craque, GOAT, Artilheiro, Cone...) |
| 👑 Painel Admin | Cadastro, edição e exclusão de jogadores |
| 📸 Upload de Fotos | Armazenadas no Firebase Storage |

---

## 🗂️ Estrutura

```
cabana-cup/
├── index.html       # App completo (frontend + integração Firebase)
├── vercel.json      # Configuração de deploy estático no Vercel
├── .gitignore
└── README.md
```

---

## 👤 Login Admin padrão

| Campo | Valor |
|---|---|
| Usuário | `admin` |
| Telefone | `(11) 00000-0000` |

> Recomendado alterar após o primeiro acesso no painel Admin.

---

## 🛠️ Tecnologias

- **HTML5 / CSS3 / JavaScript** (vanilla, sem build)
- **Firebase Firestore** — banco de dados em tempo real
- **Firebase Storage** — armazenamento de fotos
- **Firebase Analytics**
- **Google Fonts** — Bebas Neue, Rajdhani, Inter

---

Feito com ❤️ para a Cabana Cup 2026
