# Track 4 evaluation specification

The one-click demonstration runs **60 synthetic reconciliation cases** across Razorpay-like settlement, bank-credit, and ERP records. It evaluates the engine against deterministic ground truth with no customer or merchant data.

| Case family | Cases | Expected decision | Purpose |
|---|---:|---|---|
| Exact reference and amount | 40 | Auto-close | Establishes the high-confidence path. |
| Fee and GST net settlement | 7 | Auto-close with calculation | Demonstrates finance-aware reconciliation. |
| Refund in settlement cycle | 5 | Auto-close with linked refund evidence | Demonstrates non-trivial netting. |
| Expected T+1/T+2 timing lag | 4 | Monitor; no loss claim | Prevents normal settlement timing from becoming an exception. |
| Missing bank credit | 2 | Escalation-ready | Demonstrates an honest unresolved outcome. |
| Duplicate ledger posting | 1 | Human review | Demonstrates safe stop behavior. |
| Ambiguous bank narration | 1 | Human evidence required | Demonstrates bounded AI classification. |

The scorecard reports case throughput, source-record throughput, deterministic match rate, decision accuracy against ground truth, false-positive auto-resolutions, unresolved count, and elapsed run time. A case is never auto-closed when source evidence is insufficient.

The AI receives only the four residual synthetic exceptions. Its role is limited to choosing a pre-defined reason code, restating available evidence, and recommending a non-financial next step. It cannot send communications, post journals, move money, resolve risk holds, or override deterministic policy.

## Browser verification

The Reconciliation view now presents the Track 4 evaluated batch as the primary action. The source cards are explicitly labelled as ground-truth/evaluated synthetic inputs, and the prior illustrative batch metrics were removed from this route to prevent a judge from confusing placeholder statistics with evaluation output.

The public in-browser evaluation completed successfully: it processed 60 cases and 174 source records, auto-closed 52 cases, monitored 4 timing cases, retained 4 unresolved cases, recorded an 86.7% deterministic match rate, 100% decision accuracy against the corpus ground truth, and zero false-positive auto-resolutions. The bounded AI-review button also completed and presented the deterministic safe fallback for each residual case, each retaining mandatory human approval.

After correcting the GPT completion-token request shape and restarting the service, the evaluation was run again successfully through the live interface. The final AI-path check follows this verified deterministic run.

The repeated live run retained the expected result: 60 cases, 174 source records, 52 automatic closures, 4 monitored timing cases, 4 unresolved cases, 100% ground-truth decision accuracy, and no false-positive automatic closure.

During compatibility validation, the structured model response was initially returned through a wrapper shape rather than the expected top-level choices field. The classifier now supports both documented response shapes while continuing to validate the full JSON schema before showing any model result.

The post-fix deterministic evaluation remains repeatable in the browser. The final diagnostic focuses only on the optional model-backed classification; the deterministic classification fallback remains the safe operational path if the model is unavailable or violates the strict response contract.

The final model diagnostic identified a provider restriction: JSON-schema enum values must be strings or null, so the schema now permits a boolean field while the server-side Zod validator still strictly requires `requiresHuman: true`. This preserves the human-approval guarantee and restores a provider-compatible structured request.

During final browser validation, the model-backed classification remained in its loading state after the first wait interval; the interface continues to display the measured deterministic result and does not expose any incomplete model output.

The corrected structured-AI request was submitted from the live browser workflow after the evaluated residual queue was produced. Its result is only rendered after the response passes strict server-side schema validation.

The live model-backed classification completed successfully after the compatible schema correction. The model returned the expected four cases, the fixed reason-code taxonomy, evidence summaries, safe next steps, and a mandatory human-approval state. The server normalizes valid model confidence conventions (0–1 or 0–100) to the displayed percentage scale before rendering.

The final deterministic run again completed successfully in the browser after the confidence-normalization patch. The next interaction verifies the displayed structured-AI confidence values.
