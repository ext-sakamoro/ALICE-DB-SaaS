# ALICE-DB SaaS

Model-based LSM-Tree database service

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-DB |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/put` | キー・バリュー書き込み |
| `GET  /api/v1/get/{key}` | キーで読み取り |
| `POST /api/v1/scan` | 範囲スキャン |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
