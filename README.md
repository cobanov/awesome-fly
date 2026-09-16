# Awesome Fly [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> [!TIP]
> **Build your own fly experiment with [fly-connectome-template](https://github.com/cobanov/fly-connectome-template) by [Mert Cobanov](https://github.com/cobanov).**
>
> Start with a real MaleCNS soma atlas, the anatomical Flybody mesh, and a React + Three.js workbench. Bring your own environment and model; the starter includes a documented model-output format, not a pretrained brain.
>
> **[Use this template →](https://github.com/new?template_name=fly-connectome-template&template_owner=cobanov)** · [Explore the starter](https://github.com/cobanov/fly-connectome-template) · [Model integration guide](https://github.com/cobanov/fly-connectome-template/blob/main/docs/MODEL-INTEGRATION.md)
>
> Source-available under a [custom license](https://github.com/cobanov/fly-connectome-template/blob/main/LICENSE): linked template credit is required in your web UI and repository README.

> A curated collection of fruit fly connectome projects, from Doom and desktop pets to brain models, biomechanical bodies, and research tools.

Explore what people are building with **MaleCNS**, **FlyWire**, and the *Drosophila melanogaster* connectome. Each entry links to its creators' repository and explains what it actually offers.

Start with a [game](#games-and-control-experiments), explore a [desktop fly](#desktop-flies-and-interactive-worlds), or build your own using the [research foundations](#brain-models-and-embodied-simulation).

**Built something with a fly connectome? Add your own repository with a pull request.** Read the [contribution guide](CONTRIBUTING.md), [open a pull request](https://github.com/cobanov/awesome-fly/pulls), or [suggest a project](https://github.com/cobanov/awesome-fly/issues/new?template=add-project.yml).

## Contents

- [Start here](#start-here)
- [Games and control experiments](#games-and-control-experiments)
- [Desktop flies and interactive worlds](#desktop-flies-and-interactive-worlds)
- [Language, art, and other experiments](#language-art-and-other-experiments)
- [Brain models and embodied simulation](#brain-models-and-embodied-simulation)
- [Datasets and official resources](#datasets-and-official-resources)
- [Analysis libraries and viewers](#analysis-libraries-and-viewers)
- [Tutorials and papers](#tutorials-and-papers)
- [Related lists](#related-lists)
- [Contributing](#contributing)

## Start here

A **connectome** records neurons and their connections. A simulation adds assumptions about neuron dynamics, sensory input, and motor output. A moving fly, changing weights, or a game demo does not by itself demonstrate biological fidelity or learned behavior.

- **MaleCNS** covers the adult male central nervous system, including brain and ventral nerve cord. The official project dates v1.0 to **June 8, 2026** and the Cell paper to **September 3, 2026**. [Project and release history](https://male-cns.janelia.org/).
- **FlyWire / FAFB** is an adult female **brain** connectome, a different dataset from MaleCNS. [FlyWire](https://flywire.ai/).
- **Flybody** and **NeuroMechFly** supply simulated bodies and environments. Using either does not automatically connect a brain model to the body.

**Reading the list:** community entries summarize their authors' documentation, reviewed on **September 12, 2026**. These are source reviews, not independent reproductions. **Prototype**, **circuit subset**, and **release pending** identify useful limitations. Neuron counts depend on the release and filtering; synaptic contacts and directed neuron-pair connections are different quantities.

## Games and control experiments

- [Doomfly](https://github.com/nftechie/doomfly) by **nftechie** - MaleCNS simulation connected to ViZDoom through modeled visual inputs and a fixed button readout. Includes plasticity experiments and negative validation results; learned survival has not been demonstrated.
- [FlyDoom](https://github.com/eganeganegan/flydoom) by **eganeganegan** - Research framework comparing a MaleCNS-constrained sparse recurrent controller with rewired graphs, conventional neural networks, and other controls on simple VizDoom tasks.
- [Fly64](https://github.com/ornata/fly) by **ornata** - Hooks a MaleCNS model up to Super Mario 64, with a local dashboard and macOS setup. A playful experimental controller; requires your own game ROM.
- [Fly Brain Minecraft](https://github.com/blendi-remade/fly-brain-minecraft) by **blendi-remade** - Fabric mod that runs a filtered MaleCNS graph for each fly mob, with modeled sensory inputs, motor readouts, and live neural HUDs.
- [Flyhard](https://github.com/MarkUnthank/flyhard) by **MarkUnthank** - Trains a MaleCNS-based model to operate a steering wheel through simulated fly limbs and connect it to CARLA. Documents a bounded steering result; visual driving remains a future milestone.
- [Help the Fly Escape](https://github.com/dzhng/fly-escape) by **dzhng** - Arrange household objects and observe flies navigating a 3D browser game. Rust/WASM simulation using a **selected MaleCNS circuit**. [Play](https://fly-escape.vercel.app/).
- [Swat](https://github.com/hrook1/Swat) by **hrook1** - Browser arcade game with a visible escape circuit: 6,000 MaleCNS neurons influence evasive movement alongside authored game mechanics. **Circuit subset.** [Play](https://fruitfly-tiny-brain.vercel.app/).
- [FlyBrain](https://github.com/Jhongdlp/FlyBrain) by **Jhongdlp** - MaleCNS-based game-boss experiment with a Rust neural engine, Python training environment, and Three.js viewer.
- [FlyPong](https://github.com/jonatasperaza/FlyPong) by **jonatasperaza** - Pong controller built from a MaleCNS subgraph, with documented controls and negative results for its dopamine-inspired plasticity experiments. **Circuit subset.**
- [Connectome Fighter](https://github.com/Unjuno/connectome-fighter) by **Unjuno** - MaleCNS controller connected to FightingICE through explicit sensory and action mappings, with a research ledger separating connectome structure from project-defined learning rules.
- [Fly Chess Lab](https://github.com/tolatolatop/fly-chess) by **tolatolatop** - FlyWire chess experiment with a Rust/WASM LIF simulation, spike traces, and disconnection controls. Uses an engineered, currently untrained move readout. [Demo](https://tolatolatop.github.io/fly-chess/).
- [fly-craftax](https://github.com/liuzihe02/fly-craftax) by **liuzihe02** - Connectome simulation connected to Craftax, with PPO training of a descending-neuron readout, baseline comparisons, and a replay viewer. **Research prototype.**
- [Fly Dino](https://github.com/cobanov/flyjump) by **cobanov** - Original Chromium Dino controlled by a fixed 80-neuron MaleCNS circuit with simplified leaky tanh dynamics and a 243-parameter readout trained with the cross-entropy method (CEM). Includes live computed activity, reproducible training, held-out benchmarks, and circuit-silencing controls. **Circuit subset:** only the artificial readout is trained. [Play](https://flydino.cobanov.dev/) · [Methods and results](https://github.com/cobanov/flyjump/blob/main/docs/experiment.md).
- [NeuroCraft Fly](https://github.com/evnsnclr/neurocraft-fly-public) by **evnsnclr** - Minecraft project with a recorded MaleCNS-based interactive demo and a release roadmap. **Release pending:** the public repository currently contains project materials, not runnable mod or companion source.
- [FLYFEAR](https://github.com/furkancak1r/flyfear) by **furkancak1r** - Godot horror prototype where a MaleCNS-derived simulation influences a fly and an external adaptive event policy. Includes training and validation reports. [Play](https://furkancakir.dev/flyfear/).
- [FLYT3](https://github.com/seanphan/flyt3) by **seanphan** - Tic-tac-toe against a full-graph MaleCNS LIF simulation with a REINFORCE-trained descending and VNC readout, plus a fire-watch mode that classifies satellite wildfire-damage tiles through the same frozen circuit (60.8% on 5 classes) with live activity and region-lesioning views. **Full retained graph; only the readout is trained.** Reports its own negative control: a pooled-pixel MLP on the same inputs scores 85.7%. Self-hosted demo, no public link.

## Desktop flies and interactive worlds

- [DesktopFly](https://github.com/DenisSergeevitch/desktop-fly) by **DenisSergeevitch** - A macOS desktop fly combining FlyWire spiking circuits with a MaleCNS brain-to-leg extract, modeled senses, and articulated behavior. Includes an Electron port.
- [gnat](https://github.com/lubabs770/gnat) by **lubabs770** - Linux/Hyprland desktop port of DesktopFly with a brain window and stimulation controls. Uses a **668-neuron circuit subset**.
- [DesktopFly for Linux](https://github.com/somsom10/desktop-fly-linux) by **somsom10** - Python/GTK port of DesktopFly for GNOME on X11 and Wayland, retaining the upstream FlyWire circuit and documenting platform limitations.
- [FlyBrain](https://github.com/snedea/flybrain) by **snedea** - Browser-based FlyWire FAFB v783 LIF simulation with food, touch, light, and temperature inputs and a live neural activity display.
- [FlyWire Neuro](https://github.com/pusulamkendim/flywire-neuro) by **pusulamkendim** - Local FlyWire LIF simulation linked to a persistent 3D body, sensory controls, and recorded runs. Descending-neuron activity selects measured or cached motor behavior. **Research prototype.**
- [Closed-Loop Fly](https://github.com/ZeroXClem/closed-loop-fly) by **ZeroXClem** - Browser sensorimotor loop joining a modeled compound eye and optic lobe to MaleCNS descending-neuron readouts and a simulated flying body.
- [flyverse](https://github.com/tel-0s/flyverse-core) by **tel-0s** - MaleCNS simulation with modeled color vision, smell, taste, wind, locomotion, and an inspectable room environment. Sensory and motor physiology remain project assumptions.
- [NeuroTerrarium](https://github.com/5p00kyy/neuroterrarium) by **5p00kyy** - Inspectable 3D lab with a synthetic terrarium and a separate 51-body MaleCNS giant-fiber microcircuit. Reports a negative topology-control result. **Circuit subset.**
- [FLYBOARD](https://github.com/NullLabTests/flybrain) by **NullLabTests** - CPU arcade interface for injecting current into named MaleCNS populations while viewing the modeled voltage and spike field.
- [Infinite Sugar](https://github.com/cnqso/infinite-sugar) by **cnqso** - Browser artwork placing a FlyWire-based fly in a terrarium with continuous sweet-sensing input. Neural activity drives some movements while wings and small foot motions use supplied patterns. [Experience](https://infinitesugar.cnqso.com/).

## Language, art, and other experiments

- [FLM](https://github.com/nftechie/flm) by **nftechie** - Frozen language model coupled to the retained MaleCNS graph through a trained readout adapter. Language ability comes from the pretrained language model.
- [fly-brain](https://github.com/lixiang1076/fly-brain) by **lixiang1076** - FlyWire LIF simulation with a natural-language interface and project-defined dopamine-learning experiments.
- [Fly / Wirehead](https://github.com/mattyhempstead/fly-wirehead) by **mattyhempstead** - A MaleCNS simulation receives frames from insect videos on a virtual phone. Local Python/C++ simulation, browser observation chamber, and neural telemetry.
- [FlyScroll](https://github.com/ranagwho/Fruitfly-Doomscroller) by **ranagwho** - MaleCNS-based video-feed experiment where modeled visual and mushroom-body activity influences when the viewer advances to the next clip.
- [Stonkfly](https://github.com/nftechie/stonkfly) by **nftechie** - Experimental MaleCNS controller with market-chart inputs, paper trading, and optional Coinbase integration. Includes modeled reinforcement and memory; profitable learning has not been demonstrated.
- [OpenFly](https://github.com/marketcalls/openfly) by **marketcalls** - MaleCNS-based controller for a paper-traded NIFTY options strategy through OpenAlgo. Live trading is opt-in and no profitable edge has been demonstrated.
- [Fly Lab](https://github.com/Apolotary/fly-lab) by **Apolotary** - Ableton Live music experiments driven by simulated fly motor circuits and a small trainable musical readout. The measured wiring remains fixed.
- [Faiku](https://github.com/xyzzyapps/faiku) by **xyzzyapps** - Haiku and glyph-tracing experiment using MaleCNS simulation and mushroom-body-inspired reinforcement, with a separate reduced fallback model.
- [Fruitless](https://github.com/nicodunks/fruitless) by **nicodunks** - MaleCNS intervention study and Three.js visualization testing how blocking modeled mAL output changes activity in courtship-related candidate neurons.
- [Fruit Fly Fashion](https://github.com/jtc268/fruit-fly-fashion) by **jtc268** - Reproducible art experiment using MaleCNS spike vectors to control the placement, rotation, and scale of print designs.
- [mindmeld-with-fly](https://github.com/Decentricity/mindmeld-with-fly) by **Decentricity** - Sparse MaleCNS reservoir experiments with terminal rendering and recording/replay. **Prototype:** the README places the EEG interface in a future phase.

## Brain models and embodied simulation

- [Drosophila brain model](https://github.com/philshiu/Drosophila_brain_model) by **philshiu and collaborators** - Research code for the Shiu et al. connectome-based leaky integrate-and-fire model, including activation/silencing experiments, notebooks, and FlyWire data configuration.
- [fly-brain](https://github.com/eonsystemspbc/fly-brain) by **Eon Systems** - FlyWire whole-brain LIF implementation based on Shiu et al., with multiple simulation backends and benchmarking tools. This repository supplies the neural model; it is not a complete embodied demo package.
- [flybody](https://github.com/TuragaLab/flybody) by **TuragaLab / Google DeepMind / HHMI Janelia** - Anatomically detailed MuJoCo fruit-fly body, walking and flight environments, and reinforcement-learning examples. A body and control platform.
- [FlyGym / NeuroMechFly](https://github.com/NeLy-EPFL/flygym) by **NeLy-EPFL** - Python framework for embodied sensorimotor experiments with a biomechanical fly, sensory interfaces, and physical environments. Check version-specific documentation when following older tutorials.
- [flyvis](https://github.com/TuragaLab/flyvis) by **TuragaLab** - PyTorch implementation of connectome-constrained models of the fly visual system, with pretrained models and analysis tutorials.
- [train-your-fly / connectome](https://github.com/eudald-seeslab/train-your-fly) by **eudald-seeslab** - PyTorch Geometric toolkit for connectome-constrained vision models: a *Drosophila* eye model feeding message passing over the FlyWire v783 whole-brain graph to a Kenyon-cell readout. **Fixed wiring; only per-synapse gains and a linear readout are trained.** The [connectome](https://github.com/eudald-seeslab/connectome) study adds colour, shape, and numerosity tasks, randomized-ensemble controls, and manifold analysis; graphs archived on [Zenodo](https://doi.org/10.5281/zenodo.21549559).
- [webgpu-fly](https://github.com/abgnydn/webgpu-fly) by **abgnydn** - Browser-based WebGPU/WASM experiment joining FlyWire brain activity, MANC nerve-cord data, and a Flybody body through explicit approximate motor mappings. [Demo](https://webgpu-fly.pages.dev/).
- [NeuroFly](https://github.com/seven-monarchs/NeuroFly) by **seven-monarchs** - Closed-loop personal research project coupling FlyWire-based neural activity to a NeuroMechFly body, with recorded simulations and documented assumptions.
- [Fruit Fly Lab](https://github.com/vaibhavkedarisetti/fruit-fly-lab) by **vaibhavkedarisetti** - Interactive FlyWire v783 whole-brain LIF simulation with stimulus controls and activity visualization. **Research prototype.**
- [CHIMERA](https://github.com/caparison1234/chimera) by **caparison1234** - Drosophila larval connectome experiment linking a 1,373-neuron circuit to a MuJoCo body and a language-to-stimulus interface. **Larval circuit subset.**
- [Connectome OS](https://github.com/ruvnet/Connectome-OS) by **ruvnet** - Rust LIF runtime and debugging interface for stimulating, cutting, and measuring FlyWire-derived graph activity. **Alpha research preview.**
- [FastFly](https://github.com/eonfathom/FastFly) by **eonfathom** - CUDA and CuPy simulator targeting real-time or faster execution of the FlyWire v783 graph on a consumer NVIDIA GPU.
- [MaleCNS on Apple MPS](https://github.com/seohyunjun/mps-malecns-model) by **seohyunjun** - Experimental PyTorch MPS simulator for Apple Silicon with verified data preparation, named-cell stimulation, and 3D activity reports.
- [AxonWeave](https://github.com/dhakalnirajan/axonweave) by **dhakalnirajan** - Python library exposing MaleCNS as a sparse, trainable substrate for NumPy, PyTorch, and TensorFlow while keeping source topology and modeling policies explicit.
- [Embodied fly-brain](https://github.com/erojasoficial-byte/fly-brain) by **erojasoficial-byte** - Community research repository combining a FlyWire spiking model with NeuroMechFly/MuJoCo, sensory experiments, and an accompanying preprint.
- [Wired Different](https://github.com/dhruvin-sarkar/ConnectomeLens) by **dhruvin-sarkar** - classifier predicting sexually dimorphic cell types from male CNS connectome (male-cns v1.0) wiring, validated against degree-preserving null graphs; static demo with atlas, pathfinder and guessing game.
  
## Datasets and official resources

- [MaleCNS](https://male-cns.janelia.org/) - Official male CNS project, cell-type exploration, release history, and [downloads](https://male-cns.janelia.org/download/). Collaboration between FlyEM/HHMI Janelia, Cambridge, MRC LMB, and Google Research.
- [MaleCNS project source](https://github.com/janelia-flyem/male-cns) - Source for the project website and Dimorphism Explorer.
- [MaleCNS Cell Type Explorer](https://github.com/reiserlab/celltype-explorer-drosophila-male-cns) - Source and generated documentation for browsing MaleCNS v1.0 cell types, connectivity, regions, and morphology.
- [MaleCNS supplemental data](https://github.com/flyconnectome/2025malecns) - Derived data and analysis notebooks accompanying Berg et al., including sensorimotor flow and cell-type information.
- [Male optic lobe connectome code](https://github.com/reiserlab/male-drosophila-visual-system-connectome-code) - Analysis and reproduction code accompanying the complete male visual-system connectome study.
- [BANC project](https://github.com/htem/BANC-project) - Data, figures, notebooks, and documentation for the adult female Brain-And-Nerve-Cord connectome and its accompanying publication.
- [FlyWire](https://flywire.ai/) - Adult female brain reconstruction, research resources, and links to exploration tools.
- [FlyWire annotations](https://github.com/flyconnectome/flywire_annotations) - Neuron annotations and other data products for the FlyWire v783 release.
- [Drosophila neurotransmitters](https://github.com/flyconnectome/drosophila_neurotransmitters) - Versioned literature-derived neurotransmitter ground truth linked across major fly connectome datasets.
- [Optic lobe annotations](https://github.com/flyconnectome/ol_annotations) - Cross-dataset cell-type matches between FAFB/FlyWire and the MaleCNS optic lobe.

Follow each upstream dataset's citation and licensing requirements. The license of this list does not relicense linked code, datasets, or artwork.

## Analysis libraries and viewers

- [Codex](https://github.com/murthylab/codex) by **Murthy Lab** - Source for the FlyWire Connectome Data Explorer. [Explore neurons](https://codex.flywire.ai/).
- [FlyBrainLab](https://github.com/FlyBrainLab/FlyBrainLab) - Interactive platform for exploring fly brain data, constructing executable circuits, and studying their modeled function.
- [EOScircuits](https://github.com/FlyBrainLab/EOScircuits) by **FlyBrainLab** - Executable models of the Drosophila antenna, antennal lobe, and mushroom body for early olfactory-system experiments.
- [NAVis](https://github.com/navis-org/navis) by **navis-org** - Python tools for neuron morphology analysis, visualization, transformations, and data access.
- [fafbseg](https://github.com/navis-org/fafbseg-py) by **navis-org** - FlyWire/FAFB segmentation tools for meshes, skeletons, annotations, and connectivity queries, interoperable with NAVis.
- [navis-flybrains](https://github.com/navis-org/navis-flybrains) by **navis-org** - Template brains and transforms for mapping neurons between Drosophila datasets and coordinate spaces.
- [connectome-interpreter](https://github.com/YijieYin/connectome_interpreter) by **YijieYin** - Python library for effective connectivity, path finding, circuit manipulation, and differentiable models at whole-brain scale.
- [connectome data prep](https://github.com/YijieYin/connectome_data_prep) by **YijieYin** - Prepared connectivity matrices and reproducible preprocessing for MaleCNS, BANC, FlyWire, hemibrain, and other datasets.
- [cocoa](https://github.com/flyconnectome/cocoa) by **flyconnectome** - Python library for comparative connectomics, co-clustering, cell typing, and matching across FlyWire, hemibrain, MANC, and MaleCNS.
- [Connecto](https://github.com/schlegelp/connecto) by **schlegelp** - Unified Python interface that normalizes connectivity, metadata, and morphology queries across CAVE and neuPrint datasets.
- [DROCAT](https://github.com/Swida-Alba/Drosophila-cross-dataset-connectome-analysis) by **Swida-Alba** - Python and web toolkit for path finding, network visualization, morphology, and cross-dataset analysis across neuPrint, FAFB, and BANC.
- [BigClust 2](https://github.com/flyconnectome/bigclust2) by **flyconnectome** - Interactive application for exploring high-dimensional connectomic clusterings with linked 2D, 3D, connectivity, and annotation views.
- [neuVid](https://github.com/connectome-neuprint/neuVid) by **connectome-neuprint** - Generates anatomical Drosophila videos from high-level descriptions using neuPrint data and Blender or VVDViewer.
- [malecns](https://github.com/natverse/malecns) by **natverse** - R access to MaleCNS data with metadata and morphology conveniences.
- [coconatfly](https://github.com/natverse/coconatfly) by **natverse** - Comparative connectomics across fly datasets, including FlyWire, hemibrain, MANC, FANC, and MaleCNS.
- [fafbseg for R](https://github.com/natverse/fafbseg) by **natverse** - R tools for FlyWire/FAFB segmentation, meshes, annotations, and connectivity analysis.
- [neuprintr](https://github.com/natverse/neuprintr) by **natverse** - R client for neuPrint, designed to work with the wider natverse neuroanatomy ecosystem.
- [bancr](https://github.com/natverse/bancr) by **natverse** - R package for querying BANC metadata, connectivity, skeletons, and meshes.
- [neuprint-python](https://github.com/connectome-neuprint/neuprint-python) by **connectome-neuprint** - Python client for querying connectivity and metadata through neuPrint.
- [CAVEclient](https://github.com/CAVEconnectome/CAVEclient) by **CAVEconnectome** - Python client for the Connectome Annotation Versioning Engine, used to access versioned connectomic data and annotations.
- [FlyWire network analysis](https://github.com/murthylab/flywire-network-analysis) by **Murthy Lab** - Research scripts and notebooks for network statistics, motifs, connectivity, and graph structure.

## Tutorials and papers

- [Fly connectome data tutorial](https://github.com/sjcabs/fly_connectome_data_tutorial) - Workshop materials for loading, analyzing, and visualizing major fly connectome datasets using Python and R.
- [FlyWire data access](https://github.com/seung-lab/FlyConnectome) - Seung Lab tutorials for programmatic access to FlyWire data, meshes, and annotations.
- [Hemibrain examples](https://github.com/flyconnectome/2020hemibrain_examples) - Code examples accompanying Schlegel and Bates et al. for exploring cell types and circuits in the hemibrain dataset.
- [Neuronal wiring diagram of an adult brain](https://doi.org/10.1038/s41586-024-07558-y) - Dorkenwald et al., Nature (2024), the adult female brain connectome.
- [Whole-brain annotation and multi-connectome cell typing of Drosophila](https://doi.org/10.1038/s41586-024-07686-5) - Schlegel et al., Nature (2024), cell annotations and comparisons across connectomes.
- [Connectome-constrained networks predict neural activity across the fly visual system](https://www.nature.com/articles/s41586-024-07939-3) - Lappalainen et al., Nature (2024), the research behind flyvis.
- [Whole-body simulation of realistic fruit fly locomotion with deep reinforcement learning](https://www.nature.com/articles/s41586-025-09029-4) - The research accompanying flybody.

## Related lists

- [Awesome Fruit Fly Connectome](https://github.com/watthem/awesome-fruit-fly-connectome) - An earlier community list of datasets, tools, papers, and fly-connectome experiments.
- [Fly Connectomics tools](https://github.com/flyconnectome/tools) - Overview of R and Python neuroscience tools maintained by the Cambridge Fly Connectomics Group and Jefferis Lab.

## Contributing

Small projects are welcome. We prioritize a clear connection to fly connectomics, useful documentation, original creators, and accurate descriptions over star counts. Substantial ports belong here when their upstream origin is credited. Announcement-only projects must say that runnable code is pending.

Built a project that belongs here? Read [CONTRIBUTING.md](CONTRIBUTING.md), add your repository to the relevant section, and [open a pull request](https://github.com/cobanov/awesome-fly/pulls). You can also use the [project suggestion form](https://github.com/cobanov/awesome-fly/issues/new?template=add-project.yml) if you do not want to edit the list yourself. The list is maintained by [cobanov](https://github.com/cobanov), who also maintains [Fly Dino](https://github.com/cobanov/flyjump).

## License

[CC0 1.0 Universal](LICENSE). Linked projects retain their own licenses.
