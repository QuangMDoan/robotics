# create new python virtual environment
python -m venv .env

# activate virtual environment
.env\Scripts\activate

# install numpy, matplotlib packages for this environment
pip install numpy
pip install matplotlib

# GitBash: Add .env folder to .gitignore file 
echo ".env/**" >> .gitignore