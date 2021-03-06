### Code for the paper "Benchmarking Classic and Learned Navigation in Complex 3D Environments"

Project website: https://sites.google.com/view/classic-vs-learned-navigation

Video: https://www.youtube.com/watch?v=b1S5ZbOAchc

Paper: https://arxiv.org/abs/1901.10915

If you use this code or the provided environments in your research, please cite the following:

    @ARTICLE{Navigation2019,
           author = {{Mishkin}, Dmytro and {Dosovitskiy}, Alexey and {Koltun}, Vladlen},
            title = "{Benchmarking Classic and Learned Navigation in Complex 3D Environments}",
             year = 2019,
            month = Jan,
    archivePrefix = {arXiv},
           eprint = {1901.10915},
    }


    
## Dependencies:

- minos
- numpy
- pytorch
- ORBSLAM2


## Tested with: 
- Ubuntu 16.04
- python 3.6
- pytorch 0.4, 1.0


## Benchmark


- Install Anaconda https://www.anaconda.com/download/#linux

- Install dependencies via ./install_minos_and_deps.sh.  It should install everything except the datasets.
        
- Obtain mp3d and suncg datasets as described here in (1)  https://github.com/minosworld/minos/blob/master/README.md#installing 

- For benchmark handcrafted agents, run following

        source activate NavigationBenchmarkMinos
        export CUDA_VISIBLE_DEVICES=0
        python -utt benchmark_all_handcrafted_agents.py
        
You may want to comment/uncomment needed agents and/or environments if need to reproduce only part of them. 
Agents contain random parts: RANSAC in ORBSLAM and 10% random actions in all agents. Nevertheless, results should be the same if run on the same PC. From machine to machine, results may differ (slightly)

You may also want to turn on recording of videos (RGB, depth, GT map, map, beliefs) by setting VIDEO=True in  [benchmark_all_handcrafted_agents.py](benchmark_all_handcrafted_agents.py). 

Simple example of working with agents is shown in [example](examples/BasicFunctionality.ipynb). 
        
## Training 

Training and pre-trained weights for the learned agents are coming soon.

