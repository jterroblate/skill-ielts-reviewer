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

### B2. Summary Completion Checks

| Check | Flag if |
|-------|--------|
| Isolated sentences | Blanks are independent sentences, not one coherent paragraph → 🔴 Critical |
| Word limit violation | "TWO WORDS" but answer is three words → 🔴 Critical |
| Answer not in passage | Fill-in answer not found verbatim in passage text → 🔴 Critical |

### B3. Question Count & Type Checks

| Check | Flag if |
|-------|--------|
| Too few questions | <10 questions per passage → 🟡 Warning |
| Missing question types | <3 different types across 5 passages → 🟡 Warning |
| No speaking topic mapping | "Linked Speaking Topics" line absent → 🟡 Warning |

### B4. Answer Accuracy Quick-Verify

Fill-in answers: `answer.lower() in passage_text.lower()` — Must be True.

T/F/NG logic:
- TRUE: statement paraphrases information STATED in passage
- FALSE: statement says OPPOSITE of what passage states
- NOT GIVEN: claim NOT addressed (comparisons, motivations, extrapolations)

### B5. Technical Checks

| Check | Flag if |
|-------|--------|
| `&apos;` in DOCX XML | Not supported by DOCX format → 🔴 Critical |
| Question sequence | Doesn't follow passage order → 🟡 Warning |
| Student/teacher alignment | Passage text differs between versions → 🔴 Critical |

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
2. T/F/NG: TRUE=agrees, FALSE=contradicts, NOT GIVEN=no info
3. Summary answers must appear VERBATIM in passage
4. Word limits: "NO MORE THAN TWO WORDS" → answer ≤ 2 words
5. MCQ options must be fully paraphrased (no copy-paste from passage)
6. Distractors must be plausible (from passage content, wrong context)
7. No number-recall MCQs allowed
8. &apos; entities must be replaced with '
9. Matching Headings must cover all paragraphs
10. Question count ≥ 10 per passage

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
