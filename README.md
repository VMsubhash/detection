# detection flow
AI that detects the no. of plastic in an drone image of river

![screenshot of Irwin report](images/one.png)

## Dependencies
Compatible with Python 3.x

### Python Libraries
```sh
pip3 install pymongo python-chess numpy requests
```
- **tensorflow** : [tensorflow installation guide](https://www.tensorflow.org/install)

## About
Irwin (named after Steve Irwin, the Crocodile Hunter) started as the name of the server that the original
cheatnet ran on (now deprecated). This is the successor to cheatnet.

Similar to cheatnet, it works on a similar concept of analysing the available PVs of a game to determine
the odds of cheating occurring.

This bot makes improvements over cheatnet by taking a dramatically more modular approach to software design.
`modules/core` contains most of the generic datatypes, BSON serialisation handlers and database interface
layers. It is also significantly faster due to a simplified approach to using stockfish analysis.

`modules/irwin` contains the brains of irwin, this is where the tensorflow learning and application takes place.

Irwin has been designed so that `modules/irwin` can be replaced with other approaches to player assessment.

`Env.py` contains all of the tools to interact with lichess, irwin, and the database handlers.

`main.py` covers accessing the lichess API (`modules/Api.py`) via Env to get player data; pulling records from mongodb,
analysing games using stockfish, assessing those games using tensorflow and then posting the final assessments.
