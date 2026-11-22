# Changelog

## 1.5.0

- Rebuild Responses additional-tool replay from current registrations and preserve input transformation metadata across unary, stream and batch results. Reviewed npm: @ai-sdk/openai 4.0.118 to 4.0.122. Offline validation passed: node Scripts/test-packages.mjs (56 packages, 3672 owning tests and 1760 compatibility tests), generation, tooling, isolation, and version selection. The earlier OpenRouter combined fixture remains open. Existing selectors keep their signatures. See Docs/Archive/WeeklyUpstreamAudit20261122.md for retained gaps. Paid provider calls were skipped.
  Compatibility: Register history-loaded tools again on each call using omitFromRequestTools. The adapter uses the current declaration when replaying a tool reference. Requires SwiftAIOpenAICompatible 1.4.0 for the public image model conformance introduced in Core 1.6.0.
