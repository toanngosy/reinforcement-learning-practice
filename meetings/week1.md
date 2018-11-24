# Week 1 - Blog of An Outsider's Tour of Reinforcement Learning - Ben Recht
## Introduction
Recently, Reinforcement Learning (RL) becomes a hot topic since it achieved astonishing results in complex games (Dota, Go,...) and particularly on a real world problem: [cutting down Google Data Center Cooling Bill by 40%](https://deepmind.com/blog/deepmind-ai-reduces-google-data-centre-cooling-bill-40/). However, there are limited applications of Reinforcement Learning (RL) in industrial systems because of the unstability and effectiveness of RL over other well-studied control methods in Control Theory (CT).

Afterall, RL and CT solve the same challenge: how to effectively control a system and drive it to desirable states with high expected accumulative reward (or low expected accumulative cost). Not suprisingly, we have the same concepts but called by different terms: reward in RL versus cost in CT or backpropagation in DL/RL versus [the method of adjoints](http://www.argmin.net/2016/05/18/mates-of-costate/) in CT. The blog of Prof. Ben Recht is the first attempt to merge these two fields and how they can support and leverage each other. A unified view between both fields would be favorable to create new control methods and may prevents reinventing the wheel. 

## Optimal Control and RL
Assuming having state transition is linear, have math formula to solve - have A and B to describe state transition  
What if we dont have A and B? Model-free methods (PID, RL)

Measuring the performance of an control algorithm based on 2 key points: final accumulative reward, number of trials before achieving good policy.  

Iterative Learning Control in CT (design control system on repetitive task) is equivalent to Reinforcement Learning  

RL tries to hide as much info about env as possible, however there is a trade off: require a lot of iteration. On the other hand, ILC requires model -> few iteration to converge to good solution. Good algorithm should be somewhere in between - estimate a nominal/coarse model?

Most of comtemporary RL algorithms are based on Policy Gradient - estimate a stochastic policy. However we always can find a better deterministic policy, thus PG is suboptimal - in CT, no assumption of having stochastic policy. Derived algorithms from Policy Gradient such as TRPO (with whritst and bell on policy update) or soft Actor-Critic can help, I want to see how these algorithms comparing with Random Search, since TRPO is more careful on updating policy than PG (from the blog post).  

Approach on LQR with model estimator:
An estimator of model -> nominal model.
In LQR, estimate A and B by probing $u_t$. How about a nonlinear model?

--------------------------
A good algorithm should lie somewhere between model-based and model-free method

Some thoughts on An's Model-based methods:
They have paper on this estimation and how to estimate also the uncertainty - the estimated model is not only a model but a set of models, this set of models contains the model with uncertainty (bounded model).

> To be a bit more precise, suppose in that we have a state dimension d and have p control inputs. Our analysis guarantees that after O(d+p) iterations, we can design a controller that will have low cost on the infinite time horizon. That is, we can guarantee that we stabilize the system (we won’t cause fires) after seeing only a finite amount of data.

Questions:
Coarse-ID control assumes a linear relation between state and action (control params)?







