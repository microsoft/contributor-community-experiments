# Issue Management Guide

This document outlines some of the key workflows and policies that dotnet/runtime maintainers use to triage issues and manage their backlogs. The purpose of this guide is to:

1. Provide reference documentation to area owners.
2. Improve transparency on how we handle issues with the wider community.
3. Set expectations regarding automated issue management policies.

## Issue Triage

Issue triage is the initial phase of the issue management process in which feature area owners

0. Route it correctly: has it been given a correct area? does it need to be transferred to another repo? 
1. Classify the issue: is it a feature request? bug report? user question? is the issue unclear?
2. Determine viability of the issue: is it likely that we would support the feature request in principle? does the bug report reproduce? is the reported issue by-design behavior? is the issue a duplicate?
3. Estimate required effort: does the feature design need further refinement? how much work is needed to get the implementation done?
4. Assign priority and milestones.

An issue is defined as "triaged" if it either gets closed _or_ gets assigned to a milestone. Issue triage is typically a multi-step process that is performed collaboratively by the feature area owners, issue author and supported by our bot infrastructure. While most issues are typically triaged within a day or two of being reported, in some cases it might take longer depending on a variety of circumstances.

### Triage Workflow

1. The issue labeling bot assigns the `untriaged` label and infers an area label for the new issue.
2. Area owners get notified and begin triage of the issue. 
3. Area owners complete triage with the following potential outcomes:
   * Issue is accepted and assigned to a milestone; MsftBot removes the `untriaged` label; relevant labels further classifying the issue are applied by the area owner.
   * Issue is closed as either duplicate, wontfix, breaking change, answered question, etc.
   * Issue is unclear or missing information: area owner assigns the `needs more info` label; MsftBot removes the `untriaged` label and adds a post citing this guide. Possible outcomes:
     * Author responds within 14 days: MsftBot reinstates the `untriaged` label. GOTO step 2.
     * No activity is recorded: issue closed automatically by MsftBot.

## API Proposals

Issues proposing the addition of new public APIs are special, since they need to be approved during an API review meeting. This procedure is governed by our [API Review process](https://github.com/dotnet/runtime/blob/main/docs/project/api-review-process.md). A condensed version of the workflow from an area owner's perspective is the following:

1. On triage, the area owner assigns the `api-suggestion` label; MsftBot posts a link to the [API Review Process](https://github.com/dotnet/runtime/blob/main/docs/project/api-review-process.md) reminding the author to adopt the API proposal template.
2. Depending on their confidence on the API proposal, the area owner will either:
   * apply the `api-ready-for-review` label and assign the issue to an area owner who will sponsor the issue during API review; this adds the issue to the API review backlog.
   * apply the `api-needs-work` label; the design requires refinement before it can be put to review. MsftBot will ping any issues that have remained stagnant for more than 6 months.

## Enhancement

A product improvement that does NOT require public API changes should be tagged with the `enhancement` label.

## Bug reports

On triage, a reproducible bug report should be given the `bug` label.

## Performance regressions

On triage, a performance regression report should be given the `tenet-performance` label.

## Needs further triage

Ocassionally an issue might require more extensive investigation or deeper consideration. Issues like that should be given the `needs further triage` label and assigned a relevant milestone.