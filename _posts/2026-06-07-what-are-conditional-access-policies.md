---
layout: post
title: "What Are Conditional Access Policies and Why Do They Matter?"
date: 2026-06-07 00:00:00 +0000
---

If you've been working in Microsoft Azure or Entra ID, you've probably heard the term Conditional Access thrown around a lot. But what does it actually mean, how does it work, and why should you care? Let's break it down from the ground up — no jargon, just clarity.

## What Is Conditional Access?

Conditional Access is Microsoft's policy engine that sits between your users and your resources. Think of it as a smart security checkpoint — instead of just asking "who are you?", it asks "who are you, where are you, what device are you on, and what are you trying to access?"

Only after evaluating all of those signals does it decide whether to allow, block, or challenge the request.

In simple terms the logic works like this:

> **IF** a certain condition is met → **THEN** enforce a control

That's it. Everything in Conditional Access is built on that If/Then foundation.

## How It Fits Into Zer0 Trust

You've probably heard of Zer0 Trust — the security model that says "never trust, always verify." Conditional Access is one of the primary tools Microsoft provides to actually implement Zero Trust in practice.

Traditional security assumed that once you were inside the network, you were trusted. Zer0 Trust throws that assumption out completely. It doesn't matter if you're in the office, on VPN, or connecting from home — every access request is evaluated the same way.

Conditional Access enforces that principle by continuously checking:

- Who is the user and what is their risk level
- What device are they using and is it compliant
- Where are they connecting from
- What application or resource are they trying to access
- What time of day is it

Based on all of those signals, it makes a real time access decision.

## The Basic Building Blocks

Every Conditional Access policy has three parts:

### Assignments - Who and What

This is where you define the scope of the policy. You choose:

- **Users and groups** — who the policy applies to
- **Cloud apps or actions** — what resource or application is being accessed
- **Conditions** — extra filters like location, device platform, sign in risk, or client app

### Access Controls — Allow or Block

Once the conditions are matched, you define what happens:

- **Grant** — allow access, but require something first (MFA, compliant device, terms of use)
- **Block** — deny access completely
- **Session** — allow access but with restrictions (limited session, read only)

### Enable or Disable

Every policy has a simple on/off switch. Microsoft also provides a **Report Only** mode — which is incredibly useful for testing a policy and seeing what it would do before you enforce it. Always use Report Only first before turning a policy on.

## Why Do You Need It?

Here is the honest answer — passwords alone are not enough anymore. Credential theft, phishing, and token hijacking are all common attack techniques that bypass traditional username and password authentication.

Conditional Access adds layers on top of authentication:

- Even if an attacker steals a password, they still need to pass MFA
- Even if they pass MFA, they still need a compliant device
- Even if they have a compliant device, they still need to be connecting from a trusted location
- And so on

Each layer makes it exponentially harder for an attacker to get through.

## Who Needs Conditional Access?

Realistically — any organisation using Microsoft 365, Azure, or Entra ID should have Conditional Access policies in place. The risk of not having them is simply too high in today's threat landscape.

That said, the complexity of your policies should match your organisation's risk tolerance and user base.

## Licensing — What Do You Need?

This is something that trips a lot of people up. Conditional Access is not available on all Microsoft 365 plans.

| Feature | License Required |
|---------|-----------------|
| Basic Conditional Access | Entra ID P1 (included in Microsoft 365 Business Premium, E3) |
| Risk based policies | Entra ID P2 (included in Microsoft 365 E5+) |

If you are not sure what license you have, go to **Entra ID → Overview** and check the license tier shown there.

## What Comes Next

Now that you understand what Conditional Access is and how it works, the next posts in this series will go deeper:

- **Post 2** — The essential CA policies every tenant should have (MFA, block legacy auth, compliant devices)
- **Post 3** — Geo Lock policies — blocking logins by location
- **Post 4** — Advanced risk based policies using Entra ID Protection

Each post builds on the last, so by the end of the series you will have a solid, layered Conditional Access framework in place.

Have questions or want to share how you use Conditional Access in your environment? Drop a comment below.
