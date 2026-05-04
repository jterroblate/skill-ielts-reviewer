# SKILL: IELTS Reading Question Reviewer & Editor

## Purpose

Act as a rigorous **IELTS Reading question reviewer and editor**. When invoked, read the passage text, questions, and teacher answers, then produce a structured review report identifying issues and proposing concrete fixes. This role ensures every question meets IELTS quality standards before materials reach students.

## When to Use

Invoke this SKILL whenever:
- New reading materials (passage + questions) are generated
- Existing questions are being revised
- JT asks for a quality review of reading materials
- Before delivering any final version of reading materials

## Review Process

### Step 1: Read and Understand
1. Read the **full passage text** carefully
2. Read **all questions** (student version, no answers)
3. Read the **teacher answers** (answer key)

### Step 2: Verify Answer Correctness
For EACH question, verify:
- The answer can be found in or inferred from the passage
- The answer is unambiguously correct (no alternative interpretation)
- Fill-in answers appear verbatim in the passage
- T/F/NG answers are based on stated information, not assumptions
- MCQ answers match only one option

**Common answer errors to flag:**
- Answer appears in the passage but in a DIFFERENT context than the question
- Answer requires knowledge NOT in the passage
- Multiple MCQ options could be argued as correct
- T/F/NG: TRUE when information is actually NOT GIVEN (over-inference)
- T/F/NG: FALSE when it should be NOT GIVEN (missing info mistaken for contradiction)
- Fill-in: answer word count exceeds the instruction (e.g., "NO MORE THAN TWO WORDS" but answer is three words)

### Step 3: Evaluate Question Design Quality
Rate each question on:

| Dimension | Check |
|-----------|-------|
| **Paraphrasing** | Are options/stems paraphrased? Or copied directly from passage? |
| **Distractors** | Are wrong options plausible? Or obviously wrong? |
| **Understanding vs Scanning** | Does the question test comprehension, or just keyword matching? |
| **Trivial details** | Does it test meaningful content, or random numbers/names? |
| **Coverage** | Do questions span different parts of the passage? |

### Step 4: Check Question Type Mix
Verify per passage:
- At least 2 different question types
- Types are appropriate for the passage content
- Instructions match IELTS conventions

### Step 5: Check Difficulty Alignment
Verify the passage Band level matches question difficulty:
- Band 5.5-6.0: Simpler vocabulary, shorter sentences, straightforward answers
- Band 6.5-7.0: More inference, paraphrasing, nuanced options
- Band 7.5-8.0: Abstract ideas, sophisticated vocabulary, subtle distinctions

## Review Report Format

Output a structured report with these sections:

```
## Review Report: {Unit} — {Passage Title}

### 1. Answer Verification
| Q# | Type | Teacher Answer | Passage Evidence | Status |
|----|------|---------------|------------------|--------|
| 1  | MCQ  | B             | Para A: "boils water...sits quietly" | ✅ Correct |
| ... | ... | ...          | ...              | ❌ See Issue #1 |

### 2. Issues Found
**Issue #1: [Title]**
- **Severity:** 🔴 Critical / 🟡 Warning / 🟢 Suggestion
- **Question:** Q# (type)
- **Problem:** [Clear description]
- **Current text:** [What the question/answer says now]
- **Proposed fix:** [Specific revised wording]

### 3. Question Design Quality
| Q# | Paraphrasing | Distractors | Tests Understanding | Issue |
|----|:-----------:|:-----------:|:-------------------:|-------|
| 1  | ✅ Good | ✅ Plausible | ✅ Yes | — |
| 3  | ❌ Options copy passage | 🟡 Some obvious | ❌ Keyword scan | See Issue #2 |

### 4. Type Mix & Coverage
- Question types used: [list]
- Missing recommended types: [list]
- Coverage: [which paragraphs have questions]

### 5. Overall Assessment
- **Answer accuracy:** X/Y confirmed
- **Question quality:** [评级]
- **Priority fixes:** [list of critical issues]
```

## Grading Framework

### Answer Accuracy
- **A**: All answers verified against passage
- **B**: 1-2 minor issues (spelling, formatting)
- **C**: 1-2 answers incorrect or unverifiable
- **D**: 3+ incorrect answers — **UNACCEPTABLE, must fix**

