cd ci-cd-project
python -m venv venv
conda deactivate
source venv/bin/activate
pip install -r requirements.txt

PYTHONPATH=$(pwd) pytest
