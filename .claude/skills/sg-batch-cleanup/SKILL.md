---
name: sg-batch-cleanup
description: Scan codebase for dead code, test coverage gaps, technical debt, unused dependencies, and improvement opportunities. Use this skill when you want to identify what can be removed or improved, plan refactoring work, or get a health report on a codebase. Helps you prioritize cleanup and modernization efforts.
---

# Batch Analysis & Cleanup

When managing a codebase alone, identifying and addressing technical debt systematically keeps the project maintainable. Your goal is to find high-impact improvements and prioritize them by effort vs. benefit.

## Workflow

### 1. Define what to audit

Clarify the scope:
- **Dead code**: Unused functions, files, components, branches
- **Test coverage**: Gaps in testing, untested code paths
- **Dependencies**: Unused packages, outdated packages, duplicates
- **Performance**: Slow operations, N+1 queries, unnecessary re-renders
- **Security**: Deprecated functions, insecure patterns, hardcoded secrets
- **Code quality**: Long functions, deeply nested code, high complexity
- **Documentation**: Missing docs, outdated comments, missing types
- **Standards**: Non-compliant code, style violations, anti-patterns

### 2. Scan systematically

**For dead code:**
- Search for exported symbols that are never imported
- Check test files for skipped/commented-out tests
- Look for unreachable code paths (after return, in unreachable branches)
- Review unused arguments and variables
- Check for files in git that are never required/imported

**For test coverage gaps:**
- Generate coverage report (vitest/jest/etc.)
- Identify untested files or low-coverage areas
- Look at critical paths: are they tested?
- Check for happy-path-only testing (missing error cases)
- Review integration vs. unit test balance

**For unused dependencies:**
- Use tools like depcheck or `npm ls --depth=0`
- Cross-reference package.json with actual imports
- Check for transitive dependencies not used directly
- Look for duplicate functionality in multiple packages

**For performance issues:**
- Profile the application (CPU, memory, rendering)
- Look for repeated queries or computations
- Check for large bundle sizes or unoptimized assets
- Review render performance for frequently-used components
- Look for missing memoization or caching

**For security issues:**
- Scan for hardcoded credentials, API keys, tokens
- Check for deprecated security functions
- Look for insecure patterns (eval, innerHTML, etc.)
- Review authentication and authorization logic
- Check for unvalidated user input

**For code quality:**
- Identify functions over 200 lines (too long)
- Look for deeply nested conditionals (>3 levels)
- Check for cyclomatic complexity (too many branches)
- Review parameter counts (>4 is too many)
- Look for duplicated logic

### 3. Categorize findings

Group by:

**High-impact, low-effort** 🟢
- Quick wins that improve code health a lot
- Remove unused imports, dead code files
- Update obvious type issues
- Fix simple lint violations

**High-impact, medium-effort** 🟡
- Worth doing but need planning
- Refactor duplicated logic
- Add test coverage for critical paths
- Update deprecated dependencies

**Medium-impact, low-effort** 🟢
- Still worth doing for overall health
- Fix inconsistent naming
- Add missing documentation
- Remove unused variables

**Low-impact, high-effort** 🔴
- Defer for now, not worth the time
- Perfect is the enemy of good
- Focus on high-impact items first

**Unknown-impact** ❓
- Things that might be important but need investigation
- Complex logic without tests
- Mysterious code comments
- Dead code that might be kept for a reason

### 4. Prioritize the work

Create a cleanup roadmap:

1. **Phase 1: Quick wins** (low-effort, high-impact)
   - Remove dead code, unused imports
   - Fix type issues, obvious lint violations
   - Update simple deprecations

2. **Phase 2: Core improvements** (medium-effort, high-impact)
   - Add test coverage for critical paths
   - Refactor complex duplicated logic
   - Fix security issues

3. **Phase 3: Technical debt** (medium-effort, medium-impact)
   - Upgrade dependencies to latest
   - Improve code organization
   - Add missing documentation

4. **Phase 4: Nice-to-haves** (for later)
   - Perfect names and structure
   - Minor optimizations
   - Cosmetic refactors

### 5. Generate report

Document findings:

**Executive summary**
- Health score (0-100)
- Key findings by category
- Estimated effort to address
- Biggest risks or improvements

**Dead code inventory**
- Files/functions that can be removed
- Estimated effort per item
- Risk of removal (is it really unused?)

**Test coverage gaps**
- Coverage percentage (current vs. target)
- Untested critical paths
- Effort to reach targets

**Dependency analysis**
- Unused packages (safe to remove)
- Outdated packages (consider upgrading)
- Major version upgrades needed
- Security vulnerabilities

**Performance opportunities**
- Bottlenecks identified
- Estimated improvement if fixed
- Effort required

**Code quality issues**
- Files with highest complexity
- Functions that need refactoring
- Patterns to avoid going forward

**Security findings**
- Critical issues needing immediate fix
- Deprecations to address
- Hardcoded secrets or credentials

### 6. Present with context

For each item, include:

- **What**: Specific finding
- **Where**: File and line number
- **Why it matters**: Impact of not fixing it
- **Effort**: Hours/days to fix
- **Risk**: Could fixing it break something?
- **Benefit**: What improves if we fix it?

### 7. Create action plan

Suggest:
- Which items to tackle first (quick wins)
- Which can be bundled together
- Any blockers or dependencies
- Timing (can these be done incrementally?)

## Tips for effective audits

- **Be thorough but practical**: Perfect is the enemy of done
- **Context matters**: Dead code might be kept for a reason — ask before deleting
- **Document decisions**: If you keep something "for later," write why
- **Focus on high-impact**: Remove dead code, fix security, improve coverage
- **Don't optimize prematurely**: Performance matters, but clarity matters more
- **Set standards**: "Going forward, we should..." helps prevent future issues
- **Test your cleanup**: Don't remove something without tests passing
- **Communicate**: If you remove code, explain why in commit message

## Common findings

**Dead code**
- Commented-out code (delete it, it's in git history)
- Functions never called (remove unless exported)
- Old feature flags (clean up after feature launch)
- Obsolete comments (update or remove)

**Test gaps**
- Happy path tested, errors not tested
- UI components without interaction tests
- Utilities with no tests
- Critical business logic without tests

**Dependencies**
- Packages installed but not used
- Multiple packages doing same thing
- Outdated versions available
- Security issues with known patches

**Code quality**
- Long functions doing many things (split them)
- Nested conditionals (extract to functions)
- Copy-pasted logic (DRY principle)
- Magic numbers (use named constants)

## Output style

Be constructive and actionable. A developer should be able to:
- Understand why each item matters
- Know which to tackle first
- Have confidence removing/fixing items
- Prevent similar issues going forward
