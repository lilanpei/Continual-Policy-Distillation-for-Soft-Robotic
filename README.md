# Continual Policy Distillation of Reinforcement Learning-based Controllers for Soft Robotic In-Hand Manipulation

Dexterous manipulation, often facilitated by multi-fingered robotic hands, holds solid impact for real-world applications. Soft robotic hands, due to their compliant nature, offer flexibility and adaptability during object grasping and manipulation. Yet, benefits come with challenges, particularly in the control development for finger coordination. Reinforcement Learning (RL) can be employed to train object-specific in-hand manipulation policies, but limiting adaptability and generalizability. We introduce a Continual Policy Distillation (CPD) framework to acquire a versatile controller for in-hand manipulation, to rotate different objects in shape and size within a four-fingered soft gripper. The framework leverages Policy Distillation (PD) to transfer knowledge from expert policies to a continually evolving student policy network. Exemplar-based rehearsal methods are then integrated to mitigate catastrophic forgetting and enhance generalization. The performance of the CPD framework over various replay strategies demonstrates its effectiveness in consolidating knowledge from multiple experts and achieving versatile and adaptive behaviours for in-hand manipulation tasks. 

Objects used and their poses for In-Hand Manipulation:
![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/objects_pose.png?raw=true)

The proposed CPD framework is established through a pipeline shown bellow, that involves recurrently learning a soft robotic hand controller in simulation for in-hand manipulation of a specific object, and its integration with the previously acquired knowledge to build a versatile controller. 
![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/workflow.png?raw=true)

During Policy Learning, the expert’s control policy undergoes training using RL for in-hand re-orientation of an object. This process can be repeated for various objects, with a distinct expert trained for each. 

![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/rollouts.png?raw=true)

In Knowledge Integration, demonstrations of the experts’ policies are asynchronously sampled and employed for rehearsal-based continual policy distillation. This entails integrating the acquired knowledge from multiple experts into a unified policy. 

![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/CPD_framework.jpg?raw=true)


This work contributes to the advancement of soft robotic manipulation by integrating RL and CL. By addressing the catastrophic forgetting problem and integrating knowledge from multiple RL agents, the developed soft robotic hand controller enables versatile and adaptive behaviours, facilitating the effective deployment of soft robotic systems in various scenarios.

![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/Cumulative_Training_using_different_loss_functions.png?raw=true)

The approach offers advantages in terms of time efficiency, with significantly reduced training time compared to traditional online RL. By utilizing a limited-size memory buffer, memory efficiency is optimized while retaining important knowledge for learning.

![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs/performance_baselines.png?raw=true)

Overall, CPD provides a practical and efficient sequential learning framework to address the challenge of knowledge integration in complex manipulation tasks. It contributes to the advancement of learning-based control strategies for soft robotic systems within the paradigm of CL. CPD holds promise for developing intelligent and adaptive soft robotic hand controllers that continually acquire and retain knowledge, enabling them to perform a wide range of tasks effectively in several applications.

![alt text](https://github.com/lilanpei/Continual-Policy-Distillation-for-Soft-Robotic//blob/main/imgs//Comparison_of_replay-based_CL_strategies_with_variable_size_replay_buffer.png?raw=true)
