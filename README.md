# 🚦 ETCS Level 3 Requirement Analysis Toolkit

This repository provides a modular pipeline for extracting, tracking, and visualizing the evolution of ETCS Level 3 requirements across successive X2Rail specifications.
## ⚙️ Setup 

1. Clone the repository and install dependencies:
   ```bash
   git clone https://github.com/Aroua-Ben-Daya/etcs-requirement-evolution.git
   cd etcs-requirement-evolution

2. Add your specification documents (PDFs) to the data/ folder and rename them as:
data/
├── X2R1.pdf
├── X2R3.pdf
└── X2R5.pdf

3. Run the extraction script to parse requirements from one version at a time:
   ```bash
python AutoReqExtract.py

💡In the script, adjust the line pdf_path = "data/X2R3.pdf" to point to the version you want to process.

4.Once you have the .xlsx files for all versions, run:
python RequirementEvolutionTracking.py

This will produce a version-aligned Excel table in output/RequirementEvolutionOutput.xlsx.

🌳 Visualization
To view the interactive mind map:

1.Open a terminal in the repository root and launch a local server:
python -m http.server 8000
2.In your browser, navigate to:
http://localhost:8000/visualization/requirement_traceability_map.html

The visualization reads the requirement_traceability_tree_enhanced.json file and allows zooming, hovering, and topic-aware coloring for better traceability.

📘 Scripts Overview

**AutoReqExtract.py**  
Parses structured requirements from each X2Rail specification PDF  

Detects:  
- Topic headers  
- Requirement IDs (e.g., REQ-...)  
- Traceability references  

Outputs: Excel file (`output/X2R*.xlsx`)  

**RequirementEvolutionTracking.py**  
Aligns and compares requirements across X2R1 → X2R3 → X2R5  

Detects:  
- Topic/description changes  
- Requirement reuse, deletion, or addition  

Outputs: RequirementEvolutionOutput.xlsx with status annotations:  
- 🆕 New  
- ✅ Unchanged  
- 📝 Modified  
- ❌ Absent  

📎 Citation  
If you find this pipeline or visualization useful in your research or projects, please acknowledge the original author:

**Aroua Ben Daya**, *ETCS Level 3 Requirement Evolution Pipeline*, 2025.  
GitHub: [github.com/Aroua-Ben-Daya](https://github.com/Aroua-Ben-Daya)

Feel free to contact me for collaborations or extensions.

📄 License
This project is released under the MIT License.

