# Upload Verification Notes

The Data Sources page loads without an account session and presents the live uploader. The UI exposes native multi-file selection and drag-and-drop, supported-file guidance, size limits, a backend-storage notice, and the action to store the selected batch.

The backend route that lists stored batches is intentionally public only when it returns an empty collection for unauthenticated visitors. The mutation that stores file bytes remains account-protected and returns `401 Please login (10001)` without a valid session. This preserves user-scoped access to managed storage. A request to use the existing authenticated browser session was declined, so no user credentials or shared browser session were used.

Automated verification confirms the upload policy rejects executable extensions, zero-byte files, oversized individual files, and batches above the defined limits. An end-to-end stored-file test still requires a successful user login because no credentials were available to the agent.

The protected `uploads.createBatch` endpoint was invoked without an account session and returned the expected `401 Please login (10001)` response. A mocked backend test confirms a valid CSV creates a batch, stores the file through managed storage, and persists its metadata with the expected user and batch identifiers.
