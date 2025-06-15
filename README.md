# 🌿 Photosynthesis Visualization

A compact, reproducible study that **visualises incoming solar radiation and predicts leaf-level net photosynthesis using the Farquhar-von Caemmerer-Berry (FvCB) model**.  

Two representative C₃ crops are analysed:

- **Tomato (*Solanum lycopersicum*)** – full FvCB parameterisation with temperature response  
- **Lettuce (*Lactuca sativa*)** – empirical light-response fitted to shade-grown plants  

The notebooks compare open-field vs. greenhouse conditions, explore seasonal trends for two climates:

- Aillas, France (≈ 45°N)
- Guadeloupe, France (≈ 16°N)

It also quantifies the impact of a **25% PV-greenhouse shade factor** on CO₂ assimilation.



## 🚀 Getting Started

```bash
# Clone and enter the project
git clone https://github.com/<your-org>/photosynthesis-viz.git
cd photosynthesis-viz

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install required packages
pip install -r requirements.txt
Launch JupyterLab and open:

notebooks/Am_Lecoufle_graphs.ipynb


```

The notebook is fully self-contained: it reads the CSVs, computes derived variables (PPFD, ΔT), runs FvCB simulations, and generates all visualisations and tables.

Link to a jupyter colab file with the runable code
https://colab.research.google.com/drive/15nj1Qc0cEmE5TSNOLaL9_iyo93QXr6AR?usp=sharing

## 🔍 Key Features
### Multi-season solar radiation parsing:

Converts PVGIS daily extracts (multi-row header) to long format.

### Photon flux conversion & greenhouse shading:

Converts GHI → PPFD using standard coefficients. Simulates 75% light transmission under PV panels.

### Biochemical photosynthesis modelling:

Temperature-adjusted FvCB function for tomato (fvbc_with_inputs)

Empirical rectangular hyperbola for lettuce (lettuce_an)

### Visual analytics:

Hourly and daily PPFD breakdowns

Net photosynthesis curves by crop, season, and geography

Monthly and yearly integrals adjusted for photoperiod
