# Udacity Machine Learning Engineer Nanodegree

## Project: Deep RL Quadcopter Controller

#### Target :
Training an RL agent(quadcopter controller) to learn to fly & perform the defined tasks in direction to maximise reward.

#### Algorithm Class :
Deep Deterministic Policy Gradients (DDPG)

#### Problem  Type :
Continuous Control Task


#### Final Result :

I only tried using DDPG (Deep Deterministic Policy Gradients).


My final hyperparameter choices were:

- Replay memory batch size = 64
- Replay memory buffer size = 100000
- Gamma = 0.99
- Tau = 0.01


Neural Network architecture for Actor:

State pathway layers:

```
net = layers.Dense(units=200, activation='relu')(states)
net = layers.Dense(units=400, activation='relu')(net)
net = layers.Dense(units=200, activation='relu')(net)
```

Neural Network architecture for Critic:

State pathway layers:

```
net_states = layers.Dense(units=200, activation='relu')(states)
net_states = layers.BatchNormalization()(net_states)
net_states = layers.Activation('relu')(net_states)

net_states = layers.Dense(units=400, activation='relu')(net_states)
```

Action pathway layers:

```
net_actions = layers.Dense(units=200, activation='relu')(actions)
net_actions = layers.Dense(units=400, activation='relu')(net_actions)
```

- Final Reward-Episode Plot  :<br>
![Final Reward-Episode Plot](resources/reward_episode.png)


## Project Instructions

1. Clone the repository and navigate to the downloaded folder.

```
git clone https://github.com/udacity/RL-Quadcopter-2.git
cd RL-Quadcopter-2
```

2. Create and activate a new environment.

```
conda create -n quadcop python=3.6 matplotlib numpy pandas keras-gpu
source activate quadcop
```

3. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `quadcop` environment.
```
python -m ipykernel install --user --name quadcop --display-name "quadcop"
```

4. Open the notebook.
```
jupyter notebook Quadcopter_Project.ipynb
```

5. Before running code, change the kernel to match the `quadcop` environment by using the drop-down menu (**Kernel > Change kernel > quadcop**). Then, follow the instructions in the notebook.

6. You will likely need to install more pip packages to complete this project.  Please curate the list of packages needed to run your project in the `requirements.txt` file in the repository.
