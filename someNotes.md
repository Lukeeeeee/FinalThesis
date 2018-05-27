全路网智能路径规划

计划
5.22 – 6.7

1.	读完10篇左右参考文献，同时确定实验和代码的细节，一些设计上的问题 5.22 – 5.25
2.	写实验代码，跑实验，同时写论文的 abstract和 background 的部分 
5.26-5.31
3.	跑完实验后开始写自己的算法部分和贴结果
6.1-6.3
4.	revise 论文，调整排版，翻译一篇外文论文
6.4-6.6


如何设计 agent 的state action

action 按照原设计不变，4个方向

state
底层从 Dijkstra 的一个 shortest path 提供一个 valid action set，本身最短路可能存在多个path. Agent select from the set，然后根据 q 值从 valid action set 选

reward 把不同的 metric encode 进去


实验设计 

1.	Dijkstra (or other naïve routing algorithm) + RL to encode some simple scenarios 
a)	Simple grid world with obstacles 
b)	With turning cost
2.	Solution on scenario with distance limitation 
a)	No end-to-end is possible
b)	考虑设计一个简单的 hierarchical 的模型
i.	Decision on reach to charge site or the target site
ii.	After that, use a simple RL policy to do routing
c)	Or 考虑设计一个精致的 reward function 和 state representation
i.	Every charge site and target contribute to the reward computing. 
1.	By getting to the charge site also target, more reward will get
3.	Solution on dynamic environment
a)	Encode the dynamics into the reward function 
b)	Use a simple grid world without any obstacles


2. How to desgin baselien or benchmark
	2.1 








大纲
1	Abstract 
2	Introduction
3	Related work
4	Background
4.1	Route Planning Problem
4.1.1	Metric function
4.2	Search based approach
4.2.1	Dijktra
4.2.2	A star search
4.3	Reinforcement Learning based approach
4.3.1	MDP formulation
4.3.2	Value-based approach in RL
4.3.2.1	Q-Learning method
4.3.2.1.1	Tabular 
4.3.2.1.2	Function approximation 
4.3.2.1.2.1	Linear and non-linear approach
4.3.2.1.2.2	Neural network
5	Our method
5.1	Problem formulation of Route planning with MDP
5.2	Advantages by using Reinforcement learning
5.3	Different route planning scenarios 
5.3.1	Grid world with obstacles
5.3.2	Grid world with turning cost 
5.3.3	Grid world with distance limitation and charge site
5.3.4	Grid world with dynamics
5.4	Implementation details
6	Experiments and Results 
7	Conclusion and future work
8	Acknowledgement 
9	Reference











ABSTRACT

With the development of Artificial Intelligence and Machine Learning, Reinforcement Learning, as an important method in this field, have showed its great potential in field like Go, …. As a decision-making and control schema, reinforcement learning also can be applied in route planning system, which is a widely used system in navigation system … In our work, we applied reinforcement learning to route planning problem and solved various scenarios, especially for the scenario that traditional search-based route planning algorithms like Dijkstra and A * search can’t solve. 

The content of the dissertation is divided into three parts, firstly, we give the mathematical formulation of route planning problem, and adapted it into Markov Decision Process. Then we adapted it to different scenarios with modification of original formulation. At last, we compared our reinforcement learning based method with search based method which regard as the baseline under different experiments.

Our main contributions are 1) firstly applied reinforcement learning into online-routing service 2) showed the flexibility of reinforcement learning with different metric function, scenarios and even dynamics environment.

Keywords: Route planning, routing service, reinforcement learning, online learning, 




第一章 绪论
1.1	研究工作的背景与意义
1.2	路径规划问题的国内外研究历史与现状
1.3	本文的主要贡献与创新
1.4	本论文的结构安排
第二章 路径规划问题
2.1 路劲规划问题的基本数学形式
	2.2 不同的场景及其形式
		2.2.1 简单网格地图
		2.2.2 带有转弯惩罚的场景
		2.2.3 带有行驶路径限制和充电桩的场景
		2.2.4 基于时间的动态地图环境
第三章 基于搜索的路径规划方法
3.1  Dijkstra算法
	3.2  A star 算法
	3.3  基于搜索算法的局限性
第四章 强化学习基础
	4.1  马尔科夫决策过程
	4.2.  基于智能体的建模
	4.3  强化学习
		4.2.1 价值函数
		4.3.2 策略函数
		4.3.3 基于价值函数的方法
			4.3.3.1 查表法
			4.3.3.2 函数近似法
		4.3.4 基于策略梯度的方法
第五章 基于强化学习的路径规划算法
	5.1 数学形式表述
	5.2 不同场景下的强化学习解决算法设计思路
第六章 算法实现及实验
	6.1 基于面向对象编程的代码实现
	6.2 测试环境设计 
	6.3 基于搜索方法的基准模型实验
	6.4 基于强化学习方法的实验
	6.5 结果及对比
第七章 全文总结与展望
	7.1 全文总结
	7.2 后续工作展望

致谢
参考文献

