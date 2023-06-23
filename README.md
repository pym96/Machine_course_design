# MACHINE LEARNING COURSE DESIGN

## Reinforcement Learning

In reinforcement learning, the agent aims to maixmize its cumulative reward:



![image](https://github.com/pym96/Machine_course_design/assets/105438207/11257884-f545-4a0d-a173-ede71540d917)




From the perspective of Bellman equation, the caculation of cumulative reward can be also formulated as:



![image](https://github.com/pym96/Machine_course_design/assets/105438207/cfd830e3-6d53-47ef-81b3-f691ee2058b6)



## Policy Iteration Learning

Once a policy, 𝜋, has been improved using **𝑣**𝜋 to yield a better policy, 𝜋′, we can then compute 𝑣𝜋′ and improve it again to yield and even better 𝜋″. We can thus obtain a sequence of monotonically improving policies and value functions:

![image](https://github.com/pym96/Machine_course_design/assets/105438207/c89790ee-3319-41d1-88ee-679acd327393)




where ⟶E⟶E denotes a policy *evaluation*, and ⟶I⟶I denotes a policy improvement. This way of finding an optimal policy is called *policy iteration*.

### Pesudo of Policy Iteration Learning

1. **Initialization**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/a13def5f-00eb-4ea7-80de-2e3918d79fd4)

2. **Policy Evaluation**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/32142b42-9250-4a17-9e03-5b761d34a574)

3. **Policy Improvement**

![image](https://github.com/pym96/Machine_course_design/assets/105438207/f5414b7e-cf5c-4392-b99c-5e6fdae63c83)


