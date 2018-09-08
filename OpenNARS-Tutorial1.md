This tutorial is work in progress, the images will be gradually replaced with re-done ones.

NARS is an inference engine that consists of the three major parts:
![Inference engine and reasoning cycle](https://user-images.githubusercontent.com/8284677/45256877-7d022d00-b36a-11e8-8ff3-b13db705cad6.png)
with these 3 components, inference can be understood as a cycle:
1. Select 2 premises from memory
2. apply the logic rules that apply
3. obtain the results and put them back into memory.

Since NARS works under the Assumption of Insufficient Knowledge and Resources, it has to maintain a max. memory capacity, which the Bag data structure allows for: 
![AIKR and Bag](https://user-images.githubusercontent.com/8284677/45256886-b3d84300-b36a-11e8-8479-f0dfd8d3d8e4.png)
![Budget value](https://user-images.githubusercontent.com/8284677/45256919-4d075980-b36b-11e8-98c4-c028e87f1784.png)
The for us relevant operation will be a combination of select, then some usage we didn't specify yet, and then and Add call with the selected item to put the item Bag into the data structure, with Forgetting applied in-between.

Since NARS uses a term logic, memory is structured by the occurring terms, which can be compound terms and their components. Each such term gets a concept container associated with:
![Memory as a bag of concepts, concepts named by term](https://user-images.githubusercontent.com/8284677/45256897-db2f1000-b36a-11e8-8daf-79b530809ad4.png)

Each such concept container has a belief table, that stores sentences that have the same term as the concept is named by:
![Belief table of concepts](https://user-images.githubusercontent.com/8284677/45256980-4a593400-b36c-11e8-8243-75d8c65bc1c5.png)

The other data types:
![The data items](https://user-images.githubusercontent.com/8284677/45256951-049c6b80-b36c-11e8-8bfc-78baec482068.png)

![Example1](https://user-images.githubusercontent.com/8284677/45256939-c901a180-b36b-11e8-985b-a5a3cc32ba84.png)
This example results in the following memory structure:
![Resulting memory structure](https://user-images.githubusercontent.com/8284677/45257017-dec39680-b36c-11e8-8d26-f84965c6f9e0.png)

And the inference can happen through the following control loop:
![Control loop](https://user-images.githubusercontent.com/8284677/45257040-4aa5ff00-b36d-11e8-8e2f-efe6d66a5a9f.png)

Next tutorial: While the truth of the conclusion is decided by Non-Axiomatic Logic, how is the budget of the conclusion derived?
