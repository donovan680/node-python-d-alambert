# node-python-dalambert
A simple demo app which integrates node and python

Integrating Node and Python. 

3 quick ways to integrate Node and Python — useful if you want to leverage Python’s financial/mathematical capabilities, in conjunction with an existing Node application. This should be pretty straightforward as Node is at heart a simple I/O platform.
Our problem scope: we want to create a simple Express server with an endpoint that makes calls to a Python script, and returns the resulting output.

Setup.

Install Express:

npm install express — save
Create a simple express server — server.js:
var express = require(‘express’);
var app = express();
app.listen(3000, function () {
  console.log(‘server running on port 3000’);
})

We have an existing Python script that we want to call from our Node.js application — d_alembert.py is a simple simulation of the d’Alembert betting strategy for roulette. Details are not relevant for this post, but if you’re interested: d’Alembert increments the next bet size when you lose, and decrements with a win. This is a relatively ‘safe’ strategy, requiring a smaller bankroll. If the number of wins is the same as the number of losses, you will always be in profit by the number of bets. The script runs a set number of simulations, starting with a defined bet size and bankroll
