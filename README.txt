AI RECIPE GENERATOR - README

PREREQUISITES

1. System Requirements:
   - Minimum: Intel i5 processor, 8GB RAM
   - Recommended: Dedicated GPU (for YOLO models)
   - OS: Windows 10/11 or Linux

2. Python Environment:
   - Python 3.10+
   - pip 23.0+

3. Core Dependencies:
   - torch>=2.0
   - ultralytics (for YOLOv8)
   - openai>=1.0 (for GPT implementation)
   - llama-cpp-python (for local LLaMA)
   - ipywidgets (for Jupyter UI)
   - pillow (image processing)

4. Model Files:
   - YOLOv8 models (download automatically)
   - LLaMA phi-2 GGUF (4-bit quantized)
     Place in: ./Models/phi-2.Q4_K_M.gguf

5. API Keys (for cloud features):
   - OpenAI API key in environment:
     export OPENAI_API_KEY="sk-..."

INSTALLATION

1. Create virtual environment:
   python -m venv recipe_env
   source recipe_env/bin/activate  # Linux/Mac
   recipe_env\Scripts\activate    # Windows

2. Install packages:
   pip install -r requirements.txt

3. Download models:
   python download_models.py

RUNNING THE SYSTEM

1. Jupyter Notebook:
   jupyter notebook RecipeGenerator.ipynb

2. Command Line (basic mode):
   python main.py --ingredients "chicken,potatoes" --type "main course"

3. Options:
   --offline       Use local LLaMA only
   --model [n/s/m/l/x]  YOLO model size
   --images [path]  Ingredient images folder

FOLDER STRUCTURE

./Available_Ingredients/  # Put ingredient images here
./Models/                 # AI model files