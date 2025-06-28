# Fork of Werewolf The Social Deduction Game
This is fork of werewolf arena with local ollama model options (https://github.com/google/werewolf_arena/tree/main/werewolf)
This repository provides code for [Werewolf Arena](https://arxiv.org/abs/2407.13943) - a framework for evaluating the social reasoning skills of large language models (LLMs) through the game of Werewolf.

## Set up the environment
First, install ollama

### Create a Python Virtual Environment
You only need to do this once.
```
python3 -m venv ./venv
```

### Activate the Virtual Environment
```
source ./venv/bin/activate
```

### Install Dependencies
```
pip install ollama
pip install -r requirements.txt
ollama run phi4
/exit
ollama stop phi4
```

## Run a single game

fitst, turn off ollama and run
```ollama serve```
then on other cmd
```python3 main.py --run --v_models=phi4 --w_models=phi4```


## Run multiple games

`python3 main.py --eval --num_games=5 --v_models=phi4 --w_models=phi4`

## Bulk resume failed games

`python3 main.py --resume`

The games to be resumed are currently hardcoded in `runner.py`, and
is defined as a list of directories where their states are saved.

## Launch the Interactive Viewer
![alt text](viewer.png)

Once a game is completed, you can use the interactive viewer to explore the gamelog. You can see players' private reasoning, bids, votes and prompts. 

 - `npm i`
 - `npm run start`
 - Open the browser, e.g. `http://localhost:8080/?session_id=session_20240610_084702`
