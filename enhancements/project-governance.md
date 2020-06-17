---
title: project-governance
authors:
  - "@joelanford"
reviewers:
  - "@estroz"
  - "@jberkhahn"
approvers:
  - "@danielmesser"
  - "@shawnhurley"
creation-date: 2020-06-16
last-updated: 2020-06-16
status: implementable
see-also: []
replaces: []
superseded-by: []
---

# Project Governance

## Release Signoff Checklist

- [ ] Enhancement is `implementable`
- [ ] Design details are appropriately documented from clear requirements
- [ ] Test plan is defined
- [ ] Graduation criteria for dev preview, tech preview, GA

## Open Questions

1. Once a project has graduated, do we move it into the main `operator-sdk`
   repo, or do we leave it where it is?
2. Should we tweak the phases or the phase transition criteria specified below?
   Relatedly, how do we amend these in future?
3. How does the project governance overlap with the overall Operator
   Framework governance?
4. Is there an existing decision making process defined at the org level?
   (e.g. see [Helm's decision making process][helm-decisions])
5. Is there an overarching governance document this should be merged into?

[helm-decisions]: https://github.com/helm/community/blob/master/governance/governance.md#decision-making-at-the-helm-org-level

## Summary

In order to encourage more community involvement, participation, maintenance,
and contributions, the Operator Framework needs to establish a set of rules for
incorporating new projects under the Operator Framework umbrella.

Along these lines, this proposal seeks to establish governance for introducing
new projects into the Operator Framework. At a high level, we will define a set
of phases that contributions will transition between and what the transition
criteria are.

## Motivation

To encourage more community involvement, participation, maintenance, and
contributions, and to ensure that projects meet the Operator Framework
standards for quality, maintenance, and conduct.

### Goals

* Define how new projects are introduced into the Operator Framework
* Define project phases
* Define how these projects transition between various phases
* Define rules for making amendments to project governance
  
We should be able to apply these rules to the existing
[Composable proposal][composable-proposal] and make a determination for its
next steps.

[composable-proposal]: https://github.com/operator-framework/operator-sdk/pull/2340

### Non-Goals

* We probably can't think of every eventuality, so this initial proposal does
  not seek to answer all future questions about project governance. The
  amendment process can be followed in the future if rule changes are
  necessary.

## Proposed Rules for Project Governance

> **ALL Operator Framework projects, regardless of their phase, must adhere to
  the overarching Operator Framework governance process, which includes use of
  an approved open source license and the organization's code of conduct.**
>
> **Any project or project maintainer that violates these policies can be
  removed. Project maintainers who act in good faith will be given a chance to
  rectify the situation before removal.**

### Phases

1. Incubating
1. Graduated
1. Archived

The first step for a new project is to draft a proposal to this repository
(`github.com/operator-framework/enhancements`). Operator Framework maintainers
will review the proposal, provide feedback, and make a decision to about
admitting the proposed project into the target phase listed in the proposal.
This decision (and any reasoning for it) will be captured in the proposal's
pull request.

Note that it is possible to submit a project to be immediately admitted into
the graduated phase.

#### Incubating

To be approved for incubation, a proposal MUST include (at a minimum):
- A project name
- At least one project maintainer
- A clear description of:
    - WHAT the project is
    - WHY it is important for the project to be in the Operator Framework
    - HOW the project integrates with existing Operator Framework projects
    
If an implementation of the project already exists, it is recommended for the
proposal to additionally include:
- A link to the existing implementation
- Any statistics the proposer has about usage and uptake.

A proposal for an incubating project will be approved with a simple majority
vote of Operator Framework maintainers.

If a proposal is approved, it is moved to the "Incubating" phase. An Operator
Framework maintainer will:
1. Create a new project in the operator-framework GitHub organization
2. Give write access to the list of project maintainers listed in the proposal
3. Give admin access to all Operator Framework organization maintainers

At this point, any existing project implementation can be merged and new
implementations can begin.

#### Graduated

To be approved for a graduated project, a proposal MUST include (at a minimum):
- A project name
- At least three maintainers (one of whom must be an Operator Framework
  maintainer who also votes YES on the proposal).
- A clear description of:
    - WHAT the project is
    - WHY it is important for the project to be in the Operator Framework
    - HOW the project integrates with existing Operator Framework projects
- An existing implementation of the project with:
    - A link to the existing implementation
    - Statistics about the project's usage and uptake

A proposal for a graduated project will be approved with a super-majority
vote of Operator Framework maintainers.

To graduate from an incubating project to a graduated project, the project
maintainers should submit a pull request to update their existing project
proposal to include the additional information and new proposed phase. 

#### Archived

Projects will be archived due to inactivity or failure to meet Operator
Framework community standards and policies.

Incubating projects must maintain at least 1 active project maintainer to avoid
being archived. Any incubating projects that have 3 months of inactivity (no 
commits, no responses to issues, etc.) will be considered inactive and are
subject to archiving with a simple majority vote of Operator Framework
maintainers.

Graduated projects are considered official projects of the Operator Framework
and therefore WILL be maintained by Operator Framework maintainers regardless
of the activity (or lack thereof) of project maintainers. Graduated projects
can only be archived with a super majority vote of Operator Framework
maintainers.

### Amendments

To amend these rules, a super majority vote of the Operator Framework
maintainers is required.

### Project Pull Request Approvals

Pull request approvals use lazy consensus. Organization and project maintainers
participate in PR review and approval. As soon as pull requests have `lgtm` and
`approve` labels, no holds, and all required tests pass, they can be merged.

Silence from maintainers is considered approval (provided the above criteria
are met).

If lazy consensus fails, maintainers will rule using a simple majority vote.

### Risks and Mitigations

Any governance model must be open and strictly followed. Given that Operator
Framework has largely been driven by Red Hat up to this point, maintainers
must be careful to adhere to the bylaws for ALL activities in Operator
Framework repositories.

## Implementation History

Major milestones in the life cycle of a proposal should be tracked in `Implementation
History`.

## Drawbacks

The idea is to find the best form of an argument why this enhancement should _not_ be implemented.

## Alternatives

Similar to the `Drawbacks` section the `Alternatives` section is used to
highlight and record other possible approaches to delivering the value proposed
by an enhancement.

## Infrastructure Needed

A vendor-neutral merge bot should be configured on all project repositories
that follows the rules defined by the project pull request approval process.

