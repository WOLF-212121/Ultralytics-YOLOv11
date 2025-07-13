🎯 Ultralytics-YOLOv11: Player Re-Identification in Sports Footage
📝 Task: Cross-Camera Player Mapping
Objective:
Given two clips of the same gameplay from different camera angles (broadcast.mp4 and tacticam.mp4),
map players to retain consistent player IDs across both feeds.

🚀 Tech Stack
Platform: Google Colab (GPU T4)
Libraries: Torch, Ultralytics
Modules: YOLO (Ultralytics)
Visualization: Matplotlib, matplotlib_venn
Data Manipulation: Pandas, Numpy

📂 Available Contents
Pre-trained YOLOv11 model: best.pt
Sample gameplay footage: broadcast.mp4 & tacticam.mp4

⚡ Workflow
1️⃣ Load Pre-Trained Model
Using Ultralytics YOLOv11 to load best.pt.

2️⃣ Run Tracking on Footage
Feed broadcast.mp4 and tacticam.mp4 into the loaded model using .track to track:
Players with unique player IDs, Ball, Referees.

3️⃣ Visualize Tracking
Generate image outputs visualizing tracked players with ID overlays for verification.

4️⃣ Player Presence Analysis
Using Venn diagrams (matplotlib_venn) to identify:
Players present in both videos, Players unique to each camera angle.

5️⃣ Data Extraction
Using Pandas and Numpy:
Extract player IDs, List players consistently detected across feeds, Filter and handle null or missing IDs from YOLO output tensors.

🛠️ Challenges Faced
✅ Tensor Output Parsing:
The model.track functionality outputs detections in tensor format requiring additional processing to extract player IDs accurately.
✅ Handling Null Player IDs:
Some YOLO boxes lack assigned player IDs; handled using condition checks and filters to ensure clean ID extraction.
✅ Performance Constraints:
Model inference on CPU is significantly slower compared to GPU acceleration.
For tracking tasks across multiple frames or extended footage, using a GPU is strongly recommended.


Content Link for Model and sample videos - https://drive.google.com/drive/folders/1rZqQOjXO1vqj-vxdEXDwkBea332u1Z85?usp=sharing

