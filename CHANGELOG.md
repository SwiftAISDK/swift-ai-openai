# Changelog

## 1.4.0

- Chat sends `json_schema` for schema output and leaves the schema unchanged; unsupported `flex`/`priority` service tiers are removed with upstream warnings; search-preview models drop `temperature`; `reasoningSummary` no longer leaks into chat bodies. Responses applies and strips `systemMessageMode`, `passThroughUnsupportedFiles` and `includeWebSearchSources`, keeps prompt-cache breakpoints, image detail and filenames, and orders GPT-6 warnings like upstream. Function tools send only their input schema as parameters.
  Compatibility: Source-compatible; changes are additive. Request bodies, results, warnings and errors change to match the reviewed upstream package.
