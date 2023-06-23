# MACHINE LEARNING COURSE DESIGN

## Reinforcement Learning

In reinforcement learning, the agent aims to maixmize its cumulative reward:



max∑𝑡=1𝑇𝔼𝑎𝑡∼𝜋(𝑠𝑡),𝑠𝑡+1∼𝑝(𝑠𝑡+1∣𝑠𝑡,𝑎𝑡),𝑠𝑡∼𝑝(𝑠)[𝛾𝑡−1𝑟(𝑠𝑡,𝑎𝑡)].



From the perspective of Bellman equation, the caculation of cumulative reward can be also formulated as:



𝑉(𝑠𝑡)=𝔼𝑎∼𝜋(𝑠𝑡)[𝑟(𝑠𝑡,𝑎𝑡)+𝛾𝑉(𝑠𝑡+1)].



## Policy Iteration Learning

Once a policy, 𝜋, has been improved using **𝑣**𝜋 to yield a better policy, 𝜋′, we can then compute 𝑣𝜋′ and improve it again to yield and even better 𝜋″. We can thus obtain a sequence of monotonically improving policies and value functions:

𝜋0⟶E𝑣𝜋0⟶I𝜋1⟶E⋯⟶I𝜋⋆⟶E𝑣⋆,



where ⟶E⟶E denotes a policy *evaluation*, and ⟶I⟶I denotes a policy improvement. This way of finding an optimal policy is called *policy iteration*.

### Pesudo of Policy Iteration Learning

1. **Initialization**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/a13def5f-00eb-4ea7-80de-2e3918d79fd4)

2. **Policy Evaluation**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/32142b42-9250-4a17-9e03-5b761d34a574)

3. **Policy Improvement**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/f5414b7e-cf5c-4392-b99c-5e6fdae63c83)


## Reinforcement Learning

In reinforcement learning, the agent aims to maixmize its cumulative reward:

