# Entropy Collapse Engine

This repository contains a runnable C# console application that simulates the "entropy collapse"
pipeline described in the prompt. It ingests a JSON shard with entropy deltas and motifs, runs a
series of deterministic transforms, and emits a `proof_capsule.json` in the capsule v1.1.0 schema.

## Getting started

```bash
dotnet --version  # ensure .NET 8 SDK is installed
```

### Restore, build, and test

```bash
dotnet restore
dotnet build
dotnet test
```

### Running the engine

```bash
dotnet run --project src/EntropyCollapseEngine --out out --in data/sample_input.json
```

If `--in` is omitted, the engine falls back to a built-in sample input. The output directory defaults
to `out`.

## Repository layout

- `src/EntropyCollapseEngine` – console application and engine implementation
- `test/EntropyCollapseEngine.Tests` – xUnit smoke tests
- `data/sample_input.json` – example shard
- `.github/workflows/ci.yml` – GitHub Actions pipeline running restore/build/test
