# dl-loop-fixed

Fixed roles continuous loop — A executes with real host tools (scrape/file/dir),
B continuously reviews every action and selectively requests evidence, delivering
advisory deception readings (never blocking) plus context broadening.

- A: `moonshotai/kimi-k3` via NVIDIA NIM; tools: ScrapeWebsiteTool, FileRead/Write, DirectoryRead
- B: `moonshotai/kimi-k3` via NVIDIA NIM; tools: URLReadTool, DirectoryReadTool (read-only)
- Both use shared state; evidence is selective (B decides), never mandatory.

Run: `uv sync && NVIDIA_NIM_API_KEY=... uv run crewai run` where the flow's .env
must define NVIDIA_NIM_API_KEY (base URL is already in flow.json).
