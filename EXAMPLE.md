# AI Tool Production Scorecard: Cursor (Example)

## Tool Information

**Tool Name**: Cursor
**Category**: Coding assistant
**Evaluation Period**: 2026-09-01 to 2026-09-30
**Project Context**: Solo developer building a RAG pipeline for internal documentation search. Three-week sprint deadline, Python backend with FastAPI, 8,000 lines of code added or modified.

---

## 1. Speed: Claimed vs. Reality

### Pre-Use Expectation
**Expected Productivity Gain**: 50% faster based on peer recommendations and marketing materials
**Source of Expectation**: Developer forum posts and Cursor's website highlighting rapid prototyping

### Measured Reality
**Task Completion Time With Tool**: 18 days
**Task Completion Time Without Tool (baseline from similar past project)**: 16 days
**Actual Productivity Change**: -12.5% (took longer than baseline)

### Post-Use Perception
**Your Belief After Using It**: Felt like I was moving 30% faster during active coding
**Gap Between Feeling and Measurement**: Large—subjective feeling of speed did not match measured completion time. Time went into reviewing and fixing generated code, which felt less visible than writing it.

**Notes**: Autocomplete for boilerplate was genuinely fast. Multi-file refactoring suggestions saved time. But I spent hours debugging subtle logic errors in generated async code and fixing imports that looked right but broke at runtime. The acceptance rate was high (around 40% of suggestions used as-is), but the 60% that needed editing consumed more time than I expected.

---

## 2. Reliability: What Breaks and How Often

### Autonomy
**Maximum Steps Before Human Intervention**: N/A (coding assistant, not agent)
**Frequency of Manual Intervention**: Every suggestion required review; roughly 60% needed modification
**Acceptance Rate**: ~40% accepted without changes

### Quality Under Load
**Issues Introduced**: 23 issues caught in code review (mostly code smells: duplicate logic, overly complex conditionals, missing error handling)
**Issues That Shipped**: 3 minor issues made it to staging (incorrect default parameter, one unhandled edge case, one unnecessary API call)
**Severity**: Required rework in staging; no production incidents

### Predictability
**Did It Fail the Same Way Twice?**: Yes—consistently over-engineered error handling and generated overly defensive null checks in Python where types were already explicit. Once I recognized the pattern, I could edit faster.
**Failure Recovery**: Fast when I caught it during review. Costly when I trusted a plausible-looking suggestion and found the bug two days later during integration testing.

**Notes**: The tool excels at code that looks right. The failure mode is plausible incorrectness—logic that compiles and passes shallow tests but breaks under load or edge cases. I learned to distrust async code suggestions and anything involving database transactions.

---

## 3. Production Readiness: Integration and Ongoing Cost

### Integration Effort
**Time to First Useful Output**: 2 hours (install, configure API key, first useful autocomplete)
**Configuration Complexity**: Low—minimal setup, but I spent 4 hours over the first week tuning how much context to include in prompts
**Dependency on Manual Work**: High—every suggestion required human judgment. I wrote all prompts for multi-line generation manually.

### Monitoring and Maintenance
**Observability**: None—no way to track what it is doing or measure quality over time without external tooling
**Cost Tracking**: Subscription cost is flat; no per-token usage to monitor
**Latency**: Mostly acceptable. Occasional 3-5 second delays on large file edits, which broke flow.

### Longevity
**Still Using It After Evaluation Period?**: Yes
**If Yes, For What?**: Boilerplate generation, test scaffolding, and quick exploratory refactoring. I do not trust it for core business logic or async code without heavy review.

**Notes**: Integration was smooth, but I wish I could see confidence scores or flag patterns that historically caused issues. The lack of feedback loop means I am repeating the same review effort on the same class of errors.

---

## 4. Final Assessment

### What Worked
- Autocomplete for imports, type hints, and common patterns (e.g., FastAPI route definitions) saved real time
- Multi-file refactoring suggestions (renaming, extracting functions) were accurate 70% of the time and faster than manual search-and-replace
- Test generation for simple functions was solid—often needed only minor tweaks

### What Did Not Work
- Generated async code frequently had race conditions or incorrect error propagation
- Suggestions for database query logic were over-complicated and sometimes wrong (e.g., missing transaction rollback)
- No way to learn from my corrections—it repeated the same mistakes across the project

### Would You Recommend It?
**To Whom**: Experienced developers who can review code quickly and recognize subtle logic errors
**For What**: Boilerplate, scaffolding, refactoring—anything where the structure is more important than the edge cases
**With What Caveats**: Do not trust it for async, concurrency, database transactions, or business logic without thorough review. Expect to spend 30-40% of your "saved" time on review and fixes.

### Claims vs. Reality Summary
I expected 50% faster delivery based on peer claims. I measured a 12.5% slowdown in calendar time, though active coding felt faster. The gap came from review overhead and debugging plausible-but-wrong suggestions. The tool shines on well-trodden patterns and fails quietly on complex logic—exactly the inverse of what I needed under a tight deadline. Production deadlines exposed the difference between generating code fast and generating correct code.

---

## 5. Evidence Log

Commit history: 47 commits during evaluation period, 23 issue tickets logged in project tracker tagged "cursor-generated" for code introduced by the tool. Staging incident reports: 3 (all resolved before production).
