:: --- Install Python dependencies ---
python -m venv venv
venv\Scripts\activate

pip install --upgrade pip
pip install torch torchvision opencv-python numpy requests matplotlib

:: --- Download llama.cpp ---
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp

:: --- Download GGUF model (phi-2) ---
:: Place the model manually or download using PowerShell/curl/wget. Example:
mkdir models
curl -L -o models/phi-2.Q4_K_M.gguf https://huggingface.co/TheBloke/phi-2-GGUF/resolve/main/phi-2.Q4_K_M.gguf

:: --- Install build tools manually beforehand if not available ---
:: Assumes you already downloaded MinGW-w64 and curl binaries for Windows

:: --- Configure and build llama.cpp with curl support (REPLACE PATHS AS NEEDED) ---
cmake -B build -G Ninja -DCMAKE_BUILD_TYPE=Release ^
  -DCURL_LIBRARY="DCURL libcurl.a location" ^
  -DCURL_INCLUDE_DIR="DCURL include folder location"

cmake --build build
