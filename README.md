# AI Coding Skills: Lazy & Rigorous Engineering

## Why This Exists

These skills turn any AI assistant into a **lazy, senior engineer** — the kind who writes less code, fixes root causes, and ships working software without drama. They combine:

- **Ponytail principles** (shortest working diff, no speculative abstractions)
- **Andrej Karpathy’s behavioral guidelines** (think before coding, surface tradeoffs)
- **Linus Torvalds‑grade pragmatism** (surgical changes, YAGNI, reuse over rewrite)

The result? An AI that acts like a 12‑year veteran who *knows* when to be lazy and when to be rigorous.

## What’s Inside

- **SKILLS.md** – the full rule set.  
- **SKILLS_LITE.md** – a shorter, to‑the‑point version (same core ideas, fewer examples).

Both files are **ready to paste** into your AI tool of choice.

## How to Use These Skills

### For Web‑Based AI (ChatGPT, Claude, etc.)

1. Copy the **entire** content of `SKILLS.md` (or `SKILLS_LITE.md`).
2. Paste it as:
   - A **system prompt** (if available), or
   - The **first message** of a new conversation.
3. Then state your task normally. The AI will now follow the lazy‑rigorous discipline.

### For Cursor

- Put the content into a **`.cursorrules`** file in your project root.
- Cursor automatically applies those rules to every new chat.

### For GitHub Copilot

- **Copilot Chat**: paste the skills as a system message before your question.
- **Copilot Edits / Completions**: you can add the content to a project‑level `README` or a custom instructions file (if using Copilot Enterprise).

### For Aider

Use the `--system-prompt` flag:

```bash
aider --system-prompt "$(cat SKILLS.md)" --message "Your task here"
```

Or, if you want to keep it in the conversation:

```bash
aider --message "Read and adopt the following guidelines: $(cat SKILLS.md)" --message "Now, do this task..."
```

### For Cline / Continue.dev

Add the rules as a **global instruction** in your extension settings, or include them in a `cline_instructions.md` file referenced in the prompt.

## Feeding Context with Repomix

To make the AI truly effective, you need to give it **codebase context**. That’s where [Repomix](https://github.com/yamadashy/repomix) comes in.

**Repomix** packs your entire repository into a single XML file (`repomix-output.xml`). The AI can read that file to understand the whole codebase, then apply the skills to suggest changes.

### How to Use Repomix

1. Install Repomix:

```bash
npm install -g repomix
```

Or use the web version at [repomix.com](https://repomix.com).

2. Generate the packed file:

```bash
repomix
```

   This creates `repomix-output.xml` in your current directory.

3. Provide it to the AI:
   - **ChatGPT / Claude**: Upload the XML file (or paste its content) along with your request.
   - **Cursor**: Drop the file into your project root; the AI can read it via context.
   - **Aider**: Pass the file with your request:
     aider --message "Read repomix-output.xml for context, then ..."

Now the AI can analyze your entire codebase and propose **surgical, context‑aware** changes — exactly what these skills are designed for.

## Example Workflow

1. **Generate context**:
   repomix

2. **Start a new chat** with your AI tool and paste `SKILLS.md` as the system prompt.

3. **Provide the task** and attach `repomix-output.xml`.

4. The AI will:

   - Understand your codebase.
   - Climb the “lazy ladder” (reuse, standard libs, etc.).
   - Write the **shortest working diff**.
   - Avoid unnecessary refactors.
   - Leave a `ponytail:` comment if it takes a shortcut, explaining the tradeoff.

## Quick Tips

- **Always use `SKILLS.md` first**; switch to `SKILLS_LITE.md` if you hit token limits.
- For **bash‑mode** tasks (generating shell scripts), the skills include a special `bash mode` – just mention it in your request.
- If the AI asks too many clarifying questions, that’s a *good* sign – it’s following the “think before coding” rule.

## Links

- [Repomix GitHub](https://github.com/yamadashy/repomix)  
- [Repomix Web](https://repomix.com)
  
- [Ponytail GitHub](https://github.com/DietrichGebert/ponytail) 
- [Andrej Karpathy Skills GitHub](https://github.com/multica-ai/andrej-karpathy-skills)

Niyaz Gimadiev <niyaztutor@gmail.com> with ❤️