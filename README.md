# HomeOntology-and-Argumentation
The framework for the Semantic Web Journal, with link for the UI.

You can access the web UI here: http://155.207.113.42:8888/

token: ed7fb941ece54e85ad84d874343549729965deff407aa876

Title: An Open-Ended Web Knowledge Retrieval Framework for the Household Domain with Explanation and Learning through Argumentation

Authors: Alexandros Vassiliades, Nick Bassiliades, and Theodore Patkos

Abstract:
Semantic Web knowledge bases can provide explainability and knowledge availability to the knowledge representation of any cognitive robotic system. For this reason, we present a knowledge retrieval framework enhanced with external knowledge sources that can argue about its decisions and even learn new knowledge through an argumentation dialogue. The framework provides knowledge about sequences of actions on how to perform human scaled tasks in a household environment, answers queries about household objects, and performs semantic matching between entities from the web knowledge graphs DBpedia, ConceptNet, and WordNet, with the ones existing in our knowledge graph. We offer a set of predefined SPARQL templates that directly address the ontology on which our knowledge retrieval framework is built, and querying capabilities through SPARQL. The framework can argue with the user about its answers with two different scenarios, missing where an entity should be in the answers of the framework, according to the user, and wrong where an entity should not be in the answers of the framework. We evaluated our framework via two different user evaluations.


The main class of our project is the frameworkMain.py. Therefore, the framework initializes from there. After that the user is faced with the choices:

Hello! :) Right Now the questions that I can answer for you are:\
(1) How you can perform a specific task. Press 1 then give the task or tasks that you want to perform.\
(2) What can you do with some objects. Press 2 then give the objects.\
(3) What other objects are related to some objects. Press 3 then give me the objects.\
(4) On what objects can you perform an action. Press 4 then the action or actions.\
(5) On what object you can perform an action with a condition. Press 5 then give me action and condition.\
(6) What actions can be performed on a set of objects. Press 6 then give me objects.\
(7) What sequence of actions can be performed on a single object. Press 7 then give me object.\
(8) Return sequence of action of specific instance. Press 8 then give me instance.\
(9) Return the sequences of actions, based on some objects order. Press 9 then give the objects you want to search for in specific order.\
(10) You can create your own query. Press 10.

The user must then pick up a choice and start following the instructions of the framework, as for the input data needed in order for the framework to return the desirred answer. 

Example:

Choice 3

Give me the objects for which you want me to find other objects! If there are more than one seperate them by comma :)\
coffee, milk      ##The format for every question must be like this\

[coffee1, coffee2]

Which coffee do you prefer? Give me the number in the list

1

[milk1 ]

Which milk do you prefer? Give me the number in the list

1

[coffee1, milk1 ]

['kitchen1 ', 'coffe_maker1 ', 'coffee_filter1 ', 'ground_coffee1 ', 'water1 ', 'coffee_pot1 ', 'coffee_cup1 ', 'food_sugar1 ', 'spoon1 ', 'coffee_cup4 ', 'coffee_table1 ', 'coffee_cup2 ', 'glass1 ', 'ice1 ', 'table1 ', 'stove1 ']


Is everything ok, or is there something missing/wrong? [missing/wrong]\
wrong\
Ok give me the entity you consider wrong.

ice1

Please give a KB from which you found that this entity should not be part of my answers.\
WikiHow\
Let me search in the KB you gave me.\
Ok I found it!\
Arbitrator do you consider that ice1 should be in my answers?\
No\
Ok I will import this information in my KB

An issue that might occur (IF you do NOT want to use the Ui), the jar file are the ones that are sending SPARQL queries to the Ontology. The reason we use Java although all the framework is built with Python is because Python libraries could not parse the ontology quickly enough. Therefore, in order for the jar file to be functional, one may need to take the java code (inside the zip files), change the path to the .ttl file, create a jar. After that you are ready to go :). Similar changes of paths are needed inside the code, for local use.

We need to apologize for the last part, but unfortunately python does not have an rdf parser for large files that has good time performance. Thus, we used java only for this part.

If any diasmbiguation is needed for the framework please shout me an email at: valexande@csd.auth.gr
