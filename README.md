# FallMesh

**Sovereign Mesh Protocol** -- the real-time topology map connecting every product, API, tool, and hub across AI Native Solutions.

FallMesh is the connective tissue of the entire Fall ecosystem. Every sovereign tool is a node. Every node has a prime number ID. Every connection is peer-to-peer. There is no central server, no platform dependency, and no subscription.

Built under Konomi Architecture. Member of the AI Craftspeople Guild.

**Live:** [https://sjgant80-hub.github.io/fallmesh/](https://sjgant80-hub.github.io/fallmesh/)

---

## What It Is

FallMesh is a sovereign mesh network protocol and live visualization dashboard. It serves three purposes:

1. **Discovery** -- every node in the AI Native Solutions ecosystem registers itself in a single `mesh.json` manifest. Any node can discover any other node by reading this file.
2. **Topology** -- the interactive canvas renders the full mesh as a force-directed or circular graph with animated data flow particles, node health indicators, and real-time statistics.
3. **Protocol specification** -- FallMesh defines the standard envelope, capability advertisement, and communication channels that all sovereign tools use to interoperate.

The entire dashboard is a single HTML file. It runs in the browser with zero server dependencies. All configuration and API keys are stored locally in IndexedDB.

---

## How It Works

### mesh.json Schema

The `mesh.json` file is the canonical manifest for the entire mesh. Every node in the ecosystem is registered here.

```json
{
  "mesh": "fallmesh",
  "version": "1.0",
  "hub": "https://sjgant80-hub.github.io/ai-nativesolutions/",
  "updated": "2026-05-18T00:00:00Z",
  "nodes": [
    {
      "id": "fallcall",
      "name": "FallCall",
      "type": "product",
      "prime": 2,
      "url": "https://sjgant80-hub.github.io/fallcall/",
      "sovereign": true,
      "storage": "indexeddb"
    }
  ]
}
```

**Node fields:**

| Field | Type | Description |
|---|---|---|
| `id` | string | Unique identifier for the node |
| `name` | string | Display name |
| `type` | string | Node classification: `hub`, `product`, `trilogy`, or `tool` |
| `prime` | number | Prime number ID on the prime spine addressing scheme |
| `url` | string | Deployment URL (GitHub Pages) |
| `sovereign` | boolean | Whether the node is a self-contained single-file application |
| `storage` | string | Storage mechanism: `indexeddb`, `api`, or `npm` |

### Design Principles

1. **Sovereignty** -- every node owns its data. No node can compel another. Storage is IndexedDB (local). Keys are user-provided. APIs are user-selected.
2. **Bring Your Own Keys** -- each node stores API keys locally. Keys are never transmitted to mesh peers.
3. **Zero Infrastructure Cost** -- all nodes are static HTML on GitHub Pages (free forever). Discovery uses static JSON manifests. Signaling uses BroadcastChannel and postMessage.
4. **Recursive Mesh** -- every node can discover every other node via the hub manifest. Each node publishes its own capabilities in meta tags.
5. **Prime Spine Addressing** -- node IDs map to prime numbers. Hub = 1 (unity). Products = primes. The address space is MACCubeFACE(127) compatible.

### Communication Channels

All communication is zero-server:

- **Same-origin:** `BroadcastChannel('fallmesh')`
- **Cross-tab:** `localStorage` events and polling
- **Cross-origin:** URL fragment messaging and `postMessage`
- **Persistence:** IndexedDB per node

---

## All Nodes

### Hubs

| Prime | Name | URL |
|---|---|---|
| 1 | AI Native Solutions | [ai-nativesolutions](https://sjgant80-hub.github.io/ai-nativesolutions/) |
| 47 | FallMesh | [fallmesh](https://sjgant80-hub.github.io/fallmesh/) |
| 113 | FallGo | [fallgo](https://sjgant80-hub.github.io/fallgo/) |

### Products

| Prime | Name | URL |
|---|---|---|
| 2 | FallCall | [fallcall](https://sjgant80-hub.github.io/fallcall/) |
| 7 | FallLearn | [falllearn](https://sjgant80-hub.github.io/falllearn/) |
| 11 | FallGrade | [fallgrade](https://sjgant80-hub.github.io/fallgrade/) |
| 13 | FallConsensus | [fallconsensus](https://sjgant80-hub.github.io/fallconsensus/) |
| 17 | FallSignal | [fallsignal](https://sjgant80-hub.github.io/fallsignal/) |
| 19 | FallForensics | [fallforensics](https://sjgant80-hub.github.io/fallforensics/) |
| 23 | OracleEngine | [oracleengine](https://sjgant80-hub.github.io/oracleengine/) |
| 29 | FallLead | [falllead](https://sjgant80-hub.github.io/falllead/) |
| 31 | Fall127 | [fall127agents](https://sjgant80-hub.github.io/fall127agents/) |
| 83 | FallScout | [fallscout](https://sjgant80-hub.github.io/fallscout/) |
| 89 | FallForce | [fallforce](https://sjgant80-hub.github.io/fallforce/) |
| 97 | FallOffice | [falloffice](https://sjgant80-hub.github.io/falloffice/) |
| 101 | FallAccount | [fallaccount](https://sjgant80-hub.github.io/fallaccount/) |
| 103 | ExitEngine | [exitengine](https://sjgant80-hub.github.io/exitengine/) |
| 107 | SMB AI OS | [smbaios](https://sjgant80-hub.github.io/smbaios/) |
| 127 | Cassie Torus BTC Solver | [cassietorusbtc135solver](https://sjgant80-hub.github.io/cassietorusbtc135solver/) |
| 131 | GymOS | [gymos](https://sjgant80-hub.github.io/gymos/) |
| 137 | FallSalesCRM | [fallsalescrm](https://github.com/sjgant80-hub/fallsalescrm) |

### Trilogy AI Pipeline

| Prime | Name | URL |
|---|---|---|
| 53 | DocMind API | [docmind-api](https://sjgant80-hub.github.io/docmind-api/) |
| 59 | Deep API | [deep-api](https://sjgant80-hub.github.io/deep-api/) |
| 61 | Flux API | [flux-api](https://sjgant80-hub.github.io/flux-api/) |
| 67 | Trilogy SDK | [trilogy-sdk](https://sjgant80-hub.github.io/trilogy-sdk/) |
| 71 | Trilogy Framework | [trilogy-framework](https://sjgant80-hub.github.io/trilogy-framework/) |
| 73 | Trilogy Forge | [trilogy-forge](https://sjgant80-hub.github.io/trilogy-forge/) |
| 79 | FallCube API | [fallcube-api](https://sjgant80-hub.github.io/fallcube-api/) |

### Tools

| Prime | Name | URL |
|---|---|---|
| 109 | ToneSmith | [tonesmith](https://github.com/sjgant80-hub/tonesmith) |

---

## How to Add a Node

1. Choose the next available prime number for your node ID.
2. Add a new entry to the `nodes` array in `mesh.json`:

```json
{
  "id": "yournodeid",
  "name": "YourNodeName",
  "type": "product",
  "prime": 139,
  "url": "https://sjgant80-hub.github.io/yournodeid/",
  "sovereign": true,
  "storage": "indexeddb"
}
```

3. Set `type` to the appropriate classification: `hub`, `product`, `trilogy`, or `tool`.
4. Set `sovereign` to `true` if the node is a self-contained single-file HTML application, `false` if it is an API or external dependency.
5. Set `storage` to `indexeddb` for sovereign apps, `api` for API services, or `npm` for packages.
6. Update the `updated` timestamp in the root of `mesh.json`.
7. Commit and push. The live mesh at the deployment URL will reflect the new node automatically.

**Prime spine convention:** Hub = 1. All other nodes use prime numbers. Never reuse a prime that is already assigned.

---

## Live URL

[https://sjgant80-hub.github.io/fallmesh/](https://sjgant80-hub.github.io/fallmesh/)

The dashboard features:

- **Interactive mesh canvas** with force-directed and circular layout modes
- **Animated data flow particles** showing real-time connections between nodes
- **Node grid** with deployment status for every registered node
- **Protocol specification** with the full FallMesh envelope and capability schema
- **Data flow table** mapping all inter-node data relationships
- **Health dashboard** with node counts, edge counts, and availability status
- **Configuration panel** for mesh identity, API key storage, and preferences
- **Export/import** for mesh state snapshots

---

## Repository

[https://github.com/sjgant80-hub/fallmesh](https://github.com/sjgant80-hub/fallmesh)

Part of **AI Native Solutions**: [https://sjgant80-hub.github.io/ai-nativesolutions/](https://sjgant80-hub.github.io/ai-nativesolutions/)

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---

Powered by Konomi Architecture. Member of the [AI Craftspeople Guild](https://aicraftspeopleguild.github.io/).
