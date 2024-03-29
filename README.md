# gym-multilayerthinfilm

The proposed OpenAI gym environment utilizes the parallelized transfer-matrix method (TMM-Fast) to implement the optimization of multi-layer thin films as parameterized Markov decision processes. An very intuitive example is provided in example.py.
Whereas the contained physical methods are well-studied and known since decades, the contribution of this code lies the transfer to an OpenAI gym environment. The intention is to enable AI researchers without optical expertise to solve the corresponding parameterized Markov decision processes. Due to their structure, the solution of such problems is still an active field of research in the AI community.<br/>
The publication [Parameterized Reinforcement learning for Optical System Optimization](https://iopscience.iop.org/article/10.1088/1361-6463/abfddb) used this environment.

## Installation
1. conda install git pip<br/>
pip install git+https://github.com/MLResearchAtOSRAM/gym-multilayerthinfilm.git<br/><br/>
2. Clone the repository and executing setup.py<br/>
Required packages:<br/>
numpy, matplotlib, pytorch, seaborn, as specified in environment.yml
based on which you can create an approbiate environment via line command<br/>
conda env create -f environment.yml<br/>
Don't  forget to specify your common python environment path (prefix, last line in environment.yml)!

## Getting started
To get started you can execute the example py-file example_gym.py!

## Multi-layer thin films meet parameterized reinforcement learning
Reinforcement learning is an area of machine learning concerned with how intelligent agents ought to take actions in an environment in order to maximize the notion of reward. The code to be published implements such an environment for the optimization of multi-layer thin films.
In principle, the proposed code allows to execute actions taken by an agent. These actions determine which material and with which thickness to stack next, thereby consecutively forming a multi-layer thin film as illustrated in Figure 1. Such a multilayer thin-film exhibits optical characteristics. By comparison between the actual and user-defined desired characteristics, a notion of numeric reward is computed based on which the agent learns to distinguish between good and bad design choices. Due to its physical and mathematical structure, the optimization of multi-layer thin film remains a challenging and thus still active field of research in the scientific community. As such it gained recent attention in many publications. Therefore, naturally the need for a standardized environment arises to make the corresponding research more trustful, comparable and consistent.

![image](https://user-images.githubusercontent.com/83709614/127179171-bc7e8fe5-bd83-4125-a84f-12a9e16c3150.png)<br/> 
Figure 1: Principal idea of an OpenAI gym environment. The agent takes an action that specifies the material and thickness of the layer to stack next. The environment implements the multi-layer thin film generation as consecutive conduction of actions and assigns a reward to a proposed multi-layer thin film based on how close the actual (solid orange line) fulfils a desired (dashed orange line) characteristic. The made experience is used to adapt the taken actions made in order to increase the reward and thus generate more and more sophisticated multi-layer thin films.

## Description of key features
The environment can include<br/> 
•	cladding of the multi-layer thin film (e.g. substrate and ambient materials),<br/>
•	dispersive and dissipative materials,<br/>
•	spectral and angular optical behavior of multi-layer thin films (See figure 2),<br/>
•	… and many more.<br/>

The environment class allows to <br/>
•	conduct so-called parameterized actions (See publication) that define a multi-layer thin film,<br/>
•	evaluate the generated thin film given a desired optical response, and<br/>
•	render the results (See figure 2). <br/>

In general, the comprehensive optimization of multi-layer thin films in regards of optical response encompasses <br/>
•	the number of layers (integer),<br/>
•	the thickness of each layer (float),<br/>
•	the material of each layer (categorical, integer).<br/>

![image](https://user-images.githubusercontent.com/83709614/127179200-16aaf611-ad17-4082-a47f-d933ba7cbc83.png)<br/> 
Figure 2: Rendered output of the environment. Reflectivity (left) over angle of incidence and spectrum of a multi-layer thin film (right). Here, the stack features four layers and each layer’s material was chosen from a set of eight alternatives. The reward is computed based on a desired reflectivity, which is one for each angle and wavelength, but not displayed in this figure.


## Citing
If you use the code from this repository for your projects, please cite:
[Parameterized reinforcement learning for optical system optimization](https://iopscience.iop.org/article/10.1088/1361-6463/abfddb) in your publications.
