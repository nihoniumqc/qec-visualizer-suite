# Quantum Error Correction — Interactive Visualizer Suite

**Live site:** https://niharikaverma.netlify.app *(update with your actual landing page URL)*

Four free, interactive tools that make the core mechanics of quantum error correction (QEC) visible and explorable in the browser. No install, no login, no backend — every tool is a single self-contained HTML file using Canvas/SVG/Three.js for rendering.

Built by **Niharika Verma**, quantum error correction researcher focused on surface codes, decoding architectures, and fault-tolerant quantum systems.

---

## Tools

| Tool | Description | Live |
|---|---|---|
| [**Syndrome History & Spacetime Visualizer**](./tools/spacetime-visualizer) | Renders the full 3D spacetime volume (2 spatial + 1 time) that decoders like Harmony and Sparse Blossom operate on. Inject X errors and measurement faults, watch defect worldlines form, toggle decoder matching overlays. | [3dspacetimedecoding.netlify.app](https://3dspacetimedecoding.netlify.app) |
| [**MWPM Decoder Visualizer**](./tools/mwpm-decoder) | Step-by-step walkthrough of Minimum Weight Perfect Matching on a 5×5 surface code patch — syndrome extraction, defect graph construction, matching enumeration, correction, and logical-error verdict. | [mwpmdecoder.netlify.app](https://mwpmdecoder.netlify.app) |
| [**Concatenated Code Explorer**](./tools/concatenated-code-explorer) | Visualizes recursive concatenation of the 3-qubit bit-flip code. Drag a noise slider across the fault-tolerance threshold and watch logical error rates either collapse exponentially or explode. | [concatenatedcode.netlify.app](https://concatenatedcode.netlify.app) |
| [**Lattice Surgery / Logical Gate Visualizer**](./tools/lattice-surgery) | Two surface code patches merge and split to perform a fault-tolerant joint Pauli measurement (ZZ or XX), with a step-by-step protocol and an explainer of how two such cycles compose into a full logical CNOT. | [latticesurgery.netlify.app](https://latticesurgery.netlify.app) |

The root [`index.html`](./index.html) is the landing page that links all four together.

---

## Why these exist

Quantum error correction is one of the most consequential open problems in building useful quantum computers — and most of the intuition behind it (defect graphs, spacetime decoding, lattice surgery) lives in papers and slide decks, rarely in anything you can actually click on and explore. These tools are an attempt to close that gap.

## Tech stack

Intentionally minimal — no build pipeline, no package manager, no framework:

- Plain HTML / CSS / JavaScript
- [Three.js r128](https://threejs.org/) (via Cloudflare CDN) for the 3D spacetime visualizer
- [Chart.js](https://www.chartjs.org/) for the concatenated code error-rate plots
- Hand-rolled Canvas 2D rendering for the MWPM and lattice surgery tools
- Deployed via [Netlify](https://www.netlify.com/) drag-and-drop

## Running locally

Each tool is a single `index.html` file — no dependencies to install.

```bash
git clone https://github.com/<your-username>/qec-visualizer-suite.git
cd qec-visualizer-suite
```

Open any `index.html` directly in a browser, or serve the folder with VS Code's **Live Server** extension for a nicer dev loop (auto-reload on save):

1. Install the **Live Server** extension in VS Code
2. Right-click any `index.html` → **Open with Live Server**

## Deployment

Each tool is currently deployed independently on Netlify via drag-and-drop. To connect continuous deployment instead:

1. On [netlify.com](https://netlify.com), choose **Import an existing project → Deploy with GitHub**
2. Select this repository
3. Set the **Base directory** to the specific tool's folder (e.g. `tools/mwpm-decoder`)
4. Leave build command empty — these are static files, nothing to build

## License

MIT — free to use, fork, and adapt. See [LICENSE](./LICENSE).

## Contact

[LinkedIn](https://www.linkedin.com/in/) · Built for the quantum computing community.
