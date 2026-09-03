---
name: sg-audit-dependencies
description: Analyze dependencies for security vulnerabilities, outdated packages, breaking changes, and upgrade safety. Use this skill when reviewing dependency update PRs, assessing the risk of upgrading, checking for known vulnerabilities, or planning a dependency modernization. Helps you make confident upgrade decisions.
---

# Audit Dependencies

When managing dependencies for a project, your goal is to ensure updates are safe, necessary, and don't introduce breaking changes or security risks.

## Workflow

### 1. Scope the audit

Clarify what you're auditing:
- **Single update**: Review a specific package update (Renovate PR, etc.)
- **Security scan**: Check for known vulnerabilities in current dependencies
- **Upgrade plan**: Assess feasibility of upgrading major versions (React 18→19, etc.)
- **Dependency health**: Overall health of the dependency tree
- **Breaking change risk**: What breaks if we upgrade X?

### 2. Gather information

For the dependency/dependencies in question:

**Current state**
- What version is currently installed?
- When was it last updated?
- How many packages depend on it?

**Target state**
- What version are we considering?
- What changed in the new version? (changelog, release notes)
- How long ago was it released?
- Is it stable or pre-release?

**Security & stability**
- Known CVEs or security issues?
- Breaking changes between versions?
- Deprecations or API changes?
- Community adoption and activity level
- Any known issues or bug reports?

**Integration concerns**
- Do other dependencies also need updates to work with this?
- Are there peer dependency requirements?
- Does it affect the build process?
- Will tests or types need updates?

### 3. Assess the risk

Evaluate:

**Green flags** ✅
- Stable, well-maintained project
- No breaking changes or easy migration path
- Compatible with other dependencies
- Security fixes only
- Patch/minor version update
- Large adoption, no reported issues

**Yellow flags** ⚠️
- Minor breaking changes with clear upgrade guide
- Requires updates to other dependencies
- Pre-release version
- Small community or slower updates
- Deprecations but with migration path
- Major version bump

**Red flags** 🚨
- Known security vulnerabilities
- Breaking changes with no clear migration
- Unmaintained or slow updates
- Peer dependency conflicts
- Requires significant code changes
- Beta/alpha version for production

### 4. Check for cascading effects

Ask:
- What else depends on this package?
- Will the update break other things?
- Do peer dependencies need updates too?
- Will the bundle size change significantly?
- Are there type definition issues?

### 5. Make a recommendation

Provide clear verdict:

**Safe to merge** 🟢
- Why: List specific reasons
- Action: Merge and deploy
- Follow-up: Any monitoring or testing needed?

**Safe with conditions** 🟡
- What needs to be done first?
- Testing required before merge?
- Monitoring required after deploy?
- Timing constraints (deploy off-hours, etc.)?

**Not recommended yet** 🔴
- Why: Specific risks
- What to wait for: Stability, other updates, etc.
- Alternative: Use current version or different package?

### 6. Document findings

Include:
- **Audit summary**: What was reviewed and why
- **Key findings**: Security issues, breaking changes, compatibility
- **Risk assessment**: Overall risk level with reasoning
- **Recommendation**: Merge, hold, or alternative
- **If merging**: Testing checklist, deployment notes
- **If holding**: What to wait for before reconsidering

## Tips for effective audits

- **Check the changelog**: Release notes show exactly what changed
- **Review the PR**: If it's a GitHub package, check recent PRs for activity
- **Test locally first**: Run tests with the update before recommending merge
- **Know your stack**: Breaking changes in one lib might require changes elsewhere
- **Check compatibility**: Use npm-check-updates or similar to see cascading requirements
- **Monitor adoption**: Look at when major projects adopted a new version
- **Consider timing**: Some updates are better deployed during business hours vs. nights
- **Set up monitoring**: After deploy, watch logs for issues

## Security considerations

When you see security issues:
1. **Severity matters**: Is it exploitable in your use case?
2. **Exposure matters**: Are you using the vulnerable code path?
3. **Patch available**: Can you upgrade safely?
4. **Workaround**: Is there a safe workaround if you can't upgrade?

Don't merge vulnerable deps without understanding the actual risk.

## Common scenarios

**Renovate/Dependabot PR**
- Review changelog
- Check for breaking changes
- Run tests
- Recommend merge or discussion

**Major version bump available**
- Assess migration effort
- Check if dependencies also need updates
- Review breaking changes in detail
- Plan timing and testing

**Security vulnerability reported**
- Understand the vulnerability
- Check if it affects your code
- Find safe version that patches it
- Coordinate with team on urgency

**Outdated dependency**
- Assess if update is necessary
- Check what changed since current version
- Determine if it's safe to skip this update

## Output style

Be direct and actionable. A developer should be able to:
- Understand the specific risks
- Know exactly what breaks (if anything)
- Make a confident decision to merge or hold
- Know what to watch for after deploying
