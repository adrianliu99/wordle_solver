# wordle_solver

A solver for [wordle](https://www.powerlanguage.co.uk/wordle/). Done by greedily choosing the word that maximazes the expected [information gain](https://en.wikipedia.org/wiki/Information_gain_in_decision_trees).

## Usage

Wordle gives feedback by marking letters green ,yellow or grey. Here they corresond to `*`, `?` and `~`. If your guess is colored grey, grey, yellow, green, grey then it would be represented as "\~\~\?\*\~"

Example assuming the correct word is "robot":

```

>>> solver = Info_Gain_Solver()
>>> solver.next_word()
"soare"
>>> solver.next_word("~*~?~", "soare")
"cyton" 
## If you use the word that was just suggested by the solver, you don't need to specify it again
>>> solver.next_word("~~?*~") 
"robot"
```

## Performace

Solves all 2315 [words](https://gist.github.com/cfreshman/a03ef2cba789d8cf00c08f767e0fad7b) (spoiler warning) in at most 6 attempts. Average number of attempts is 3.47.
