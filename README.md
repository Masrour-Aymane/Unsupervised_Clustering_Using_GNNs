# Graph Clustering

This notebook reproduces experiments from the paper *"Graph Clustering with Graph Neural Networks"* using Deep Modularity Networks (DMoN). It includes synthetic data generation (ADC-SBM model) and real-world dataset analysis (Cora, Citeseer, Pubmed) for reproduction of the results.

---

## **Prerequisites** 🛠️

### **1. Dependencies**
- Python 3.7+
- Jupyter Notebook
- Libraries:
  ```bash
  numpy matplotlib argparse pathlib torch torch_geometric
   ```

  - **graph-tool** *(Critical dependency for new synthetic data generation)*:
  
    - **Windows Note**: `graph-tool` is not natively supported on Windows. Use one of these options:
    
      1. **WSL (Windows Subsystem for Linux)**: Install Ubuntu and use  
         ```bash
         apt-get install python3-graph-tool
         ```
    
      2. **Docker** *(considered solution in our case)*: Use a pre-built Docker image with `graph-tool` (e.g.  
         ```bash
         docker pull tiagopeixoto/graph-tool
         ```
## Notebook Execution ▶️

### Key Sections

1. **Synthetic Data Generation (ADC-SBM Model)**:
   - Generates synthetic graphs and node features.
   - Uses `graph-tool` for graph sampling (ensure it works in your environment).
   - Adjust `GenerationParameters` in the notebook for custom datasets.

2. **Real-World Data Processing**:
   - Modify paths to point to your real datasets (Cora, Citeseer, Pubmed).

3. **Visualization**:
   - Calls `visualize_covariance_comparison()` for adjacency/covariance plots.

---

### Windows-Specific Notes 🔧

- **graph-tool Issues**: If using WSL/Docker, run the notebook from a Linux terminal.

- **Path Handling**: Use `Path` from `pathlib` (already in code) for cross-platform paths.

- **Command-Line Args**: Replace `argparse` with hardcoded parameters in the notebook  
  (Jupyter doesn’t support `argparse` natively).

## Project Structure 📂
```
├── DMoN_analysis.ipynb # Main notebook 
├── adc_sbm_datasets/ # Auto-generated synthetic datasets 
├── real_data/ # Place real datasets here (Cora, Citeseer, Pubmed) 
└── figures/ # Output plots (e.g., covariance.png)
```
