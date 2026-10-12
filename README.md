# Stochastic Processes Lab

Short simulation notebooks that check the main results from my graduate course on stochastic processes and queueing systems (IE 8532, University of Minnesota). Each notebook takes one topic from the course, states the theory, simulates the process in Python, and compares what the simulation gives with what the theory predicts.

I work in transportation research, so over time the examples will lean toward that setting, such as bus headways, vehicle arrivals, and queues at charging stations or facilities.

## Notebooks

| # | Topic | Status |
|---|-------|--------|
| 1 | [Poisson processes](01_poisson_processes.ipynb) | In progress |
| 2 | [Train dispatch, waiting cost and the best departure interval](02_train_dispatch.ipynb) | In progress |
| 3 | Interarrival times, splitting, and superposition | Planned |
| 4 | Order statistics property and compound Poisson processes | Planned |
| 5 | Non-homogeneous Poisson processes | Planned |
| 6 | Renewal theory and the inspection paradox | Planned |
| 7 | Discrete-time Markov chains | Planned |
| 8 | Continuous-time Markov chains and M/M/s queues | Planned |

[![Open notebook 1 in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NastaranTork/stochastic-processes-lab/blob/main/01_poisson_processes.ipynb)
[![Open notebook 2 in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NastaranTork/stochastic-processes-lab/blob/main/02_train_dispatch.ipynb)

## What is in notebook 1 so far

I build a Poisson process from iid exponential gaps between arrivals, then test whether the resulting counts behave the way the definition says they should.

- The count in a window follows a Poisson distribution, with mean and variance both equal to the rate times the window length.
- Windows of the same length have the same distribution wherever they sit, which is the stationary increments property.
- Counts in windows that do not overlap are independent, checked with a correlation and with a direct comparison of joint and product probabilities.

Each check states a prediction first, shows the simulated result next to the theory, and notes how much of any difference is explained by sampling error.

## What is in notebook 2 so far

A train leaves a station every t minutes, and passengers arrive as a Poisson process. Leaving often costs money in departures, and leaving rarely makes passengers wait. The notebook finds the best interval.

- Simulation confirms that the expected total waiting time in one cycle is λt²/2, with the match checked against standard errors.
- A cost per minute combines a fixed departure cost and a waiting cost per passenger-minute.
- A simulation over many intervals shows the cost per minute falls, bottoms out, and then rises, so there is a best interval.
- The simulated best interval is checked against the exact answer from calculus.

## How I work through each topic

1. Write the theoretical result and my prediction before running any code.
2. Simulate the process with a fixed random seed so the numbers can be reproduced.
3. Compare simulation and theory with numbers and a plot.
4. Write down what the evidence does and does not show.

## Running the notebooks

Open a notebook with the Colab badge above, or install the packages and run Jupyter locally.

```
pip install numpy scipy matplotlib jupyter
jupyter lab
```

## Source

The theory follows lecture notes from IE 8532. The code and the written conclusions are my own.
