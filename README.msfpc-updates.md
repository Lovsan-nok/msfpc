# MSFPC: README additions (Progress UI & Theme)

This file contains a brief note describing the recent updates to msfpc.sh in branch update/2026-progress-ui.

What's new (v2.1.0)
- Progress UI: per-payload progress bar and stepper for batch mode. Uses a simple timings cache (~/.msfpc/timings) to estimate remaining time.
- Theme support: --theme <name> (default|solarized|mono|red) changes the script color palette.
- Banner fonts: --font <figlet-font> will render the banner using figlet if installed.
- No-color: --no-color disables colorized output for compatibility with limited terminals or piping.
- Safety: trap-based cleanup and mkdir-based lock for the timings cache to avoid concurrent writes.

Usage examples
- Single payload: ./msfpc.sh windows 192.168.1.10 4444
- With theme and figlet font: ./msfpc.sh --theme solarized --font slant windows 192.168.1.10 4444
- Batch: ./msfpc.sh --all 192.168.1.10

Notes & limitations
- The --font option requires figlet to be installed and only affects the ASCII banner.
- The timings cache is a heuristic and will improve after multiple runs.
- The script cannot change your terminal emulator's font; it only influences in-script banner styling.

