# Razorpay Buildathon research notes

## Official Track 4 requirements

Source: https://razorpay.com/buildathon/

Track 4 is **AI Finance Controller**. The required outcome is an agent that closes one finance-operations loop across a synthetic batch of **50 or more records**, reports its **match rate**, and lists the **exceptions it cannot resolve**. The stated bar is **throughput, measured accuracy, and an honest exception list**; a cherry-picked match is explicitly insufficient.

Ledger Sherlock's current multi-source reconciliation framing, deterministic matching, AI exception investigation, policy controls, audit trail, validation view, and real file-intake architecture are aligned in concept. The key proof gap is that the product currently displays illustrative dashboard metrics rather than producing those metrics from an executable synthetic 50+ record dataset and repeatable evaluation run.

## Reconciliation pain-point evidence

Sources:
- https://razorpay.com/docs/payments/settlements/dashboard/
- https://razorpay.com/blog/what-is-payment-reconciliation/
- https://www.reddit.com/r/indianstartups/comments/1sgtwir/razorpay_settlements_are_always_short_anyone_else/

Razorpay's official settlement documentation describes a settlement as a combination of payment, adjustment, tax, fee, transfer, and refund components. It also supports settlement timelines, channel-wise balances, downloadable reports, and holds. This validates that a net settlement cannot always be reconciled through a simple one-to-one gross-amount comparison.

Razorpay's reconciliation explainer identifies timing differences, data-entry errors, missing transactions, fees, and interest as common discrepancy classes. It positions automation as a way to focus human effort on exceptions, to improve error detection, and to maintain a clear audit trail.

One public Reddit discussion reported a monthly settlement shortfall that took significant time to explain, attributing it to processing fees, GST on fees, failed UPI reversals, and refunds that landed in the same cycle. This is anecdotal, not market-wide evidence, but it maps closely to the multi-source, reason-coded exception queue that Ledger Sherlock should demonstrate.

## Social and review-platform signal

Sources:
- https://x.com/Razorpay/status/2065652886437060690
- https://www.linkedin.com/posts/ca-mayur-pal-a51a7181_hi-i-am-sharing-my-very-bad-experience-with-activity-7215785735621070848-aAWL
- https://www.trustpilot.com/review/razorpay.com?page=9

An official Razorpay X post claims that its Agentic Dashboard pulls Razorpay settlements from bank statements, matches them line-by-line, and answers finance questions. This is a critical differentiation signal: a generic “Razorpay settlement + bank-statement reconciliation” demo now risks looking like a reimplementation of a product direction that Razorpay has already announced.

Public feedback on LinkedIn, Reddit, and Trustpilot repeatedly mentions settlement holds, delayed resolution, poor visibility into the cause, and the working-capital impact of unresolved payment issues. These sources are self-selected reports and should not be treated as representative prevalence estimates. Their consistent qualitative pattern supports the problem, but the submission should not claim that it replaces risk, support, or settlement-release processes.

The defensible product opportunity is therefore not a generic reconciler. It is a **transparent finance-ops controller**: a system that separates expected timing differences from actionable breaks, produces reason-coded evidence, assigns an accountable owner and SLA, prepares an escalation-ready packet, and prevents unsafe automatic accounting actions.
