# Changelog

## 1.3.0

- Add typed extraction through Responses. Preserve initial and historical text-format/reasoning/tool updates, compact parallel-call metadata and cache-comparison diagnostics across unary, streaming and batch results. Redact provider tool credentials only in telemetry copies; image/mask/markup downloads use unauthenticated configured transport. Reviewed npm delta: @ai-sdk/openai 4.0.111 to 4.0.117. Validation: `node Scripts/test-packages.mjs` passed all 52 owning suites and 1731 facade tests; tooling 27/27, generation/isolation checks, standalone exports and 106 minimum/latest consumers, documentation check and 101-page build passed. Publication requires green exact-source Swift 6.3.3 CI. Paid/live verification and full-package parity are not claimed.
  Compatibility: Additive native APIs or capabilities under the project minor-release convention. npm baselines and Swift SemVer are independent; this reviewed delta does not establish full-package or live-service parity. Required direct minimums: swift-ai-core 1.3.0 to 1.4.0, swift-ai-openai-compatible 1.2.0 to 1.3.0.
