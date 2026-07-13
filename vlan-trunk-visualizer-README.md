# VLAN Trunk Visualizer

An interactive diagram showing how VLANs, access ports, and trunk links behave in a multi-switch environment — built as a companion tool for the *How Protocols Work, and How They Break* series on [ubritsa.com](https://ubritsa.com).

## What it shows

- **3 switches**, each with a distributed member of every VLAN — the setup you'd see when the same VLANs need to reach users spread across multiple floors or wiring closets.
- **3 VLANs**: VLAN 10 (Finance), VLAN 20 (Engineering), VLAN 30 (Guest), each with its own access port on every switch.
- **Trunk links** between switches carrying all three VLANs at once, rendered as three parallel colored lanes wrapped in a single white-bordered casing — one physical cable, multiple logical VLANs riding it.
- **Live traffic animation**: frames continuously flow host-to-host along access links and trunk lanes at a readable pace (no step-by-step control needed — just watch it run).
- **Unicast vs. broadcast**: distinguished visually (solid dot vs. hollow ring) in the shape key, so you can see the difference between a frame going to one host and one flooding an entire VLAN.
- **Delivered-frame counters**: a running count per VLAN, shown inline next to each VLAN's legend entry.

## How to use it

Open `vlan-trunk-visualizer.html` directly in any modern browser. No server, build step, or install required. An internet connection is needed only to load the JetBrains Mono / Syne fonts from Google Fonts — the tool still functions without it, just with fallback system fonts.

## What to watch for

- Each host's frames only ever travel to same-VLAN destinations, even though every VLAN's traffic is physically riding the same trunk cable between switches.
- The trunk casing represents one physical link — the three lanes inside it are a visual aid for the logical VLAN separation via 802.1Q tagging, not three separate wires.

## License

MIT — see the repository [LICENSE](LICENSE). A credit back to Goblin Eaters Cyber Cavern (ubritsa.com) if you reuse or adapt this tool is appreciated but not required.