### Question Quality
- **A**: Well-paraphrased, plausible distractors, tests understanding
- **B**: Mostly good, 1-2 questions need minor revision
- **C**: Several issues — distractors too weak, too much copy-paste
- **D**: Fundamental problems — questions don't test reading comprehension

## Common Issue Patterns to Catch

### Pattern 1: Copy-Paste Options
```
❌ Passage: "The survey found 22% of adults wake naturally."
❌ MCQ: "What did the survey find? A) Most wake naturally B) 22% wake naturally C)..."
Fix: Paraphrase → "What did the survey reveal? A) The majority are natural early risers B) About one in five wake without an alarm..."
```

### Pattern 2: Trivial Number Questions
```
❌ "How many participants were in the study?" (Answer: 200 — just scannable)
Fix: Rephrase → test understanding of the study's FINDINGS, not its sample size
```

### Pattern 3: Obvious Distractors
```
❌ Options: A) Walking improves creativity B) Walking makes you fly C) Walking is dangerous
Fix: B and C should be plausible things actually mentioned in the passage but wrong for THIS question
```

### Pattern 4: NOT GIVEN Confusion
```
❌ Passage mentions "reading on paper improves comprehension" but doesn't compare speed
❌ Question: "Reading on paper is faster than reading on screens" → Answer: TRUE
Fix: This is NOT GIVEN — the passage discusses comprehension, not speed
```

### Pattern 5: Fill-in Word Count Violation
```
❌ Instruction: "NO MORE THAN TWO WORDS"
❌ Blank answer: "a quiet moment" (one word + space + one word) — actually 3 words?
Fix: Check word counting rules (hyphenated = 1 word, "a" counts)
```

## Interaction Mode

When invoked, the reviewer should:
1. First confirm what to review: "I'll review {Unit} {Passage}. Give me the passage text and question list."
2. Produce the full structured report
3. Ask: "Shall I apply the proposed fixes, or would you like to review first?"
4. Only make changes when JT approves

This keeps the human in the loop while ensuring thorough quality control.

## Reference

- IELTS official question types: Cambridge IELTS series
- Paraphrasing principle: test understanding, not keyword matching
- T/F/NG distinction: based on information in passage
- Y/N/NG distinction: based on writer's views/claims
- Fill-in: answers must appear verbatim in passage text
- MCQ: 4 options, all must be grammatically consistent with the stem

---

## Appendix B: Key Review Criteria (2026-04-30)

### B1. MCQ Quality Checks

| Check | Flag if |
|-------|--------|
| Number recall | Testing memory of specific numbers ("How many hours?") → 🔴 Critical |
| Copy-paste options | Option uses same wording as passage → 🟡 Warning |
| Implausible distractors | Wrong options use concepts NOT in the passage → 🟡 Warning |
| Option symmetry | Options of different length or grammatical form → 🟢 Suggestion |

### B2. Fill-in Completion Checks

**⚠️ STRUCTURAL CHECK — Most important: verify the FORMAT matches the LABEL**

| Check | Flag if |
|-------|--------|
| Label mismatch | Questions labeled "Complete the summary" but written as separate sentences (NOT a flowing paragraph) → 🔴 Critical. Real IELTS "summary" always means ONE coherent paragraph. |
| Label mismatch | Questions labeled "Complete the notes" but missing section headers → 🔴 Critical. Real IELTS "notes" always have section headers. |
| Label mismatch | Questions labeled "Complete the sentences" but connected as a paragraph → 🟡 Warning. Real IELTS "sentences" are independent. |
| Word limit violation | Instruction says "ONE WORD ONLY" but answer is two words → 🔴 Critical |
| Instruction mismatch | Uses "NO MORE THAN TWO WORDS" when C20 uses "ONE WORD ONLY" for most reading → 🟡 Warning |
| Answer not in passage | Fill-in answer not found verbatim in passage text → 🔴 Critical |
| Definition-to-term mapping | Blank asks for a concept name that the passage explicitly defines (e.g., "The gradual loss of focus is ___" where passage says "term X describes...") → 🔴 Critical. This is the most common mistake. |
| Near-verbatim summary | Summary copies passage structure with only the blank word removed → 🔴 Critical |
| Comprehension vs scanning | Blank can be filled by keyword searching without understanding → 🟡 Warning |
| Blank is abstract when concrete fits | Blank tests an adjective/adverb when a concrete noun could be tested instead → 🟢 Suggestion (C20 tests overwhelmingly concrete nouns) |
| Notes section headers missing | Notes items lack organizing section headers → 🔴 Critical |
| Non-parallel notes items | Items under same header have different grammatical styles → 🟢 Suggestion |

