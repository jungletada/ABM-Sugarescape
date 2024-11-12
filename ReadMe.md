# Sugarscape Constant Growback Model with Traders

## Summary

This is Epstein & Axtell's Sugarscape model with Traders, a detailed description is in Chapter four of
*Growing Artificial Societies: Social Science from the Bottom Up (1996)*. The model shows an emergent price equilibrium can happen via a decentralized dynamics.

This code generally matches the code in the Complexity Explorer Tutorial, but in `.py` instead of `.ipynb` format.

### Agents:

- **Resource**:  Resource agents grow back at one unit of sugar and spice per time step up to a specified max amount and can be harvested and traded by the trader agents.
  (if you do the interactive run, the color will be green if the resource agent has a bigger amount of sugar, or yellow if it has a bigger amount of spice)
- **Traders**: Trader agents have the following attributes: (1) metabolism for sugar, (2) metabolism for spice, (3) vision,
  (4) initial sugar endowment and (5) initial spice endowment. The traverse the landscape harvesting sugar and spice and
trading with other agents. If they run out of sugar or spice then they are removed from the model. (red circle if you do the interactive run)

The trader agents traverse the landscape according to rule **M**:
- Look out as far as vision permits in the four principal lattice directions and identify the unoccupied site(s).
- Considering only unoccupied sites find the nearest position that produces the most welfare using the Cobb-Douglas function.
- Move to the new position
- Collect all the resources (sugar and spice) at that location
(Epstein and Axtell, 1996, p. 99)

The traders trade according to rule **T**:
- Agents and potential trade partner compute their marginal rates of substitution (MRS), if they are equal *end*.
- Exchange resources, with spice flowing from the agent with the higher MRS to the agent with the lower MRS and sugar
flowing the opposite direction.
- The price (p) is calculated by taking the geometric mean of the agents' MRS.
- If p > 1 then p units of spice are traded for 1 unit of sugar; if p < 1 then 1/p units of sugar for 1 unit of spice
- The trade occurs if it will (a) make both agent better off (increases MRS) and (b) does not cause the agents' MRS to
cross over one another otherwise *end*.
- This process then repeats until an *end* condition is met.
(Epstein and Axtell, 1996, p. 105)

The model demonstrates several Mesa concepts and features:
 - OrthogonalMooreGrid
 - Multiple agent types (traders, sugar, spice)
 - Dynamically removing agents from the grid and schedule when they die
 - Data Collection at the model and agent level
 - custom solara matplotlib space visualization

-------------
## Summary
这是Epstein & Axtell的“糖景模型与交易者”模型的内容，详细描述见于《构建人工社会：自下而上的社会科学》（1996年）第四章。该模型展示了一种价格均衡的涌现现象，可以通过去中心化的动态实现。  

此代码大体上与复杂性探索者教程中的代码一致，但为.py格式，而非.ipynb格式。

### Agents:
- **Resource**: Resource agent 在每个时间步增加一单位的糖和香料，直至达到指定的最大值，并可以被 trader agent 收获和交易。（在互动运行中，如果 Resource agent 拥有较多的糖，则显示为绿色；如果拥有较多的香料，则显示为黄色）
- **Traders**: Trader agent 具备以下属性：(1) 糖的新陈代谢率，(2) 香料的新陈代谢率，(3) 视野范围，(4) 初始糖的存量，(5) 初始香料的存量。Trader agent 在景观中移动，收获糖和香料，并与其他 agent 进行交易。如果它们的糖或香料耗尽，则会从模型中移除。（在互动运行中显示为红色圆圈）

trader agents 根据规则 **M** 穿越景观：
- 在视野允许的范围内朝四个主要的网格方向观察并识别未被占据的位置。
- 仅考虑未被占据的位置，找到使用Cobb-Douglas函数产生最大福利的最近位置。
- 移动到新的位置。
- 收集该位置的所有资源（sugar 和 spice）。
（Epstein 和 Axtell, 1996, 第99页）

traders 根据规则 **T** 进行交易：
- agent 和潜在的交易伙伴计算他们的边际替代率（MRS），如果相等，则 *结束*。
- 资源交换，spice 从具有更高 MRS 的 agent 流向具有较低 MRS 的 agent，sugar 反向流动。
- 价格 (p) 通过取 agents 的 MRS 的几何平均值来计算。
- 如果 p > 1，则 p 单位的 spice 被交换为 1 单位的 sugar；如果 p < 1，则 1/p 单位的 sugar 被交换为 1 单位的 spice。
- 如果交易满足以下条件则发生：(a) 使双方 agent 增益（提高 MRS），并且 (b) 不导致 agents 的 MRS 互相交错，否则 *结束*。
- 该过程会重复，直到达到 *结束* 条件。
（Epstein 和 Axtell, 1996, 第105页）


### See also:
[Complexity Explorer Sugarscape with Traders Tutorial](https://www.complexityexplorer.org/courses/172-agent-based-models-with-python-an-introduction-to-mesa)