![image](https://github.com/pym96/Machine_course_design/assets/105438207/114ab667-ade0-449a-a177-7bae612e152a)


From the perspective of Bellman equation, the caculation of cumulative reward can be also formulated as:

![image](https://github.com/pym96/Machine_course_design/assets/105438207/6e082419-a3fb-48de-96a5-0b158f34f37c)


## Policy Iteration Learning

Once a policy, $\pi$, has been improved using $v_{\pi}$ to yield a better policy, $\pi'$, we can then compute $v_{\pi'}$ and improve it again to yield and even better $\pi''$. We can thus obtain a sequence of monotonically improving policies and value functions:

$$
\pi_0 \stackrel{\text{E}}{\longrightarrow} v_{\pi_0} \stackrel{\text{I}}{\longrightarrow} \pi_1 \stackrel{\text{E}}{\longrightarrow} \dots \stackrel{\text{I}}{\longrightarrow}\pi_{\star}\stackrel{\text{E}}{\longrightarrow}v_{\star},
$$

where $\stackrel{\text{E}}{\longrightarrow}$ denotes a policy *evaluation*, and $\stackrel{\text{I}}{\longrightarrow}$ denotes a policy improvement. This way of finding an optimal policy is called *policy iteration*.

### Pesudo of Policy Iteration Learning

1. **Initialization**

    $V(s) \in \mathbb{R}$ and $\pi(s) \in \mathcal{A}(s)$ arbitrarily for all $s \in \mathcal{S}$

2. **Policy Evaluation**

    Loop:

    > $\Delta \leftarrow 0$  
    > Loop for each $s \in \mathcal{S}$:  
    > > $v \leftarrow V(S)$  
    > > $V(s) \leftarrow \sum_{s',r}p(s', r | s, \pi(s))[r + \gamma V(s')]$  
    > > $\Delta \leftarrow \max(\Delta, |v-V(s)|)$
    
    until $\Delta < \theta$ (a small positive number determining the accuracy of estimation)

3. **Policy Improvement**  

    policy-stable $\leftarrow$ true  
    For each $s \in \mathcal{S}$:
    
    > *old-action* $\leftarrow \pi(s)$  
    > $\pi(s) \leftarrow \arg \max_a\sum_{s', r}p(s', r | s, a)[r + \gamma V(s')]$  
    > If *old-action* $\ne \pi(s)$, then *policy-stable* $\leftarrow$ *false*  
    
    If *policy-stable*, then stop and return $V \sim v_{\star}$ and $\pi \sim \pi_{\star}$; else go to 2

## Reinforcement Learning

In reinforcement learning, the agent aims to maixmize its cumulative reward:

$$
\max \sum_{t=1}^T \mathbb{E}_{a_t \sim \pi(s_t), s_{t+1} \sim p(s_{t+1} \mid s_t, a_t), s_t \sim p(s)}[ \gamma^{t-1} r(s_t,a_t)].
$$

From the perspective of Bellman equation, the caculation of cumulative reward can be also formulated as:

$$
V(s_t) = \mathbb{E}_{a \sim \pi(s_t)}[r(s_t,a_t) + \gamma V(s_{t+1})].
$$

## Policy Iteration Learning

Once a policy, $\pi$, has been improved using $v_{\pi}$ to yield a better policy, $\pi'$, we can then compute $v_{\pi'}$ and improve it again to yield and even better $\pi''$. We can thus obtain a sequence of monotonically improving policies and value functions:

$$
\pi_0 \stackrel{\text{E}}{\longrightarrow} v_{\pi_0} \stackrel{\text{I}}{\longrightarrow} \pi_1 \stackrel{\text{E}}{\longrightarrow} \dots \stackrel{\text{I}}{\longrightarrow}\pi_{\star}\stackrel{\text{E}}{\longrightarrow}v_{\star},
$$

where $\stackrel{\text{E}}{\longrightarrow}$ denotes a policy *evaluation*, and $\stackrel{\text{I}}{\longrightarrow}$ denotes a policy improvement. This way of finding an optimal policy is called *policy iteration*.

### Pesudo of Policy Iteration Learning

1. **Initialization**

    $V(s) \in \mathbb{R}$ and $\pi(s) \in \mathcal{A}(s)$ arbitrarily for all $s \in \mathcal{S}$

2. **Policy Evaluation**

    Loop:

    > $\Delta \leftarrow 0$  
    > Loop for each $s \in \mathcal{S}$:  
    > > $v \leftarrow V(S)$  
    > > $V(s) \leftarrow \sum_{s',r}p(s', r | s, \pi(s))[r + \gamma V(s')]$  
    > > $\Delta \leftarrow \max(\Delta, |v-V(s)|)$
    
    until $\Delta < \theta$ (a small positive number determining the accuracy of estimation)

3. **Policy Improvement**  

    policy-stable $\leftarrow$ true  
    For each $s \in \mathcal{S}$:
    
    > *old-action* $\leftarrow \pi(s)$  
    > $\pi(s) \leftarrow \arg \max_a\sum_{s', r}p(s', r | s, a)[r + \gamma V(s')]$  
    > If *old-action* $\ne \pi(s)$, then *policy-stable* $\leftarrow$ *false*  
    
    If *policy-stable*, then stop and return $V \sim v_{\star}$ and $\pi \sim \pi_{\star}$; else go to 2

## Reinforcement Learning

In reinforcement learning, the agent aims to maixmize its cumulative reward:

$$
\max \sum_{t=1}^T \mathbb{E}_{a_t \sim \pi(s_t), s_{t+1} \sim p(s_{t+1} \mid s_t, a_t), s_t \sim p(s)}[ \gamma^{t-1} r(s_t,a_t)].
$$

From the perspective of Bellman equation, the caculation of cumulative reward can be also formulated as:

$$
V(s_t) = \mathbb{E}_{a \sim \pi(s_t)}[r(s_t,a_t) + \gamma V(s_{t+1})].
$$

## Policy Iteration Learning

Once a policy, $\pi$, has been improved using $v_{\pi}$ to yield a better policy, $\pi'$, we can then compute $v_{\pi'}$ and improve it again to yield and even better $\pi''$. We can thus obtain a sequence of monotonically improving policies and value functions:

$$
\pi_0 \stackrel{\text{E}}{\longrightarrow} v_{\pi_0} \stackrel{\text{I}}{\longrightarrow} \pi_1 \stackrel{\text{E}}{\longrightarrow} \dots \stackrel{\text{I}}{\longrightarrow}\pi_{\star}\stackrel{\text{E}}{\longrightarrow}v_{\star},
$$

where $\stackrel{\text{E}}{\longrightarrow}$ denotes a policy *evaluation*, and $\stackrel{\text{I}}{\longrightarrow}$ denotes a policy improvement. This way of finding an optimal policy is called *policy iteration*.

### Pesudo of Policy Iteration Learning

1. **Initialization**

    $V(s) \in \mathbb{R}$ and $\pi(s) \in \mathcal{A}(s)$ arbitrarily for all $s \in \mathcal{S}$

2. **Policy Evaluation**

    Loop:

    > $\Delta \leftarrow 0$  
    > Loop for each $s \in \mathcal{S}$:  
    >
    > > $v \leftarrow V(S)$  
    > > $V(s) \leftarrow \sum_{s',r}p(s', r | s, \pi(s))[r + \gamma V(s')]$  
    > > $\Delta \leftarrow \max(\Delta, |v-V(s)|)$

    until $\Delta < \theta$ (a small positive number determining the accuracy of estimation)

3. **Policy Improvement**  

    policy-stable $\leftarrow$ true  
    For each $s \in \mathcal{S}$:
    
    > *old-action* $\leftarrow \pi(s)$  
    > $\pi(s) \leftarrow \arg \max_a\sum_{s', r}p(s', r | s, a)[r + \gamma V(s')]$  
    > If *old-action* $\ne \pi(s)$, then *policy-stable* $\leftarrow$ *false*  
    
    If *policy-stable*, then stop and return $V \sim v_{\star}$ and $\pi \sim \pi_{\star}$; else go to 2
