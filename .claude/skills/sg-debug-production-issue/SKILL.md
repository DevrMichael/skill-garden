---
name: sg-debug-production-issue
description: Diagnose and fix production issues by analyzing error reports, logs, and crash data to find root causes and recommend fixes. Use this skill when something breaks in production, a user reports a bug, or you need to analyze error logs. Helps you quickly identify what went wrong and how to fix it.
---

# Debug Production Issue

When something breaks in production, your goal is to quickly identify the root cause and deploy a fix without making things worse.

## Workflow

### 1. Gather context

Start by collecting all available information:

**What happened**
- User report or error alert?
- What were they trying to do when it broke?
- When did it start happening?
- Is it happening for all users or just some?
- How many users are affected?

**System state**
- Recent deployments or changes?
- Error logs or stacktraces?
- Monitoring/alerting data (latency, CPU, memory, etc.)?
- Database logs or query performance?
- Third-party service issues (API down, etc.)?

**Reproduction**
- Can you reproduce it locally?
- What are the exact steps?
- Does it happen consistently or intermittently?
- On what browsers/devices/regions?

**Scope**
- Is it a code bug, infrastructure issue, or external dependency?
- One feature or entire system?
- Frontend, backend, or both?

### 2. Analyze available data

**Error logs**
- Read the full stacktrace, not just the error message
- Note the exact line and function where it failed
- Look for patterns (same error multiple times)
- Check timestamps to correlate with other events

**Application logs**
- What was happening before the error?
- What requests were being processed?
- What state was the application in?
- Are there warnings or debug logs that help?

**System metrics**
- Was there a spike in traffic?
- Memory/CPU usage when it happened?
- Database connection pool exhausted?
- Slow queries or timeouts?

**User data**
- What user(s) triggered the issue?
- Their browser, device, region?
- Their recent actions?
- Any patterns (same endpoint, same data type)?

### 3. Form hypotheses

Based on gathered data, propose 2-3 likely causes:

**Code bugs**
- Logic error in recent changes
- Off-by-one errors, null pointer, type mismatch
- Race condition or timing issue
- Unhandled edge case

**Data issues**
- Unexpected data format
- Corrupted or missing data
- State mismatch (cache vs. database)
- Type conversion failure

**Infrastructure/environment**
- Service dependency down (database, API, cache)
- Resource exhaustion (disk, memory, connections)
- Network issue or timeout
- Configuration mismatch between environments

**External factors**
- Third-party service changed behavior
- Browser update broke something
- OS or runtime version incompatibility
- Data ingestion or migration issue

### 4. Prioritize hypotheses

Ask:
- Which is most likely given the evidence?
- Which would have broadest impact if true?
- Which is easiest to verify?
- Which takes longest to fix?

Start with high-likelihood, high-impact hypotheses.

### 5. Test hypotheses

**For code bugs**
- Look at recent commits to that area
- Trace through the logic with the failing user's data
- Check if tests cover this scenario
- Try to reproduce locally with same conditions

**For data issues**
- Query the database to see the actual data
- Check data transformation logic
- Look for type mismatches or format issues
- Review data migrations or recent updates

**For infrastructure**
- Check service status/health endpoints
- Look at resource usage
- Review recent deployments or config changes
- Check network connectivity and latency

**For external factors**
- Check service status pages
- Review if dependencies updated recently
- Test with multiple browsers/devices
- Check release notes for changes

### 6. Identify root cause

Once you've narrowed it down:

**The root cause should answer:**
- What specifically went wrong?
- Why did it go wrong?
- Why wasn't it caught before production?
- Could this have been prevented?

**Be specific**, not vague:
- ✅ "Null pointer in getUserRoles() when user has no roles assigned"
- ❌ "Something broke in the auth system"

### 7. Recommend a fix

Provide:

**Immediate mitigation** (if needed)
- Can you quickly roll back?
- Is there a workaround for users?
- Should the service be temporarily disabled?
- How long can you stay broken?

**Permanent fix**
- Code change needed? Where exactly?
- Data cleanup needed?
- Infrastructure change?
- How to prevent this in the future?

**Testing plan**
- How to verify the fix works?
- What scenarios to test?
- Should you test on staging first?
- Any regression risk?

### 8. Document and deploy

Include:
- **Root cause summary**: What went wrong
- **Fix**: Exact code/data/config change
- **Testing done**: What you verified
- **Risk assessment**: Could this break something else?
- **Rollback plan**: How to revert if needed
- **Monitoring**: What to watch after deploying

## Tips for effective debugging

- **Start with the error message**: It usually points to the problem
- **Read the full stacktrace**: The line number shown may be a symptom, not the cause
- **Check recent changes**: 90% of production bugs follow a deploy
- **Reproduce locally first**: Eliminates environment-specific issues
- **Think like the user**: What were they actually trying to do?
- **Check the obvious first**: Typos, missing semicolons, wrong variable names
- **Use binary search**: Disable half the feature, see if it still breaks
- **Read error logs fully**: Scroll up, there's usually context before the error
- **Correlate with time**: When exactly did it start? What changed?
- **Test the fix thoroughly**: Don't deploy a bandaid that masks the real issue

## Common production issues

**Null pointer / undefined reference**
- Check where nulls can come from
- Add null checks or provide defaults
- Review database/API contract

**Performance degradation**
- Check for new N+1 queries
- Look for memory leaks
- Review recent algorithmic changes
- Check if a dependency update changed behavior

**Data loss or corruption**
- Review recent migrations or data changes
- Check transaction handling
- Look for race conditions
- Verify backup/recovery procedures

**Service unavailable**
- Check downstream dependencies
- Look for resource exhaustion
- Review scaling/load balancing
- Check recent deploy or config changes

**Wrong behavior (not a crash)**
- Review recent logic changes
- Check for off-by-one errors
- Look at conditional logic
- Test edge cases

## Output style

Be direct and diagnostic. The developer reading this should be able to:
- Understand exactly what went wrong
- Know where the bug is in the code
- Fix it with confidence
- Know how to prevent it next time
