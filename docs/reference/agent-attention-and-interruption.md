# Agent Attention and Interruption

Use this guidance when an agent needs to get the user's attention outside the
normal conversation, such as through a desktop sound, spoken cue, or push
notification. It governs developer-facing interruptions. Product notifications,
customer communications, and generated audio assets have separate policies.

## Put the request in the conversation first

State the complete question, decision, or requested action in the originating
Codex conversation. An external cue is only a nudge to look there; it is not a
second channel for carrying the request or its context.

Use an attention cue sparingly:

- `decision-needed`: the agent has asked a concrete question and cannot make
  safe progress without the user's decision;
- `restart-needed`: a restart is required before the user can continue;
- `resource-blocked`: user intervention is needed to unblock a real dependency;
- `course-update`: a meaningful, nonblocking change makes it useful for the
  user to review or redirect the work.

Do not cue for routine progress, speculative questions, work the agent can
safely continue, or the same unresolved decision repeatedly. For a nonblocking
update, keep progressing on independent work.

## Use an available, opted-in channel

Use only an attention integration that is already available and enabled for
this user and environment. Check its current status immediately before making a
request; do not assume a channel is configured, online, or shared across
machines or threads. Follow that integration's invocation, privacy, expiry,
rate-limit, and recovery instructions.

Keep requests to a fixed category and the minimum identifiers required by the
integration. Never include the question or answer body, conversation transcript,
secrets, raw repository paths, or arbitrary speech. A thread title may be used
only when the integration permits it and the user has opted into that specific
channel. Never turn the question itself into notification text.

Do not install a plugin, change global settings, enable an external destination,
or make a paid text-to-speech request as an interruption unless the user has
authorized that setup. Reuse the user's configured channels and preferences.

## Interpret delivery results carefully

An accepted or queued request means only that the integration accepted it; it
does not prove the user saw, heard, or acted on it. Respect expiry and
deduplication behavior, and do not retry in a loop. If no channel is enabled or
available, continue in the conversation. If blocked, name the blocker and the
event or user action that clears it.

## Integration boundary

This policy is portable. A project-specific extension, plugin, skill, or local
service may provide an optional delivery mechanism, but its setup and exact
commands belong in that integration's own documentation. Do not assume a
particular alert extension is installed in a copied project.
