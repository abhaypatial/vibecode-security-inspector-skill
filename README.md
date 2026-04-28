<div align="center">
  <img src="logo.png" alt="VibeCode Security Inspector Logo" width="220" />

  <h1>🛡️ VibeCode Security Inspector 🛡️</h1>
  
  <p><strong>The ultimate agent skill to lock down vibe-coded apps across all major AI assistants.</strong></p>

  <p>
    <img src="https://img.shields.io/badge/Security-Vibe--Coded-DC2626?style=for-the-badge&logo=shield" alt="Security" />
    <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" alt="MIT License" />
    <img src="https://img.shields.io/badge/Built_By-Abhay_Patial-indigo?style=for-the-badge" alt="Author" />
  </p>
</div>

---

## ⚡ What is this?

AI coding assistants are magical. They build features fast, but they consistently hallucinate **security fundamentals**. They will hardcode your secrets, bypass row-level security, trust client-submitted prices, and leak data via Server Components. 

**VibeCode Security Inspector** is a custom set of "skills" and instructions that you can plug into your favorite AI code assistant to catch these patterns *before* they make it to production.

## 🚀 Supported AI Assistants

We've added native support for all the major players. Whether you're running terminal agents or IDEs, we've got you covered:

- 🔵 **Google Gemini & Antigravity**
- 🟢 **OpenAI Codex**
- 🟠 **Anthropic Claude Code**
- 🟣 **Cursor IDE**
- 🌊 **Windsurf Editor**
- 🐙 **GitHub Copilot**

## 📦 Installation

### For Terminal Agents (Claude Code, Codex, Antigravity, Gemini CLI)

```bash
npx skills add https://github.com/AbhayPatial/vibecode-security-inspector-skill --skill vibecode-security-inspector
```
*(Requires Node.js installed)*

### For IDEs (Cursor, Windsurf, GitHub Copilot)

Clone this repository and copy the `vibecode-security-inspector` folder directly into your workspace.

```bash
git clone https://github.com/AbhayPatial/vibecode-security-inspector-skill.git
cp -r vibecode-security-inspector-skill/vibecode-security-inspector/ .cursor/rules/ # Or equivalent for your IDE
```
Then, prompt your IDE: *"@workspace Run the VibeCode Security Inspector audit on this project."*

## 🔍 The Hitlist: What We Catch

We specifically target the massive blind spots that major AI assistants miss when "vibe coding" modern web apps. 

| 🛡️ Category | 🚨 What It Catches |
|-------------|-------------------|
| **Server Components (RSC)** | 🆕 Leaking database records in Next.js Server Components, over-fetching data. |
| **Server Actions** | 🆕 Unprotected `"use server"` endpoints missing authorization checks. |
| **Secrets & Env Vars** | Hardcoded API keys, secrets exposed in `NEXT_PUBLIC_`/`VITE_` vars. |
| **Database Security** | Disabled Supabase RLS, `USING (true)` policies, Firebase `allow: if true` rules. |
| **Auth & Authorization** | Trusting `jwt.decode()`, middleware-only auth, tokens in localStorage. |
| **Payments** | Client-submitted prices via Stripe, missing webhook signature verification. |
| **Mobile** | API keys in Expo JS bundle, `AsyncStorage` for tokens, unsafe deep links. |
| **AI / LLM** | Exposed OpenAI keys, missing token usage caps, prompt injection vulnerabilities. |
| **Data Access** | SQL injection, Prisma `$queryRawUnsafe`, mass assignment flaws. |

## 💡 How It Works

1. **Context Loading**: When you trigger the skill or mention security, your AI assistant reads the `SKILL.md` manifest.
2. **Dynamic References**: It cross-references your tech stack. If you use Next.js, it loads the RSC and Server Action security rules. If you use Stripe, it loads payment rules.
3. **Audit Execution**: The AI reviews your codebase strictly against these ground-truth rules instead of relying on its flawed training data.

---

<div align="center">
  <p>Contributions, corrections, and improvements are very welcome!</p>
  <p>Created with 💻 by <b>Abhay Patial</b></p>
</div>
