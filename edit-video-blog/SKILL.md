---
name: edit-video-blog
description: Write a polished technical blog post from a video transcript and an initial draft. Use when the user provides a transcript and/or draft and wants a finished article suitable for publication.
---

Ask the user to provide:
- The **video transcript** (required — this is the source of truth for what was actually said)
- The **initial draft** article, if they have one
- The **YouTube video URL**, if they have one
- The **GitHub repository URL**, if any
- The **target audience** (e.g. "intermediate Go developers", "developers new to Kubernetes")

---

## Step 1 — Extract key points from the transcript

Read the full transcript. Extract:
- The core thesis or problem being solved
- Key technical concepts introduced, in the order they are introduced
- Any code snippets, commands, or concrete examples mentioned
- Memorable quotes or phrasing worth preserving verbatim
- Any caveats, gotchas, or nuances the speaker emphasized

Do NOT rely on the draft for this step — go straight to the transcript.

---

## Step 2 — Audit the draft against the transcript

If a draft was provided, compare it against your extraction:

- **Gaps**: what's in the transcript but missing from the draft?
- **Drift**: what's in the draft that doesn't reflect what was actually said? Flag these — don't silently drop them.
- **Code snippets**: the draft may contain code snippets that don't appear in the transcript — these are valuable and should be kept. The transcript is the source of truth for what was *said*, not for code.
- **Structure**: does the draft's order respect conceptual dependencies? (Information is a DAG — later concepts should not assume earlier ones that haven't been introduced yet.)

Present a brief summary of findings to the user before proceeding.

---

## Step 3 — Propose a section structure

Propose a heading outline for the article. Each section should:
- Map to a coherent chunk of the transcript
- Have a clear single purpose
- Build on what came before

Also decide where the YouTube embed and GitHub link will appear. Usually:
- GitHub link goes early, near the introduction, so readers can follow along
- YouTube embed goes at the end, as a "watch the full walkthrough" call to action

Confirm the structure with the user before writing.

---

## Step 4 — Write the article

Write each section in order. For each section:

- Use the transcript as the source of truth for technical accuracy
- Write for **readers who will not watch the video** — the article must stand alone
- Use **maximum 3–4 sentences per paragraph**; prefer short, declarative sentences
- Include code blocks for any commands, snippets, or config shown in the video
- Preserve technical precision — don't smooth over nuance or caveats the speaker mentioned

Avoid:
- Filler phrases ("In this section, we will...", "As we can see...")
- Re-stating the section heading in the first sentence
- Padding that wasn't in the transcript

---

## Step 5 — Add the YouTube embed and GitHub link

At the end of the article, add the YouTube video as a plain Markdown link placeholder:

```markdown
[VIDEO](YOUTUBE_URL)
```

Replace `YOUTUBE_URL` with the URL provided by the user.

If a GitHub repo was provided, add a contextual link near the top of the article (e.g. in the intro paragraph or as a callout block):

```markdown
> The full source code is available at [github.com/user/repo](https://github.com/user/repo).
```

---

## Step 6 — Final review

Before presenting the finished article, check:
- [ ] Every technical claim is grounded in the transcript
- [ ] No section assumes knowledge introduced later
- [ ] Code blocks are properly fenced with the correct language identifier
- [ ] YouTube placeholder link is present at the end
- [ ] The article reads well without needing to watch the video
