# KAIST IE437 Final Project

## [Paper](https://arxiv.org/pdf/2310.07747.pdf) 

This repository contains the implementation and reproduction of experiments from the paper **[NeurIPS'2023] "Accountability in Offline Reinforcement Learning: Explaining Decisions with a Corpus of Examples"** by Hao Sun et al.

## Key Insight:
**_Test-time decisions made by an agent should have a decision basis in the training decision dataset. Using a latent space decomposition and similarity-based matching, decisions made by agents in offline reinforcement learning can be interpretable._**


### Requirement
```
gym==0.26.2
pytorch==2.1.0
shapely==2.0.2
scipy==1.11.3
medkit-learn==0.1.0
tqdm
```

### To Repruduce Results
The following code reproduces the results reported in the paper. 

1. To generate a batched dataset, run

```
python3 generate_data.py --env ENV_NAME
```

- Change the --inv_forv = 1.0 or -1.0 will generate an offline dataset for normal or reversed dynamics. (to manifest the multiple potential outcome settings/ POMDP setting)
- Change the --env = 'Pendulum-v1', 'LunarLanderContinuous-v2' to generate data for different tasks. The Pendulum-v1 dataset is provided in the dataset folder.


2. To reproduce our main results, run

- Pendulum-v1 experiments
```
python3 reproduce_pendulum-het.py --dsize 50000
```
- LunarLanderContinuous-v2 environment
```
python3 reproduce_lunar.py --dsize 50000
```


---
### BibTeX
```bibtex
@article{sun2023accountability,
  title={Accountability in Offline Reinforcement Learning: Explaining Decisions with a Corpus of Examples},
  author={Sun, Hao and H{\"u}y{\"u}k, Alihan and Jarrett, Daniel and van der Schaar, Mihaela},
  journal={arXiv preprint arXiv:2310.07747},
  year={2023}
}
