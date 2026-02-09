<h1 align="center">flux</h1>

<p align="center">Search, monitor, and nuke processes with ease, with system resource tracking</p>

<p align="center">
  <img src="assets/demo1.png" alt="demo" width="700">
  <img src="assets/demo2.png" alt="demo" width="700">
</p>

<p align="center">
  <img alt="GitHub Actions Workflow Status" src="https://img.shields.io/github/actions/workflow/status/VG-dev1/flux/rust.yml?style=for-the-badge">
  <img alt="Crates.io Version" src="https://img.shields.io/crates/v/flux-cli?style=for-the-badge">
  <img alt="Crates.io License" src="https://img.shields.io/crates/l/flux-cli?style=for-the-badge">
  <img alt="Crates.io Total Downloads" src="https://img.shields.io/crates/d/flux-cli?style=for-the-badge">
</p>


## Why flux

Tools like `htop` and `btop` cram an overwhelming amount of information onto the screen-columns, graphs, and stats everywhere, making it hard to find the process you actually care about. `flux` strips away the clutter and focuses on what matters: quickly finding, monitoring, and acting on processes in a clean, readable interface. With live CPU and memory tracking, port-aware process discovery, and intuitive keyboard navigation, `flux` gives you all the actionable insights without the messy visual noise, letting you manage your system faster and more efficiently.

## Features
- **Real-time Resource Monitoring**: Track CPU and memory usage, live
- **Port Discovery**: Identify which processes are listening on specific ports
- **Batch Actions**: Select multiple processes with `Space` or use `--nuke` to batch-kill by filter
- **Easy Navigation**: Move around effortlessly with `j/k` or arrow keys
- **Smart UI**: Context-aware coloring for high resource usage

## Usage
```bash
# See all processes, live (sorted by CPU)
flux

# Pre-filter by process name
flux -f chrome

# Use a different signal (default: SIGKILL)
flux -s SIGTERM

# Sort by memory usage
flux --sort mem

# Sort by PID
flux --sort pid

# Sort by name
flux --sort name

# See system resource usage (CPU and memory)
flux --resources

# Kill all the processes with a specific name
flux -f chrome --nuke
```

## Options

| Flag | Description |
|------|-------------|
| `-f, --filter <name>` | Pre-filter processes by name |
| `-s, --signal <signal>` | Signal to send (default: KILL) |
| `--sort <field>` | Sort by: cpu, mem, pid, name, port |
| `--ports` | Show only processes with open ports |
| `--port <PORT>` | Filter by specific port number |

## Installation

### From source

```bash
cargo install flux-cli
```

## License
MIT
