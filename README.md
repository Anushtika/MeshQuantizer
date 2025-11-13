🌀 MixAR – 3D Mesh Loading and Visualization Toolkit
📘 Overview

MixAR is a Python-based toolkit for loading, inspecting, and visualizing 3D mesh files (specifically .obj format).
It provides an educational demonstration of how 3D geometry data is parsed, represented, and rendered using libraries like Trimesh, Open3D, and Matplotlib.
This project aims to make 3D mesh processing more transparent and modular, allowing you to switch between libraries or even handle meshes manually.

✨ Features

📂 Load .obj mesh files using Trimesh or a custom parser.

🧩 Extract vertices and faces arrays for numerical manipulation.

🔍 Visualize 3D models interactively with Open3D or statically using Matplotlib.

🧮 Perform basic mesh inspection and validation (geometry, face connectivity, vertex count).

💡 Works even if external dependencies like trimesh or open3d are unavailable (fallback mode).

🧰 Tech Stack
Category	Tools / Libraries
Language	Python 3.8+
Core Libraries	numpy, matplotlib, pathlib
3D Processing	trimesh, open3d
Visualization	matplotlib, open3d.visualization

🚀 Usage
1️⃣ Load and Inspect Mesh
from mixar import load_mesh_with_trimesh, load_mesh_basic

vertices, faces = load_mesh_with_trimesh("models/example.obj")
print("Vertices:", vertices.shape)
print("Faces:", faces.shape)

2️⃣ Visualize with Open3D
import open3d as o3d

mesh = o3d.geometry.TriangleMesh()
mesh.vertices = o3d.utility.Vector3dVector(vertices)
mesh.triangles = o3d.utility.Vector3iVector(faces)
o3d.visualization.draw_geometries([mesh])

3️⃣ Or visualize using Matplotlib (fallback)
from mpl_toolkits.mplot3d.art3d import Poly3DCollection
import matplotlib.pyplot as plt

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot_trisurf(vertices[:,0], vertices[:,1], vertices[:,2], triangles=faces)
plt.show()

🧩 Project Structure
mixar/
├── mixar.ipynb                # Main notebook
├── models/                    # Folder for sample .obj meshes
├── requirements.txt           # Dependencies
├── README.md                  # Project documentation

📈 Example Output

✅ Successfully loads .obj meshes

✅ Displays 3D visualizations (interactive if Open3D available)

✅ Handles missing dependencies gracefully

(Insert screenshots or GIFs of your 3D visualizations here!)

📚 Learning Outcomes

Understanding the OBJ file format

Parsing and reconstructing 3D meshes from raw text

Using Trimesh and Open3D for geometric processing

Visualizing meshes using Python’s plotting ecosystem

B.Tech CSE (AI & ML), SRM Institute of Science and Technology
💡 Passionate about AI, 3D vision, and intelligent systems

🧾 License

This project is released under the MIT License — feel free to use, modify, and distribute it.
