# Protobuf Package Guide

`protobuf` owns the gRPC contract between `api` and `server`.

## Responsibilities

- Maintain `.proto` files for gRPC services and messages.
- Version service namespaces when making breaking contract changes.
- Provide tooling dependencies for generating Python gRPC stubs.

## Boundaries

- Do not put gRPC server implementation here; use `server`.
- Do not put gRPC client orchestration here; use `api`.
- Do not put REST/OpenAPI definitions here; use `openapi`.

## Commands

```bash
uv sync
uv run ruff check .
uv run ruff format .
uv run ty check
```

Generate Python stubs with:

```bash
uv run python -m grpc_tools.protoc \
  -I proto \
  --python_out=src \
  --pyi_out=src \
  --grpc_python_out=src \
  proto/autoforex/server/v1/trading_service.proto
```
