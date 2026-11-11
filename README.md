git --version

---for checking UV inthis sytem--
uv --system

if UV is not in your sytemthen run below command

powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

--check which uv version install in this sytem--
uv --version

mkdir meridian-ai
cd meridian-ai
uv init --python 3.12


git clone https://github.com/mayank953/meridian-ai-learner.git ../meridian-reference
cp ../meridian-reference/requirements.txt .
cp ../meridian-reference/requirements-dev.txt .
cp ../meridian-reference/.env.example .
cp -R ../meridian-reference/sample_docs .
rm main.py

uv add -r requirements.txt

uv run python -c "import sys, fastapi, langchain; print(sys.version.split()[0], fastapi.__version__, langchain.__version__)"

this for mac
mkdir -p backend/{api,rag,agent,config,logger,exceptions,tests} touch backend/{api,rag,agent,config,logger,exceptions}/__init__.py

belwo one for windows

$folders = @("api", "rag", "agent", "config", "logger", "exceptions", "tests")

foreach ($folder in $folders) {
    New-Item -ItemType Directory -Force -Path "backend/$folder"
    New-Item -ItemType File -Force -Path "backend/$folder/__init__.py"
}


if you want to add and file in gitignore then run below command
Add-Content -Path .gitignore -Value "logs/"