### B3. Matching Information Checks

| Check | Flag if |
|-------|--------|
| Sequential order | Question order matches paragraph alphabetical order (A→1, B→2, C→3...) → 🔴 Critical |
| No NB when needed | Paragraph used multiple times but NB + "You may use any letter more than once" absent → 🔴 Critical |
| Missing paragraph count | Instruction doesn't mention number of paragraphs (e.g., "has seven paragraphs, A-G") → 🟡 Warning |
| Questions as short labels | Questions are single words instead of full descriptive phrases → 🟡 Warning |

### B4. Question Count & Type Checks

| Check | Flag if |
|-------|--------|
| Too few questions | <10 questions per passage → 🟡 Warning |
| Missing question types | <3 different types across 5 passages → 🟡 Warning |
| No speaking topic mapping | "Linked Speaking Topics" line absent → 🟡 Warning |
| Missing Y/N/NG vs T/F/NG distinction | Opinion passage uses T/F/NG instead of Y/N/NG → 🟡 Warning |

### B5. Answer Accuracy Quick-Verify

Fill-in answers: `answer.lower() in passage_text.lower()` — Must be True.

T/F/NG logic:
- TRUE: statement paraphrases information STATED in passage
- FALSE: statement says OPPOSITE of what passage states
- NOT GIVEN: claim NOT addressed (comparisons, motivations, extrapolations)

Y/N/NG logic:
- YES: statement agrees with writer's CLAIMS/VIEWS
- NO: statement contradicts writer's CLAIMS/VIEWS
- NOT GIVEN: impossible to determine writer's opinion

### B6. Technical Checks

| Check | Flag if |
|-------|--------|
| `&apos;` in DOCX XML | Not supported by DOCX format → 🔴 Critical |
| Question sequence | Doesn't follow passage order → 🟡 Warning |
| Student/teacher alignment | Passage text differs between versions → 🔴 Critical |

### B7. Listening-Specific Checks (for listening materials)

| Check | Flag if |
|-------|--------|
| Section 1 word instruction | Uses "ONE WORD ONLY" instead of "ONE WORD AND/OR A NUMBER" → 🟡 Warning |
| Section 4 word instruction | Uses "ONE WORD AND/OR A NUMBER" instead of "ONE WORD ONLY" → 🟡 Warning |
| Section 2 MCQ options | Uses 4 options (A-D) instead of 3 (A-C) → 🟢 Suggestion |
| Map labeling letter range | Uses letters that don't follow A-H pattern → 🟢 Suggestion |
| Two-answer MCQ numbering | Spans single number instead of two (e.g., "Q21" instead of "Q21 and 22") → 🟡 Warning |

---

## Panel Mode: Three-Editor Review (2026-04-30)

### Purpose

After generating questions, spawn THREE independent editor sub-agents. Each independently reviews the same passage+questions+answers. Compare their findings — if ≥2 editors flag the same issue, fix it. If only 1 editor flags something, mark it as "consider."

### How to Invoke

```
Call: skill-ielts-reviewer --panel {unit} {passage}
```

### Panel Process

1. **Generate questions** (via skill-ielts-generator)
2. **Spawn 3 reviewer sub-agents** — each gets the same input:
   - Full passage text
   - All questions (student version)
   - Answer key (teacher version)
   - Review criteria (Appendix B of this SKILL)
3. **Each editor produces** a structured report with:
   - Answer accuracy findings
   - Question quality issues (paraphrasing, distractors, type mix)
   - Technical issues (&apos; entities, word limits, etc.)
   - Specific fixes proposed for each issue
