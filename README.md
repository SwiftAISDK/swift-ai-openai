<!-- Generated distribution; edit the canonical repository. -->
# swift-ai-openai 1.2.0

Independent Swift-native port of Vercel AI SDK. Source and upstream dispositions are in PROVENANCE.json and Porting/.

## Distribution manifest

Add this package to your SwiftPM dependencies:

```swift
.package(url: "https://github.com/SwiftAISDK/swift-ai-openai.git", from: "1.2.0")
```

Products: `SwiftAIOpenAI`.
Contribute and report issues in the canonical SwiftAISDK repository.

## Authored usage guide

# Swift AI OpenAI

An independent Swift-native port of the provider-facing Vercel AI SDK package
`@ai-sdk/openai`. Responses and chat, completions, embeddings, images, transcription/speech, decisions/evaluation, batches, files, skills and the existing OpenAI Live WebSocket adapter.

Swift 6.3 or newer; declared platforms macOS 12 and iOS 15. This source is
maintained in the canonical SwiftAISDK repository and exported as an independently
versioned Swift package. Swift versions are independent of the npm baselines.

## Usage

Depend on `.product(name: "SwiftAIOpenAI", package: "swift-ai-openai")`.
For generation and explicit registries also add `swift-ai-core` and its `SwiftAI`
product. The canonical [example](https://github.com/SwiftAISDK/SwiftAISDK/blob/main/Examples/OpenAIOnly) contains a complete
manifest for local development and runs offline with an injected transport.

```swift
import SwiftAI
import SwiftAIOpenAI

let provider = try AIProviders.openAI(
    configuration: OpenAIProviderSettings(apiKey: "your-api-key")
)
let model = try provider.languageModel("your-model-id")
let result = try await AI.generateText(
    model: model,
    request: .init(messages: [.user("Hello")])
)
```

Native factories use typed `configuration:` settings. The legacy `settings:`
overloads belong to `SwiftAISDK`. When importing both facades, qualify `SwiftAI.AI`
or `SwiftAISDK.AI` and the appropriate factory namespace. Core uses explicit model
objects or registries; it does not initialize an implicit Gateway.

OpenAI depends on the generic compatible package for shared wire behavior; its
runtime does not depend on Anthropic, the aggregate, MCP or UI. Provider-specific
model catalogs, authentication/defaults, Responses and audio behavior are owned here.
`OpenAIProvider` is the native concrete factory type; the legacy OpenAI factory's
`SwiftAISDK.OpenAICompatibleProvider` return type remains unchanged.

## Porting and verification

Run `swift test --package-path Packages/swift-ai-openai --no-parallel` from the
canonical checkout. Full verification is `node Scripts/test-packages.mjs`, followed
by `node Scripts/verify-provider-isolation.mjs` and
`node Scripts/verify-provider-versions.mjs`. The latter uses synthetic local Git
tags, not released version histories.

`Porting/map.json` owns source/test/fixture relationships. Reviewed npm versions,
archive evidence and test snapshot dispositions remain in the canonical
`Porting/upstream-lock.json`. Extraction does not advance baselines or claim new
upstream parity. Cross-package wire APIs support port adapters; prefer the typed
provider factory for application code.

Licensed under Apache-2.0; see LICENSE. Vercel names identify provenance, not
affiliation. Contribute through the canonical SwiftAISDK repository. Distribution repositories are generated from it.

Original public initializer and helper signatures remain available for typed
function references, alongside the extended APIs. Their original defaults are preserved.
