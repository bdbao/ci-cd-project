cd ci-cd-project
python -m venv venv
conda deactivate
source venv/bin/activate
pip install -r requirements.txt

PYTHONPATH=$(pwd) pytest


gh auth login
gh repo create ci-cd-project --public
git init
git add .
git commit -m "init: Initial commit"
git remote add origin https://github.com/bdbao/ci-cd-project.git
git branch -M main
git push -u origin main