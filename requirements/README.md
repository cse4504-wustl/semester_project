# Requirements: Merge, Address Feedback, and Expand

Team project kickoff

## Goal

By the end of this activity, your team has **one requirements document** that:

1. merges the requirements drafts your teammates wrote in their earlier groups, with duplicates removed and nothing lost;
2. addresses the instructor's feedback, or logs why a comment is still open;
3. expands your **three most important user stories** (your tracer bullets) with acceptance criteria and links to the business rules that apply.

The finished document is saved and committed as **`requirements/requirements.md`** in this repository.

## Before you start

- Each of you has the requirements document draft **your group** wrote earlier, and the instructor's feedback on it. If some of you were in the same group, you share one draft. Bring each distinct draft once.
- Choose a **scribe**. The scribe runs the Claude merge, holds the merged file, and applies the team's edits. The other two check and challenge. 
- The scribe has this repository cloned and open in an editor.

## Steps at a glance

| Step | Who | What you produce |
| --- | --- | --- |
| 1. Merge with Claude | Whole team | One merged draft of `requirements.md`, checked by you |
| 2. Address feedback | Whole team | Each comment ticked off, fixed, or logged under Open Questions |
| 3. Choose tracer-bullet stories | Whole team | Three stories moved into section 2 of the file |
| 4. Expand | In parallel, one story each | Acceptance criteria and rule links for each of the three stories |
| 5. Cross-review, then commit | Pairs, then the scribe | A checked file committed to `requirements/requirements.md` |

The instructor will visit each team after step 3 to ask which three stories you chose and why.

---

## Step 1: Merge with Claude

If **all of you were in the same group**, you have one draft. Skip to step 2.

Claude is good at the mechanical part of merging: finding overlapping stories and rules and reconciling IDs. It can also drop items or invent them, so **your team owns the final document and must check Claude's work.**

### How to do it

1. Open Claude in a new chat.
2. Copy the prompt below into the message box.
3. Attach the unique drafts of your requirements to the chat. Then send the message.
4. Read the reply. If Claude asks a question, answer briefly.
5. If something is wrong, tell Claude in the same chat what to fix, for example: "US-04 from Draft 2 is missing from the merged file. Add it and update the report."
6. Check the result with the verification checklist below.
7. Copy **Part A only** into `requirements/requirements.md`. Keep Part B (the merge report) for reference. It does **not** go in the repository.

### The merge prompt (copy everything in this box)

```text
You are helping a team of three software engineering students merge requirements drafts into one document. The drafts were written by different groups, so they overlap, use different wording, and use different ID numbers. Your job is to merge them faithfully and to show your work so the team can check it.

RULES YOU MUST FOLLOW

1. Do not invent requirements. Every user story and business rule in your output must come from at least one draft. If something seems to be missing, list it under Open Questions instead of adding it.
2. Do not drop anything silently. Every story and rule in every draft must either appear in the merged document or be listed in the merge report as a duplicate of a specific merged item.
3. Merge two items only if they describe the same need or the same rule. When they overlap partly, keep the clearer wording and combine details that add information. If you are unsure whether two items are duplicates, keep both and flag them in the report.
4. Keep the original meaning. You may fix grammar and formatting lightly, but do not change what a story or rule requires.
5. Write each user story as: "As a <specific role>, I want <capability>, so that <benefit>." If a draft story is missing its role or benefit, keep it as written and flag it in the report. Do not make one up.
6. Give user stories new IDs (US-01, US-02, ...) and business rules new IDs (BR-01, BR-02, ...), numbered in a consistent order. Where a story refers to a business rule, update the reference to the new BR ID.
7. If drafts contradict each other, do not choose a side. Put both versions under Open Questions and in the report.
8. Do not write acceptance criteria and do not rank the stories. The team will do both later.
9. If a draft contains comments from an instructor, leave them out of the merged document, but list them in the report so the team can address them next.

OUTPUT

Give me the merged document, inside a single markdown code block so I can copy it. Use the same structure as in the original drafts.

```

### Verification checklist: check Claude's work before you use it

