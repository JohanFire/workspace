# workspace-settings
Here I will storage all my workspace-settings such as VSCode, bash, vim, etc.


---

# AI tools
## Skills
Reusable instruction templates that teach Claude a specific workflow or behavior.
Defined in a `SKILL.md` file, invoked with `/skill-name` or automatically when
Claude detects they are relevant.
> Example: `/systematic-debugging` guides Claude to investigate the root cause before
proposing any fix.

---

## MCP Servers
External tools and data sources connected to Claude via the **Model Context Protocol**.  
They expose real capabilities Claude can execute: database queries, GitHub operations,   
API calls, etc. Configured in `.mcp.json`.
> Example: a GitHub MCP server lets Claude read PRs, create issues, and review commits.  

---

## Agents
Specialized AI assistants with their own system prompt, tool restrictions, and model.    
When you use an agent, it replaces Claude Code's default behavior for that session.      
> Built-in examples: `Explore` (read-only codebase analysis), `Plan` (architecture       
design).

---

## Sub-agents
Isolated assistants that Claude automatically creates and delegates to during a session  
to handle a specific task (research, review, debugging). They run in their own context   
and return results to the main conversation without polluting it.
> Spawned internally via the `Agent` tool or within custom agents.

---

## Plugins
Distributable packages that bundle skills, agents, hooks, and MCP servers to share       
across projects or teams. Plugin skills are namespaced to avoid conflicts
(`/plugin:skill`).
> Useful for standardizing configurations across multiple projects or sharing with       
teammates.

---

## Quick reference

| Concept    | What it is                     | When to use it                          |
|------------|--------------------------------|-----------------------------------------|
| Skill      | Instructions for Claude        | Teach processes or patterns             |
| MCP Server | External tool / API            | Connect Claude to external services     |
| Agent      | Session with its own identity  | Specialize Claude for a context         |
| Sub-agent  | Agent delegated by Claude      | Parallelize or isolate sub-tasks        |
| Plugin     | Distributable bundle           | Share extensions across projects        |

---

## Skills (sets and references)
[skills.sh](https://skills.sh/)
Today I use it mainly for Claude, but its useful for any other Agent tool like Windsurf, Copilot, etc.

### Elemental

**frontend-design**
```sh
npx skills add https://github.com/anthropics/skills --skill frontend-design
```

**interface-design**
```sh
npx skills add https://github.com/dammyjay93/interface-design --skill interface-design
```

**vercel-react-best-practices**
```sh
npx skills add https://github.com/vercel-labs/agent-skills --skill vercel-react-best-practices
```

**brainstorming**
```sh
npx skills add https://github.com/obra/superpowers --skill brainstorming
```

**systematic-debugging**
```sh
npx skills add https://github.com/obra/superpowers --skill systematic-debugging
```

**changelog-generator**
```sh
npx skills add https://github.com/composiohq/awesome-claude-skills --skill changelog-generator
```

**api-design-principles**
```sh
npx skills add https://github.com/wshobson/agents --skill api-design-principles
```

**error-handling-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill error-handling-patterns
```

**tailwind-design-system**
```sh
npx skills add https://github.com/wshobson/agents --skill tailwind-design-system
```

**python-testing-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill python-testing-patterns
```

**architecture-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill architecture-patterns
```

**architecture-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill code-review-excellence
```

**postgresql-table-design**
```sh
npx skills add https://github.com/wshobson/agents --skill postgresql-table-design
```

### More "optional" or in case you need them
Regla general: Las skills son herramientas, no reglas. Úsalas cuando el contexto lo
justifique. Usar tipos avanzados "siempre" puede llevar a over-engineering — código más  
complejo de lo necesario.

**prompt-engineering-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill prompt-engineering-patterns
```

**python-performance-optimization**
```sh
npx skills add https://github.com/wshobson/agents --skill python-performance-optimization
```

**fastapi-templates**
```sh
npx skills add https://github.com/wshobson/agents --skill fastapi-templates
```

**async-python-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill async-python-patterns
```

**typescript-advanced-types**
```sh
npx skills add https://github.com/wshobson/agents --skill typescript-advanced-types
```
Cuándo usarla                                                                                        
- Estás construyendo una librería o framework que otros van a usar                       
- Necesitas tipos genéricos complejos para APIs type-safe
- Implementas patrones avanzados (state management, form validation, discriminated
unions)
- Migras código JavaScript grande a TypeScript con arquitectura compleja
- Diseñas sistemas de tipos parametrizados

Cuándo NO la necesitas

- CRUD típico, REST APIs estándar
- Aplicaciones frontend cotidianas con React/Vue
- Scripts o utilities simples
- Código donde los tipos básicos (string, number, interfaces simples) son suficientes

**nodejs-backend-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill nodejs-backend-patterns
```

**nextjs-app-router-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill nextjs-app-router-patterns
```

**e2e-testing-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill e2e-testing-patterns
```
Cypress and Playwright

**github-actions-templates**
```sh
npx skills add https://github.com/wshobson/agents --skill github-actions-templates
```

**emil-design-eng**
CSS stuf
```sh
npx skills add https://github.com/emilkowalski/skill --skill emil-design-eng
```

**responsive-design**
CSS stuf
```sh
npx skills add https://github.com/wshobson/agents --skill responsive-design
```

**mobile-android-design**
```sh
npx skills add https://github.com/wshobson/agents --skill mobile-android-design
```

**mobile-ios-design**
```sh
npx skills add https://github.com/wshobson/agents --skill mobile-ios-design
```

**sql-optimization-patterns**
```sh
npx skills add https://github.com/wshobson/agents --skill sql-optimization-patterns
```

---

## MCP's (sets and references)
- [n8n-mcp](https://github.com/czlonkowski/n8n-mcp)

---

## Plugins (sets and references)
- [superpowers](https://github.com/obra/superpowers)
- [everything-claude-code](https://github.com/affaan-m/everything-claude-code)
    36 specialized agents, 147 skills, 51 commands
- [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)
- [claude-mem](https://github.com/thedotmack/claude-mem)


