This repo is modeled over [Quan Vuong's pytorch implementation](https://github.com/quanvuong/handful-of-trials-pytorch) of the algorithm described in [Deep Reinforcement Learning in a Handful of Trials using Probabilistic Dynamics Models](https://arxiv.org/abs/1805.12114).

A work in progress!

## Requirements

1. The requirements in the original [TF implementation](https://github.com/kchua/handful-of-trials)
2. Pytorch 1.0.0

For specific requirements, please take a look at the pip dependency file `requirements.txt` and conda dependency file `environments.yml`.

## Running Experiments

Experiments for a particular environment can be run using:

```
python mbexp.py
    -env    ENV       (required) The name of the environment. Select from
                                 [cartpole, reacher, pusher, halfcheetah].
```

Results will be saved in `<logdir>/<date+time of experiment start>/`.
Trial data will be contained in `logs.mat`, with the following contents:

```
{
    "observations": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, obs_dim]
    "actions": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, ac_dim]
    "rewards": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, 1]
    "returns": Numpy array of shape [1, num_train_iters * neval]
}
```

To visualize the result, please take a look at `plotter.ipynb`

## Acknowledgement

Huge thank to the authors of the paper for open-sourcing their [code](https://github.com/kchua/handful-of-trials/). Most of this repo is taken from the official TF implementation.
