# auto-forex-protobuf

gRPC protobuf contracts for AutoForexV2.

## Setup

```bash
uv sync
```

## Development

```bash
uv run ruff check .
uv run ruff format .
uv run ty check
```

## Generate Python Stubs

```bash
uv run python -m grpc_tools.protoc \
  -I proto \
  --python_out=src \
  --pyi_out=src \
  --grpc_python_out=src \
  proto/autoforex/server/v1/trading_service.proto
```
