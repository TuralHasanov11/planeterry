# Architecture Decision Record 1

## Title

Interface that represents Video Provider

## Status

Pending

## Context

Coupling to a dedicated Video Provider platform. 

## Decision

One architectural decision: use a provider abstraction for video generation. Don't tightly couple your application to Kling or Everygen. Your `VideoProvider` interface should let you replace a provider without rewriting the entire production pipeline. 

## Consequences

...