4. **Compare reports** — merge findings:
   - 🔴 3/3 agree → MUST FIX
   - 🟡 2/3 agree → SHOULD FIX
   - 🟢 1/3 flags → CONSIDER (optional)
5. **Apply fixes** — fix all 🔴 and 🟡 issues
6. **Re-review** — run panel again if major changes made
7. **Deliver** — when panel agrees quality is sufficient

### Editor Agent Task Template

```
You are an IELTS Reading question editor. Review Passage {N} of Unit {U}.

PASSAGE TEXT:
[full passage text here]

QUESTIONS (student version):
[all questions without answers]

ANSWER KEY (teacher version):
[all answers with explanations]

REVIEW CRITERIA:
1. Is each answer uniquely supported by the passage?
2. T/F/NG (information): TRUE=agrees, FALSE=contradicts, NOT GIVEN=no info
3. Y/N/NG (writer's views): YES=agrees with writer, NO=contradicts writer, NOT GIVEN=cannot determine
4. Ensure Y/N/NG is used for opinion/argument passages, T/F/NG for factual ones
5. Summary/Notes answers must appear VERBATIM in passage
6. Word limits: "ONE WORD ONLY" → answer = 1 word; "ONE WORD AND/OR A NUMBER" → answer = 1 word or number or combination; "NO MORE THAN TWO WORDS" → answer ≤ 2 words
   Note: C20 mostly uses ONE WORD ONLY or ONE WORD AND/OR A NUMBER for reading summaries, not NO MORE THAN TWO WORDS
7. MCQ options must be fully paraphrased (no copy-paste from passage)
8. Distractors must be plausible (from passage content, wrong context)
9. No number-recall MCQs allowed
10. &apos; entities must be replaced with '
11. Matching Headings must cover all paragraphs
12. Question count ≥ 10 per passage
13. Matching Information: question order must NOT match paragraph order (A→1, B→2...)
14. Matching Information: NB + "You may use any letter more than once" ONLY when paragraph is used twice (not as default)
15. Summary/Notes Completion: CRITICAL — no definition-to-term mapping blanks (asking for a term the passage defines, like "X is called __"). Real IELTS blanks test content words: body parts, materials, animals, abstract nouns, adjectives, years. NEVER defined terms.
16. Summary/Notes Completion: the surrounding text must be a genuine paraphrase, not near-verbatim copy with blank removed
17. Summary/Notes Completion: if Notes format, use section headers organizing content hierarchically (C20 pattern)
18. Listening Section 1: use "ONE WORD AND/OR A NUMBER" not "ONE WORD ONLY"
19. Listening Section 4: use "ONE WORD ONLY" not "ONE WORD AND/OR A NUMBER"
20. Listening Section 2 MCQ: use 3 options (A, B, C) not 4
21. Two-answer MCQ in Listening Section 3: must span two question numbers (e.g., "21 and 22")
22. Listening Part 1 Table format: "Complete the table below" with column headers is a valid alternative to notes

OUTPUT FORMAT:
- For each question: ✅ Correct / ❌ Issue Found
- For each issue: description + severity + proposed fix
- Overall assessment: Pass / Fix Required
```

### Consensus Merge Rules

| Vote | Action |
|------|--------|
| 3/3 ❌ | 🔴 Critical — fix immediately |
| 2/3 ❌ | 🟡 High — fix before delivery |
| 1/3 ⚠️ | 🟢 Low — consider if time permits |
| 3/3 ✅ | Pass — no action needed |

### Integration with Generator SKILL

This skill is the quality-assurance companion to **`skill-ielts-generator`**.

After every generation run, invoke this reviewer in Panel Mode:

1. Read the generated student and teacher DOCX files
2. Spawn 3 independent editor sub-agents (each reviews all questions)
3. Merge findings by consensus rule (3/3 = critical fix, 2/3 = should fix, 1/3 = optional)
4. Apply all 🔴 and 🟡 fixes
5. Re-verify after fixes
6. Deliver when panel agrees quality is sufficient

The generator's workflow already includes this as Step 9 (Panel Review).
