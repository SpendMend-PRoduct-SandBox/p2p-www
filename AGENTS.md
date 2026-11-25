# AGENTS.md · p2p-www

Purchasing (P2P) web front end. Product intent lives in
[product-context](https://github.com/SpendMend-PRoduct-SandBox/product-context); this repo holds code and technical context only.

**Stack:** React 18 · Vite · Node 20 (Playwright for end-to-end tests when added)

```bash
npm install
npm run build
npm run dev
```

## Before you plan
1. Open the Delivery issue and follow the **spec link at the pinned SHA**. Read the whole spec at that SHA, not `main`.
2. Read `product-context/context/business-rules/` and `compliance.md` for cross-cutting rules (SoD, audit, PHI).
3. Read `docs/adr/` and `docs/context/` in this repo.
4. Post your implementation plan as a comment on the Delivery issue before writing code.
5. If the spec is ambiguous, ask in a comment and add the `agent-question` label. Do not guess business rules.

## Rules
- Implement only what the spec and the Delivery issue scope say. Out-of-scope items stay out.
- Every acceptance test from the spec becomes an automated test whose name contains its ID (`AT-1`, `AT-2`, ...).
- Every state change writes an audit event. Never let a user approve their own request.
- No PHI in any data, fixture or log.
- Ship behind the feature flag named in the spec.
- Open one PR per Delivery issue, using the PR template. You cannot merge: the Feature Lead adds `intent-approved`,
  and Engineering approves.
