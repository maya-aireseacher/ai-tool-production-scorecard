# AI Tool Production Scorecard

## Tool Information

**Tool Name**: [e.g., Cursor, Claude Code, GitHub Copilot]
**Category**: [coding assistant | RAG framework | vector database | orchestrator | other]
**Evaluation Period**: [start date] to [end date]
**Project Context**: [Brief description: what you built, team size, timeline pressure]

---

## 1. Speed: Claimed vs. Reality

### Pre-Use Expectation
**Expected Productivity Gain**: [e.g., 24% faster based on vendor claims]
**Source of Expectation**: [Marketing material | Peer recommendation | Benchmark study]

### Measured Reality
**Task Completion Time With Tool**: [hours or days]
**Task Completion Time Without Tool (baseline or estimate)**: [hours or days]
**Actual Productivity Change**: [+/- X% — calculate: (baseline - actual)/baseline × 100]

### Post-Use Perception
**Your Belief After Using It**: [Did you feel faster? By how much?]
**Gap Between Feeling and Measurement**: [If measurement showed slowdown but you felt faster, note it here]

**Notes**: [What tasks felt faster? Which ones took longer? Where did the time go?]

---

## 2. Reliability: What Breaks and How Often

### Autonomy
**Maximum Steps Before Human Intervention**: [For agents: how many actions before you had to step in?]
**Frequency of Manual Intervention**: [Every task | Every few tasks | Rarely]
**Acceptance Rate**: [For code suggestions: % of suggestions you accepted without modification]

### Quality Under Load
**Issues Introduced**: [Count of bugs, code smells, vulnerabilities you caught in review]
**Issues That Shipped**: [Count that made it past review into production]
**Severity**: [Mostly harmless | Required rework | Caused production incident]

### Predictability
**Did It Fail the Same Way Twice?**: [Yes/No — can you recognize and route around failure modes?]
**Failure Recovery**: [How long to fix when it breaks? Does it break your flow?]

**Notes**: [Describe failure modes. What triggers them? How do you know when output is wrong?]

---

## 3. Production Readiness: Integration and Ongoing Cost

### Integration Effort
**Time to First Useful Output**: [hours or days from install to actually helping]
**Configuration Complexity**: [Low | Medium | High — how much prompt engineering or tuning?]
**Dependency on Manual Work**: [e.g., 79% of prompts hand-crafted, or mostly automated]

### Monitoring and Maintenance
**Observability**: [Can you see what it is doing? Do you trust it enough to not watch?]
**Cost Tracking**: [Can you measure cost per task? Does cost matter for your use case?]
**Latency**: [Acceptable | Noticeable | Blocks your flow]

### Longevity
**Still Using It After Evaluation Period?**: [Yes/No]
**If No, Why Not?**: [Too slow | Too unreliable | Better alternative | Integration cost too high]
**If Yes, For What?**: [Specific tasks or all work?]

**Notes**: [What would have made integration smoother? What ongoing pain remains?]

---

## 4. Final Assessment

### What Worked
[Concrete tasks or workflows where this tool delivered value. Be specific.]

### What Did Not Work
[Tasks where it slowed you down, introduced risk, or required more effort than doing it yourself.]

### Would You Recommend It?
**To Whom**: [Beginners | Experienced developers | Teams with X constraint]
**For What**: [Specific use cases]
**With What Caveats**: [Required conditions for success]

### Claims vs. Reality Summary
[One paragraph: biggest gap between what was promised and what you experienced. Include any numbers from your measurements above.]

---

## 5. Evidence Log

[Optional: Link to commit history, issue tracker, or time logs that support your measurements. If you tracked specific incidents in the CSV, reference it here.]