- [ ] Pick three stories from each draft and find every one of them in the merged file.
- [ ] Every duplicate that Claude merged really is the same need or rule. Split any that are not.
- [ ] Nothing in the merged file is unfamiliar to all of you (nothing was invented).
- [ ] Contradictions and gaps are listed under Open Questions.

---

## Step 2: Address feedback in the merged file

Check each comment on your group's draft against the merged file. Many comments may already be fixed, either by your group's later revisions or by the merge.

Each of you checks the feedback on **your own group's draft**, because you know that draft's context. Tell the scribe what to change, and the scribe applies it.

| Label | Meaning | What to do |
| --- | --- | --- |
| Already addressed | Your group's revisions or the merge already handle it | Tick it off |
| Needs a fix | It is still open in the merged file | Tell the scribe what to change in the merged file |
| Unclear | You do not understand it, or you disagree | Ask the instructor, or log it under Open Questions |

Every comment ends up ticked off, fixed, or logged under **Open Questions** with the reason. None are silently skipped.

---

## Step 3: Choose three tracer-bullet stories

A **tracer-bullet story** is one that, once built, gives a thin but working path through every layer of your system. Building these first proves your architecture and gives early feedback on your riskiest assumptions. Choose stories that meet most of these criteria:

- **Core value:** users would immediately notice if it were missing.
- **End to end:** it touches every layer, from the user interface through the use case to data storage.
- **Risk:** it exposes the least certain technology or requirement.
- **Small:** one teammate could build it in a few days once it is designed.
- **Connected:** together the three stories form one coherent path through your product, for example create, view, and update.

Agree on three stories as a team. You will expand them with acceptance criteria in step 4. 

---

## Step 4: Expand your story (in parallel)

Each teammate expands one tracer-bullet story:

1. Write **acceptance criteria** in Given/When/Then form. Write at least two: a normal case and a failure or edge case.
2. **Link the business rules** that apply, by ID. If a rule the story depends on is missing from section 4, add it there, or record the gap under Open Questions.
3. Make sure every criterion describes something a teammate could **observe or test**.

The scribe integrates everyone's work into the file.

## Step 5: Cross-review, then commit

### Cross-review

Review the story written by the teammate to your left against the checklist below. Fix what you can now. Log anything unresolved under Open Questions.

### Quality checklist

- [ ] Nothing was lost or invented in the merge: three stories from each source draft appear in the merged file.
- [ ] Every instructor comment is marked already addressed or fixed, or is listed under Open Questions with the reason it is unresolved.
- [ ] No duplicate stories or rules, and every US and BR ID is unique.
- [ ] Exactly three stories are in section 2 (Tracer Bullet Stories), and together they form one coherent path.
- [ ] Each tracer-bullet story has at least two testable acceptance criteria: a normal case and a failure or edge case.
- [ ] Each tracer-bullet story links its business rules, and every linked ID exists in section 4 (Business Rules).
- [ ] Business rules are numbered, testable, and stated separately from the stories.
- [ ] Contradictions between drafts are resolved or listed under Open Questions.

### Commit

The scribe saves the finished document as `requirements/requirements.md` and commits it. The `requirements` directory already exists in your repository; keep any placeholder file that is already there.

**Command line:**
Note, that for the time being, the `main` branch is not locked and you can push your requirements directly to main. Once we start development, `main` branch will be locked and we will follow the GitHub workflow we practiced.

```bash
git pull
git add requirements/requirements.md
git commit -m "Add merged team requirements with tracer-bullet stories"
git push origin main
```

**GitHub web editor:** open the `requirements` folder in your repository, choose **Add file**, then **Create new file** (or **Upload files**), name it `requirements.md`, paste the content, and commit.

Then the other two teammates run `git pull` and open `requirements/requirements.md` on GitHub to confirm it renders with headings, lists, and your three expanded stories.

---

## Done when

- [ ] `requirements/requirements.md` is on `main` and renders correctly on GitHub.
- [ ] All three teammates can see it after a `git pull`.
- [ ] It contains three expanded tracer-bullet stories, numbered business rules, and an Open Questions section.
- [ ] The commit message says what changed.
