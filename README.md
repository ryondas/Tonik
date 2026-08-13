## Tonik

From-scratch LLM inference engine (Java) serving a from-scratch GPT trained on TinyShakespeare and Llama 3.2 1B.

### Layout

- `engine/` — Java, Gradle project. SIMD kernels, paged KV cache, gRPC server.
- `trainer/` — Python. Training, export to `.tonik` weight format, golden-tensor dumps for parity tests.
- `clients/python/` — thin gRPC client.
- `golden/` — reference tensors both halves validate against.
- `models/` — model weights (gitignored, not committed).

The two halves communicate only through the `.tonik` weight format and the `golden/` parity files.
