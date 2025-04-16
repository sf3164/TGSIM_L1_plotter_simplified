# Vehicle Trajectory Visualization Tool simplified version (for TGSIM I294 L1 Stationary Data)

This is a simplified python GUI-based tool for plotting **vehicle trajectories** using TGSIM I294 L1 data. Designed for fast and direct use, this version allows users to manually input multiple vehicle IDs and generate interactive Plotly visualizations that include detailed lane and trajectory data.

## Features

- Select a **run index**.
- Manually input **comma-separated vehicle IDs** (e.g., `101, 205, 309`).
- Error handling for:
  - Non-numeric inputs
  - Vehicle IDs not found in selected run
- Generates interactive Plotly plots with hover info:
  - ID
  - Time
  - Lane
  - Speed
  - Acceleration
- Displays all **lane centerlines** with labels for road context.

## Example Output

The tool produces an HTML file (`L1_Simplified_Plot.html`) displaying the interactive plot.
<img width="825" alt="Screenshot 2025-04-16 at 5 15 51 PM" src="https://github.com/user-attachments/assets/1c6f9016-422f-4eb9-8318-9a4e24ba9ae4" />

## File Structure

```bash
.
├── TGSIM_L1.csv            # Main trajectory dataset
├── Centerline/
│   ├── I-294-L1-Run_1-geometry-with-ramps.csv
│   ├── I-294-L1-Run_2-geometry-with-ramps.csv
│   └── ...                            # One file per run index
├── plotter.py           # Python file with Tkinter GUI and plotting code
└── README.md
```

## Dependencies

- `pandas`
- `plotly`
- `matplotlib`
- `tkinter` (built-in in most Python distributions)

You can install the required packages with:

```bash
pip install pandas plotly matplotlib
```

> `tkinter` is usually included with standard Python installations. If you're using Linux and don't have it installed, try:
>
> ```bash
> sudo apt-get install python3-tk
> ```

## How to Use

1. Download the TGSIM I294 L1 main dataset and the centerline files from the following website:
https://data.transportation.gov/Automobiles/Third-Generation-Simulation-Data-TGSIM-I-294-L1-Tr/7zjf-a4zf/about_data
2. Rename the main dataset to TGSIM_L1.csv and move it to the same directory as the `plotter.py` script.
3. In the same directory as `plotter.py`, create a new folder named `Centerline`, and move all the centerline files into this folder.
4. Launch the Python to run `plotter.py` and run all cells.
5. A GUI window will appear.
6. Select a **run index** to load data.
7. Enter one or more vehicle IDs (comma-separated).
8. Click **Plot** to generate the interactive plot.
   

The plot will open in a browser window and also be saved as `L1_Simplified_Plot.html`.


## Notes

- Centerline CSVs must be named in the format:  
  `I-294-L1-Run_<run_index>-geometry-with-ramps.csv`
- These files must be placed in the `Centerline/` directory relative to the notebook.
- The code currently writes to a fixed output file (`L1_Simplified_plot.html`) — feel free to modify this for custom output names.

## License

This project is open-source

## Author

David Feng  
Ph.D. Student, UVA Civil & Environmental Engineering Dept.  <br />
Graduate Research Assistant, Turner-Fairbank Highway Research Center
