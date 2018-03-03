---
layout: default
title: ViewModel Composition Manifesto
---

## Vision

Designing a UI when the back-end system consists of dozens (or more) of microservices is a challenge. We have separation and autonomy on the back end, but on the front-end this all needs to come back together. ViewModel Composition stops it from turning into a mess of spaghetti code, and prevents simple actions from causing an inefficient torrent of web requests.

### Description

When building systems based on SOA principles service boundaries are a key aspect, if not THE key aspect. If customers get service boundaries wrong the end result has the risk to be, in the best case, a distributed monolith, and in the worst one, a complete failure.

Service boundaries identification is a challenge on its own, it requires a lot of business domain knowledge and a lot of confidence with high level design techniques. Other than that there are technical challenges that might drive customers in the wrong directions due to the lack of technical solutions to problems they foresee while defining service boundaries.

The transition from the user mental model, what the domain expert describes, to the service boundaries architectural model in the SOA space raises concerns such as:

> If domain entities, as described by the domain experts, are split among several different services
>
> * how can I then display to users what they need to view?
> * when systems need to make decisions how can they "query" data stored in many different services required to make that decision?

These type of questions lead customers to design systems using rich events, and not thin ones, in order to share data between services and at the same to share data with cache-like things, such as Elastic Search, to satisfy UI query/visualization needs.

This is the beginning of a road to hell that can only lead to a distributed monolith, where data ownership is a lost concept and every change impacts the whole system. In such a scenario it's very easy to blame SOA and the tool set.
