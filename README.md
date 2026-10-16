## Wongel Nadew — Research Portfolio

Personal portfolio of Wongel Nadew, PhD candidate at Utah State University working on computational mechanics and scientific machine learning.

**Live site:** https://wongel-yilma.github.io

### Contents

**Publication**
- [Learning the governing partial differential equation of solid diffusion from atomistic simulations](https://wongel-yilma.github.io/projects/md-diffusion), *Proceedings of the Royal Society A* (2025). [DOI: 10.1098/rspa.2025.0383](https://doi.org/10.1098/rspa.2025.0383)

**Projects**
- [Physics-Informed Neural Networks for PDE Discovery (PINN-SR)](https://wongel-yilma.github.io/projects/pinn-sr): [code](https://github.com/Wongel-Yilma/PINN-SR)
- [Grain Growth Simulation in Metal Additive Manufacturing](https://wongel-yilma.github.io/projects/am-grain-growth): [code](https://github.com/Wongel-Yilma/AM_microstructure_simulations)
- [Parallel 2D Ising Model on CPUs and GPUs](https://wongel-yilma.github.io/projects/ising)
- [Physics-Informed Neural Networks: A Brief Review and Examples](https://wongel-yilma.github.io/projects/pinn-review)
- Entropic Regression in Python: [code](https://github.com/Wongel-Yilma/Entropic-Regression)

### Repository layout

| Path | Contents |
|------|----------|
| `index.md` | Home page: publications and project list |
| `projects/` | One page per project |
| `images/projects/<project>/` | Figures for each project page |
| `pdf/` | Project reports |
| `_config.yml` | Site title, profile photo and sidebar text |
| `_layouts/default.html` | Page layout |

### Adding a project

1. Put the figures in `images/projects/<project-name>/`, and any report in `pdf/`.
2. Create `projects/<project-name>.md` with this front matter:
   ```markdown
   ---
   layout: default
   title: Project Title
   ---
   ```
3. Add an entry to `index.md` that links to `/projects/<project-name>`.

GitHub Pages rebuilds the site automatically after each push to `main`.

### Credits

Built with the [Minimal](https://github.com/pages-themes/minimal) Jekyll theme (CC0 1.0), starting from the [quick-portfolio](https://github.com/evanca/quick-portfolio) template by evanca.
