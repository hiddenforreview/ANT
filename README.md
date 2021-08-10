# Knowledge Amalgamation for Multi-Label Classification (KAMLC)
This is the implementation repository of <i>Adaptive kNowledge Transfer (ANT)</i>, the solution for (KAMLC).

## File listing

+ __main.py__ : Code for training ANT
+ __model.py__ : Supporting models
+ __utils.py__ : Supporting utility functions
+ __requirements.txt__ : Library requirements

## Instructions 

Prepared folders:

+ __data__ : directory to place training data
+ __teachers__ : directory to place teacher models
+ __output__ : directory for training logs 
    + __plot__ : directory for training plots

The datasets and the teachers we use in our paper are available here:


Run script as:

    python main.py -expname syn_exp1 -t_model ./teachers/exp1_syn_t1.sav ./teachers/exp1_syn_t2.sav \
    -t_numclass 4 4 -t_class 1 2 3 4 3 4 5 6 -s_class 1 2 3 4 5 6 -data ./data/SYN/syn_test.txt
  
  
<b>Parameters:</b>

+ __Required:__
  + __-t_model__ : a list of paths of teacher models 
  + __-t_labels__ : a list of specialized classes of each teacher, concatenated in correspond to t_model , e.g., t1_class: 1 2 3 4 and t2_class: 3 4 5 6, then t_class: 1 2 3 4 3 4 5 6
  + __-s_labels__ : a list of comprehensive classes of the student
  + __-data__ : the path of student training data file

+ __Student network:__
  + __-lr__ : learning rate, default 0.001
  + __-ep__ : epochs, default 500
  + __-bs__ : batch size, default 8
  + __-layers__ : #layers, default 1
  + __-hiddim__ : #hidden units, default 32

+ __Others:__
  + __-seed__ : set seed for reproduction, default 0
  + __--save__ : boolean parameters, whether to save the student model, default false
  
  
