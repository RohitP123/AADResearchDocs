# About Me
- Team Member: Rohit Patil
- Email: rpatil73@gatech.edu
- Cell Phone: 612-751-3406
- Interests: Machine Learning/AI, Basketball, Football
- NAS Subteam Members:
  * Sai Guntabonu (sg1@gatech.edu)
  * Elias Cho (echo94@gatech.edu)
  * Kevin Park (kpark373@gatech.edu)
  * Tristan Thakur (tthakur9@gatech.edu)
  * Alex Wang (awang602@gatech.edu)
  * Hugh Weston (hweston3@gatech.edu)
  * Noah Cook (ncook40@gatech.edu)
  * Ruby Yu (r.yu@gatech.edu)
  * Ravij Lade (rlade@gatech.edu)

- Titanic ML/GP Group 5 Team Members: Keigo Hayashi (khayashi31@gatech.edu), Kevin Song (ksong85@gatech.edu), Sai Guntabonu (sguntabonu3@gatech.edu), Yunling Tao (ytao307@gatech.edu)
## Spring 2024
* [Friday Apr 26](#friday-apr-26)
* [Week of Apr 22](#week-of-apr-22)
* [Week of Apr 15](#week-of-apr-15)
* [Week of Apr 8](#week-of-apr-8)
* [Week of Apr 1](#week-of-apr-1)
* [Week of Mar 25](#week-of-mar-25)
* [Week of Mar 11](#week-of-mar-11)
* [Week of Mar 4](#week-of-mar-4)
* [Week of Feb 26](#week-of-feb-26)
* [Week of Feb 19](#week-of-feb-19)
* [Week of Feb 12](#week-of-feb-12)
* [Week of Feb 5](#week-of-feb-5)
* [Week of Jan 29](#week-of-jan-29)
* [Week of Jan 22](#week-of-jan-22)
* [Week of Jan 8](#week-of-jan-8)

## Fall 2023 TOC
* [December 8](#december-8)
* [Week of Dec 4](#week-of-dec-4)
* [Week of Nov 27](#week-of-nov-27)
* [Week of Nov 20](#week-of-nov-20)
* [Week of Nov 13](#week-of-nov-13)
* [Week of Nov 6](#week-of-nov-6)
* [Week of Oct 30](#week-of-oct-30)
* [Week of Oct 23](#week-of-oct-23)
* [Week of Oct 16](#week-of-oct-16)
* [Week of Oct 2](#week-of-oct-2)
* [Week of Sep 25](#week-of-sep-25)
* [Week of Sep 18](#week-of-sep-18)
* [Week of Sep 11](#week-of-sep-11)
* [Week of Aug 28](#week-of-aug-28)
* [Week of Aug 21](#week-of-aug-21)

## Spring 2022 TOC
* [Week of April 24th](#week-of-april-24th)
* [Week of April 17th](#week-of-april-17th)
* [Week of April 10th](#week-of-april-10th)
* [Week of April 3rd](#week-of-april-3rd)
* [Week of March 27th](#week-of-march-27th)
* [Week of March 13th](#week-of-march-13th)
* [Week of March 8th](#week-of-march-8th)
* [Week of March 1st](#week-of-march-1st)
* [Week of February 22](#week-of-february-22)
* [Week of February 15th](#week-of-february-15th)
* [Week of February 8th](#week-of-february-8th)
* [Week of February 1st](#week-of-february-1st)
* [Week of January 25th](#week-of-january-25th)
* [Week of January 16th](#week-of-january-16th)
* [Week of January 9th](#week-of-january-9th)

# Spring 2023
## Friday Apr 26
### Team Meeting
- Finals this week
- Self-Driving Team
   - Problem: current object detection models lack accuracy needed for safe transportation
   - Goal: Use EMADE to develop an object detection model (a model better than YOLO)
   - Dataset - Lyft 3D object detection for autonomous vehicles
   - They got a keras implementation of YOLOv3 using a github script
   - Created a new class for the YoloLearner primitive(LayerType object)
      - First half of primitive simulates the conversion script
      - The second half of the primitive simulates the train script
      - Had some issues with keras tensors fitting to model not loading
   - Evaluation Methods: OuI, evaulate_object_count, and evaluate_class accuracy (measures proportion of correctly identified classes for detected objects against total num of objects detected)
   - Used standalone tree evaluator to test their primitive and evaluation methods
   - Planning on integrating other potential models into EMADE (YoloV1, YoloV4, YoloV8, Yolo-NAS, R-CNN Object Detection, Faster R-CNN, ResNet)
   - Built a docker build to easily get EMADE setup
      - Doesn't really work well with PACE
   - Future Work: additional tensorflow implementations
- LLM
   - Explained the overall architecture of how their team would work after a user ssh connects. 
   - They have a diverse prompt pool and did random selection to decide the prompts. Also are doing modular changes to prompts in order to not alter their fundamental nature.
   - Prompt Engineering Techniques: Zero-Shot prompting(only up to model), Few-Shot prompting(Give examples to guide model), Chain of thought prompting(sequential cues to guide model)
      - Things they are hoping to incorporate prompt engineering in the future: Tree of thoughts prompting(structure input in hierarchical manner), directional stimulus(guides model with specific hints to target responses), Ease of testing
   - Initial output loop had a big drop in accuracy (due to dropout). Also attributed it to 7b model instead of other model
   - Made sure to keep the same conversation for creating initial population
   - They also implemented accuracies to associate each model with a weighted accuracy. This allows for choosing best model while leaving room for diversity.
   - They were also having errors with setup that they got fixed for new members
- Island Migration
   - Goal is to try and create better evolutionary algorithms
   - Objectives: genetic diversity, improve analysis and testing, test implementation with individualized islands.
   - Genetic Diversity: 1. Calculate distances into distance matrix, 2. Perform hierarchical clustering on each distance matrix, 3. Diversity Calculation with Simpson's Diversity Index(lower index means more diversity)
   - Phenotypic Diversity - take objective space and divide into different bins. Normalize and use Shannon diversity index
   - Looked into a combination of genotypic and phenotypic diversities.
   - Created dashboard to visualize EMADE
      - Have database tables with pareto front individuals
      - Generational Pareto Graphs (How island pareto fronts change from gen to gen)
      - Individual Island Pareto Fronts
      - Island Heatmap
      - Added diversity metrics (genotypic and phenotypic)
   - Individualized Islands: have isalnds care about different objectives
   - For testing, they decided to use MNIST dataset and only 0, 1, and 2 as classes
   - Comparisons btwn Islan Migration, Normal Emade, and no migration- migration was too often for island migration turning it into an EMADE run
   - Expanding datasets - Cifar10(had issues with with memory)
   - Future Work: combine genotypic index values, continue testing, work with other subteams to test their work on new problems
- Our subteam presented next. 
   - [Here](https://docs.google.com/presentation/d/1Cdue12HWeqKeNsHSh9HOPShlyz1jLBsekQHg6uc4xXQ/edit#slide=id.p) is a link to our presentation
- Transfer Learning
   - Problem: Chest X-Ray disease detection
   - Goal: train models through emade to correctly identify diseases
   - Dataset: National Institute of Health front chest x-rays
   - Switched from multiclass to multilabel dataset
   - Made some changes after midterms - changed loss function to categorical cross entropy, changed activation function to softmax
   - Explained the different datasets that they split their original dataset into (small sample of dataset, full dataset, full dataset w/ no finding class, and balancing/combined dataset)
   - Explained some issues they encountered and fixes for these issues: These include test data being empty, issues with standalone tree evaluator, RAM issues, Long runtime issues, Lock File Issues.
   - Implemented Grad-CAM to identify critical regions within an input image.

## Week of Apr 22
### Team Meeting
- Our subteam is working on getting runs for our subsubteams. We are working on getting a seeding file and standardizing eval params for each subsubteam.
- Self Driving is having issues with workers on PACE-ICE. They also successfully added the YOLO primitive, added gen function, and updated the parse tree function.
- Transfer Learning finished two multi-label datasets. They are also currently getting a empty test dataset error that they are working on resolving.
- Island Migration is doing data calculations of hypervolume. Also they have a run with individualized islands.
- LLM was able to get 10 generations on their 7b model. They added time and accuracies into prompts.

### Personal Progress
- I started by creating a seeding file that would work for all subteams with the new skip connection changes. I did this by taking some individuals from our midterm seed and added some extra individuals.
   - Fixed malformed node errors (these were caused by errors parsing the individual strings) 
      - Fixed by making sure all activation functions were uncommented
      - Also changed old skip connections to the new format of SkipConnection4dim(NBack_, activationFunction)
   - [Here](https://github.gatech.edu/awang602/emade/commit/a921b985a5697c1aa703e74b08260715b0414725) is the commit for the seeding file.
- I also made sure to standardize some of my evolution parameters so it is the same across different subsubteams. These changes include changes to params in our input template, changes to the layerunit terminal, and adding back in early stopping.
   - These commits can be found [here](https://github.gatech.edu/awang602/emade/commit/51c851aaecc1a664641d1157bdabc9bfa1eb3f05) and [here](https://github.gatech.edu/awang602/emade/commit/dc6a89e29126fabce0ecba42fb937974dd4bc86f)
- One issue we found was that the layerunit 1024 and 256 were causing individuals to have extremely large evaluation times. Therefore, we decided to [get rid of these](https://github.gatech.edu/awang602/emade/commit/ea37340d4c6a3f88e4f1f8f54bfb4f71ad381c27) in the seed and as a terminal in gp_framework_helper.

- I was able to get a full evolutionary run with these standardized params. It got to around generation 96. Below is the AUC for the run.
   - <img width="318" alt="Screenshot 2024-04-24 at 6 56 34 PM" src="https://github.gatech.edu/storage/user/67530/files/5647d349-36ee-49d8-97d1-c740dae601f2">
   - Something I noticed is that inceptionLayer individuals are not showing up very often. In fact, it is quite rare to see them. They were only in generation 0 and one time in generation 3, however after there, they did not show up at all.
      - I believe this is because these individuals are more complex and therefore cause a longer elapsed time which is one of our objectives that we are minimizing. Therefore, the master avoids this layer. This is something I will probably bring up in the presentation.
   - Tristan and I also did many other runs. The following image displays the AUC's for these runs.
      - <img width="278" alt="Screenshot 2024-04-26 at 8 38 10 PM" src="https://github.gatech.edu/storage/user/67530/files/b64af439-9abf-414e-86e5-823294ce49ce">
   - These runs are unnormalized. The normalized data as well as runs for other subteams can be found [here](https://docs.google.com/spreadsheets/d/1vu25B47CVorDYaVv-RV-cOrl-Z-6SXMhCyFE44Y-aoU/edit#gid=0)


- On some runs I was getting issues.
   - One run the eval param of generating 50 individuals at the start caused some bad individuals to generate. These individuals would take extremely long to evaluate (sometimes up to 6000 seconds). This delay caused the run only to get up to generation 3. Therefore, I decided to only have 5 initially generated individuals.
   - Another issue is the master process dying due to a pickle data was truncated error. I am not really sure what this is and how we can fix it.
      - <img width="899" alt="Screenshot 2024-04-24 at 4 54 42 PM" src="https://github.gatech.edu/storage/user/67530/files/a328242d-36d2-44a7-9ff5-773993084138">
   - Another issues was the master stalling. This was caused after adding the changes that the mate/mutate team made. These [changes](https://github.gatech.edu/awang602/emade/commit/ab28288651cd410d89c0c3e4b206026f35b084cd) were made to the mate and mutate functions in emade_operators.py.
      - My master got stuck at generation 26 9(~2 hours) and there was no progress afterwards. I decided to revert back to the old file and continue runs.



- I created my final slides. I am going to talk about Splitting overview, the new addition primitive I implemented and some runs I did for splitting and skip connections.
   - I also created a slide for Noah and gave him the rundown on what he would present.
   - Also talked with Tristan about things Tristan could present (future work with new optimizations and the primitive he has been working on)



### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Create Seeding File for everyone to use | Complete | Apr 22 | Apr 26 | Apr 22 |
| Change eval parameters to agreed upon params | Complete | Apr 22 | Apr 26 | Apr 22 |
| Do Runs for finals | Complete | Apr 22 | Apr 26 | Apr 23 |
| Make slides for final presentation | Complete | Apr 22 | Apr 26 | Apr 25 |

## Week of Apr 15
### Team Meeting
   - Our subteam got a run with skip connections, mate/mutate were able to get add layer and swap layer working, and ViT is still working on issues they were having
   - Self driving is working on getting their branch on PACE. They are also working through some errors with their YOLO primitive, and have members running on standalone tree evaluator.
   - Transfer Learning finished their multi-label dataset, ran the dataset against EMADE and had bad results, looked into implementation of grad-cam and it looked fine
   - Island Migration got a version of MNIST (0, 1, and 2). Three objectives to train over. Also integrating CIFAR10 to get more datasets.

### Personal Progress
- This week I decided to add a new primitive that will take advantage of combining two data tensors after splitting. I decided to implement the Addition Primitive(Add) from tensorflow.keras.layers.
   - This also gave potential to some ideas for next semester: Finding ways to take advantage of the ability to split data tensors (researching better combining function and what we can do after splitting)
   - I implemented the additionLayer primitive by first creating a function that will append the Add() wrapper to the beginning of the layerlist on which AdditionPrimitive is being called on. The code for that is shown below. I used a testing file to implement these changes. [Here](https://github.gatech.edu/awang602/emade/commit/dc81f8c49e9f50f7cca4b6fad2e793bceb3661df) is my commit with the testing file.
```python 
def AdditionLayer(*argv):
    empty_layerlist = InputLayer()
    addlist = [Add()]
    # slice over by 1 to avoid "input"
    for arg in argv:
        addlist += arg.mylist[1:]
    empty_layerlist.mylist.append(addlist)
    return empty_layerlist
```
   - I also made sure to add the primitive to our pset with the code below.
```python
pset.addPrimitive(AdditionLayer, [nnm.LayerListM], nnm.LayerListM, name='add_test')
pset.context.update({'add_test': AdditionLayer})
```
   - The primitive successfully worked when compiling and evaluating the individual as shown below. In the image below, you can see an individual with the additionlayer primitive in a model.summary(). Also at the bottom, you can see the individual being evaluated.
   - <img width="1512" alt="Screenshot 2024-04-15 at 5 39 47 PM" src="https://github.gatech.edu/storage/user/67530/files/02d6ee12-9840-4980-aadd-4dceb98ed8ee">
   - I decided to add these changes to neural network methods and gp_framework_helper to potentially use this primitive in a run.

- Tristan was having some issue with getting a run with skipconnection
   - These issues included seeding process being killed, cloning issues, and evaluating issues, load_environment.
   - As a result of these issues I decided to make sure that the skip connection testing branch still works fine. So I switched to the branch and performed a run. It worked fine, however it only got to generation 35 since some individuals took a really long time to evaluate (~4000 seconds). Below is the pareto front for that run.
      - <img width="323" alt="Screenshot 2024-04-19 at 5 05 41 PM" src="https://github.gatech.edu/storage/user/67530/files/77b05d88-93a1-4a61-a744-12035073a100">
    - This confused me since I have pushed my latest code to the repo, and Tristan had pulled my recent changes, but there are still issues on his end even though we have the exact same code. Tristan is still working on fixing this.
- On the skipconnection-testing branch, I decided to implement the AdditionLayer changes with skip connections. I seeded and evaluated an individual that uses this primitive and it was successful as shown in the image below:
   - <img width="1068" alt="Screenshot 2024-04-19 at 5 08 13 PM" src="https://github.gatech.edu/storage/user/67530/files/3650fd46-31c7-41bf-b544-39b89c50626f">
   - One of the individuals did not evaluate due to this error string 
      - ```**********Inputs have incompatible shapes. Received shapes (13, 13, 64) and (13, 13, 128)```

- Subteam Meeting
   - We all gave each other updates on what we are working on and also what the plan for finals is.
   - Some things I decided to bring up which are important for our runs include getting a new seeding file with skip connection, standardized evolution parameters, and a potential fix to our AUC graphs being heavily reliant on the individuals with the lowest f1 score.
   - Elias is going to be getting a seeding file with skip connections this weekend which all subteams will use as our standardized seed.

- I also did a run with the new addition primitive.
   - It worked fine and I could see this primitive show up for future generation individuals. Below is the AUC graph. Only got to about gen 20.
      - <img width="317" alt="Screenshot 2024-04-22 at 5 01 52 PM" src="https://github.gatech.edu/storage/user/67530/files/cdfd1471-d42f-4997-bb07-be3c7cd5f1b4">

- At the hackathon, I worked on cleaning up my code, testing runs, and helping some members with setup.


### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Implement new addition primitive | Complete | Apr 15 | Apr 22 | Apr 19 |
| Test skip connection run again (bc Tristan had issues) | Complete | Apr 16| Apr 22 | Apr 18 |
| Subteam Meeting | Complete | Apr 15 | Apr 22 | Apr 19 |
| Test Skip connection with addition primitive | Complete | Apr 15 | Apr 22 | Apr 19 |
| Figure out Plan for finals in terms of presenting/runs | Complete | Apr 15 | Apr 22 | Apr 20 |
| Start Doing Runs for finals | Complete | Apr 15 | Apr 27 | Apr 23 |

## Week of Apr 8
### Team Meeting
   - Our subteam is still helping new members get on PACE, Fixing Dimension issues with ViT, testing skip connections, and working on add layer with mutations
      - Aaron mentioned that it is important to constrain image sizes when altering dimensions after feature extraction
   - Self-Driving is using the keras implementation of YOLO and are planning on fine tuning it for their lyft dataset.
   - Transfer Learning fixed their multi-class implementation and got results from EMADE, new members are getting on PACE
   - Island Migration fixed their data gathering for MNIST and got valid individuals(One of their members got to 350 generations). They might start doing seeded runs since a lot of time is going into searching for valid individuals.
   - LLM team new members were able to start making api calls to the LLM. Still having CUDA issues. 

### Personal Progress
   - This week the main focus was to try and get a full evolutionary run working with skip connections. Last week I was able to seed and evaluate individuals.
      - I seeded and evaluated a new set of individuals this time. Then, I started a master process. However, the master process just continuously stalled and individuals in the db were saying waiting for master. The img below shows the master stalling until it exits when it runs out of time.
         - <img width="975" alt="Screenshot 2024-04-19 at 3 25 49 PM" src="https://github.gatech.edu/storage/user/67530/files/f4c26ed4-1c4d-49d8-91d2-8aa629c6fad5">
         - The warning that is in the image is expected as I have seen that when I had a master work.
         - This is the same issue that I had earlier in the semester, but I was unable to find a fix for. It stalls when loading the truth dataset specifically. This is weird since the worker processes also do this step, but have never stalled/failed.
      - I tried modifying the code and slowly removing the skip_connection changes, but didn't have any luck in solving this issue.
      - I then, realized that it might be an issue with the global mods file, and the naming of mods. Therefore, I decided to switch out the global mods file to the [global mods file](https://github.gatech.edu/awang602/emade/blob/splitting-test/Global_MODS) in our splitting-test branch and made our mod names large numbers to fix some malformed node errors.
          - This ended up fixing the stalling issue and allowed me to do a full run. Therefore, I did a full run and got to generation 135. Below shows the master actually working.
          - <img width="1055" alt="Screenshot 2024-04-13 at 3 23 54 PM" src="https://github.gatech.edu/storage/user/67530/files/d052af03-e53b-4783-8e19-e0d945d5f49b">
          - Looking into the individuals generated, I can see that most of the do in fact use this new skip connection format which is good. Below is an example of an individual from generation 130 and its mods that it uses.
          - ```NNLearner(ARG0, PassLayerList(DenseLayer(LayerUnit1024, reluActivation, No_Normalization, GlobalMaxPoolingLayer2D(InceptionLayer(mod_360(InceptionLayer(mod_340(mod_230(Input(ARG1))))))), NoDropout)), AdagradOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))```
          - ```mod_230: Module(datatype, data_dims, Conv2DLayer(LayerUnit96, softmaxActivation, KernelSize7, Stride2, ValidPadding, No_Normalization, Conv2DLayer(LayerUnit1792, sigmoidActivation, KernelSize1, Stride2, ValidPadding, Layer_Normalization, ARG0)), SkipConnection4dim(NBack6, geluActivation), MaxPool2D(PoolSize2), Dropout50)```
          - ```mod_340: Module(datatype, data_dims, Conv2DLayer(LayerUnit192, linearActivation, KernelSize1, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit1536, softmaxActivation, KernelSize5, Stride1, SamePadding, Layer_Normalization, DenseLayer4dim(LayerUnit512, tanhActivation, No_Normalization, ARG0))), NoSkipConnection4dim(), NoPooling(), Dropout20)```
          - ```mod_360: Module(datatype, data_dims, DenseLayer4dim(LayerUnit2048, geluActivation, Layer_Normalization, Conv2DLayer(LayerUnit128, softmaxActivation, KernelSize1, Stride2, ValidPadding, Layer_Normalization, ARG0)), SkipConnection4dim(NBack7, tanhActivation), AvgPool2D(PoolSize2), NoDropout)```
      - I also plotted the pareto front for this graph and got the following AUC of 1438.9 (restricted generation to gen 100)
         - <img width="332" alt="Screenshot 2024-04-19 at 3 41 47 PM" src="https://github.gatech.edu/storage/user/67530/files/69e1e846-9d7e-4b9d-ad4a-ad698af6f775">
   - I also started thinking about what we want to show for finals from the splitting side. I think for now, the focus is just going to be on the results of multiple skip connection runs and some type of statistical test to compare our work with other subteams.

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Try a Full Evolutionary Run with Skip Connections | Complete | Apr 8| Apr 15 | Apr 9 |
| Figure out issue with stalling master process | Complete | Apr 8| Apr 15 | Apr 13 |
| Subteam Meeting | Complete | Apr 8 | Apr 15 | Apr 12 |
| Start thinking about what to do for finals | Complete | Apr 8| Apr 15 | Apr 14 |
| Get pareto front for full run with skip connections | Complete | Apr 8| Apr 15 | Apr 14 |


## Week of Apr 1
### Team Meeting
   - Our subteam is onboarding new members, ViT is still fixing dimension issues, Splitting is implementing skip connections changes, and mate/mutate is working on swap layer and add layer
   - As a class we talked about the difference between mutli-label vs multi-class problems
   - Self Driving are implementing YOLO spatial primitive instead of the mock version, and are working to get everyone to run standalone tree evaluator
   - Transfer Learning fixed standalone issues and got similar results as their EMADE runs and are making multi-label dataset
   - Island Migration integrating MNIST into EMADE and are finalizing migration logic
   - LLM is working on new member onboarding

### Personal Progress
- I first created a new branch in order to test skip connections
   - We found out that Tristan might not have been performing skip connection runs as intended as there should have been errors. So we are trying to integrate all the skip connection changes successfully.
   - I created a skipconnection-testing branch in order to work on testing this new feature. [Here](https://github.gatech.edu/awang602/emade/commit/56cac24990827f1186930f9bab9e91c069a1ca71) is the commit
- I also decided to create a file to test the skip connections outside of emade. [This](https://github.gatech.edu/awang602/emade/blob/skipconnection-testing/skipconnection_test.py) is what the file looks like. It was built off the original file used for testing the inceptionLayer primitive.
   - I was getting malformed node errors that look like below.
   - <img width="1509" alt="Screenshot 2024-04-09 at 3 48 09 PM" src="https://github.gatech.edu/storage/user/67530/files/38a8b495-6236-4b8d-8385-d5615c8c3ad7">
   - I assume this is because somewhere within the code, it is not registering the new skip connection correctly. (I bash reinstalled and made sure all my changes were correct, so I am not entirely sure why I am still getting this error).
   - As a result of this issue, I decided to move on to see if I can compile the individuals successfully through emade and see them in my database
- I created a seeding file with individuals that have mods that use skip connections. This was taken from an old member's codebase. [Here](https://github.gatech.edu/awang602/emade/blob/skipconnection-testing/SeedingFiles/skip_connection_testing) is the file.
   - I tried compiling these individuals within the db and it worked fine as seen in the image below. This confused me since, when I test an individual outside of emade, I keep getting the malformed node errors mentioned above. I plan to go back and find out why next week.
      - <img width="1074" alt="Screenshot 2024-04-09 at 3 56 45 PM" src="https://github.gatech.edu/storage/user/67530/files/302fb58f-8846-4c91-81ec-3dfa81537420">
      - This is what a mod with the new skip connection (labeled SkipConnection4dim) looks like
         - ```mod_34: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, ARG0))), SkipConnection4dim(NBack5, reluActivation), NoPooling(), Dropout50)```
   - I also tried to evaluate these individuals, by starting up a worker and this also worked fine. The results for these individuals is shown in the image below.
      - <img width="399" alt="Screenshot 2024-04-09 at 4 01 31 PM" src="https://github.gatech.edu/storage/user/67530/files/0ce9e9ab-523b-4b95-ad6e-d1d025b6c59f">
   - I will try to run a master next week to see if that works
- I pushed all my changes to the skipconnection-testing branch and explained my changes to Tristan as well: [commit](https://github.gatech.edu/awang602/emade/commit/6387f5432753255ebfe3534f041edfe1ef284292)


### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Integrate Skip Connection Changes | Complete | Apr 1| Apr 8 | Apr 7 |
| Compile Skip Connection Individuals | Complete | Apr 1| Apr 8 | Apr 7 |
| Evaluate Skip Connection Individuals | Complete | Apr 1| Apr 8 | Apr 7 |
| Subteam Meeting | Complete | Apr 1 | Apr 8 | Apr 5 |
| Create new branch for skip connection testing | Complete | Apr 1 | Apr 8 | Apr 4 |

## Week of Mar 25
### Team Meeting
   - We started by finishing up midterm presentations
   - LLM
      - They are using the Cifar10 dataset
      - Implemented tournament selection and did a lit review to reassess their current state of the problem (models were very repetitive)
      - Created new prompts that allowed for better model diversity.
   - Bootcamp Team 5
      - During preprocessing, they gave a score for the title of a passenger (married women + children, women, other)
      - Got a 0.33 AUC for the ML model pareto front
      - MOGP performed slightly better (AUC:0.313) but had issues with initial population
      - Talked about issues they have had and modifications to the evaluation parameters
      - EMADE performed best with AUC of 0.267
   - Plan for our subteam is to continue to perform runs with the same evolution parameters as other subteams for finals
   - Met with new members and got them access to our NAS notes doc. Also tasked them with getting setup on PACE using this doc.

### Personal Progress
- At our subteam meeting we discussed our plans for finals
   - Continue to perform runs
   - Major question was would we want all of our runs to use the skip connection changes that were made earlier
      - This didn't work for most of our members, but we decided that we would try and have all our subteams use these new changes
      - This means we are going to need to get a new seeding file for runs that use individuals with this new skip connection
      - I personally had issues getting runs with this earlier in the semester as my master kept failing. I am going to try once again this week.
- I decided to perform a full evolutionary run with splitting just to make sure everything still worked after spring break
   - Everything did work and below is an image of the AUC graph for the run
   - <img width="282" alt="Screenshot 2024-04-01 at 2 21 45 PM" src="https://github.gatech.edu/storage/user/67530/files/ff5bb76e-0f27-47af-a7d4-5c3c3ba4219c">
- Setting Up a branch for splitting runs
   - I planned to create a new branch just so anyone can perform baseline splitting runs without the skip connection changes
   - We had a second semester student, Alex, make a fork of our current repo and made sure to give everyone privileges for pushing.
      - This is because our old repo's owner is no longer on the subteam so we have no way for new members to get access
      - I also cloned this new repo into my scratch directory
   - Here are some commits for this new branch that I made which consist of some changes to files for making evolutionary runs work as intended: [commit](https://github.gatech.edu/awang602/emade/commit/7215507a9444fe7e76e2959c73bc2ce2543846a6)

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Subteam Meeting | Complete | Mar 25| Apr 1 | Mar 29 |
| Check in on new members PACE setup | Complete | Mar 25| Apr 1 | Mar 29 |
| Perform a full evolutionary run | Complete | Mar 25| Apr 1 | Mar 31 |
| Create new branch for splitting runs and update files as necessary | Complete | Mar 25| Apr 1 | Mar 31 |
| Start working on getting a run with new skip connection changes | Complete | Mar 25| Apr 1 | Mar 31 |
| Clone Alex's fork of emade for nas | Complete | Mar 25| Apr 1 | Mar 30 |


## Week of Mar 11
- Midterms Week!
- We presented first. A link to our slides is [here](https://docs.google.com/presentation/d/1fFlLP0oHFkh8U6w6_8OvzpeOjkqYwEelSHpN5UPXPzE/edit#slide=id.g2c19e5bfa49_0_0)
- Titanic Group 1 + 4
   - The did some pretty interesting things
   - Designed a custom selection algorithm, but also used NSGA2 as well
   - Additionally, they forced EMADE to look at feature data, which should make EMADE run faster, but this was not the case
      - EMADE is designed to deal with a wide array of problems, so forcing a specific problem would lead to less time wasted by having EMADE look for other viable options
- Island Migration
   - Some things they were able to accomplish/work towards for midterms
      - calculating genotypic and phenotypic diversity within an island
      - improve analysis and testing
      - Added to their dashboard that allows them to streamline the testing procedure and get many visualizations of data.
         - Really interesting idea, that maybe our subteam could work towards implement since we are working towards mass runs now
      - Started testing individualized islands
   - Started working on some other datasets: breast cancer, old wine regression
   - For the future they want to compare their data with runs with EMADE since they are currently comparing Island to Island, also they want to continue to test individualized islands.
- Bootcamp 2
   - ML algos: K Nearest Neighbors, Gaussian Naive Bayes, Support Vector Machines, Multilayer Perceptron(grid search to make it work better)
   - MOGP: found that many of the individuals split into two group (individuals either close to bottom of pareto front line or close to top, gap in the middle) Heavy speciation. Tended toward false negative rate
   - MOGP performed better
   - EMADE better at minimizing both FPR and FNR together but still performed worse than MOGP
- Self Driving
   - Main task right now is generating bounding boxes
   - Using Lyft3d Object detection for Autonomous Vehicles as their dataset
   - Used YOLO architecture approach to create a mock primitive to resemble this architecture
   - Evaluation Methods: calculate intersection over union, evaluate_class_accuracy and evaluate object count
   - Developed a docker build to run EMADE and MySQL in a single command.
   - In the future, they are hoping to implement actual YOLO, and more eval functions and get more members on EMADE
- Transfer Learning
   - Able to complete an evo run up to 15 generations
      - used a hernia(8 images) and another disease with 11 images and got perfect results. This is fine due to chance since there are few images to classify.
      - The top 3 classes in their dataset was: No finding, Infiltration, Atelectasis (most data in dataset) they got AUC values for combinations of all of these
   - Data Analysis
      - Pretrained Model: Xception Model had high usage over middle gens but gradually disappeared as mobilenet usage increased
      - They performed their data analysis as looking at count of diff optimizerss, diff pretrained models, diff layers, and diff activation functions usage over generations
   - Future: Hope to get everyone EMADE working, and get model w/ good performance
- LLM and last Bootcamp will present after spring break since we ran out of time.

## Week of Mar 4

### Team Meeting
- Midterms next week from 5pm - 8pm
- Our subteam (NAS) got attention layer working with inception layer. Many of us are having trouble with running our master. Our mating team is working on setting up new objectives such as eval time. We need to come up with a design of experiments
- Self Driving greatly improved docker compose time, started working on their input xml file, and wrote a script to create EMADE based data pairings.
- Transfer Learning was able to successfully run EMADE. For midterms, they hope to get an AUC over generations, and pre-trained models usage.
- Island Migration have uploaded pareto front visualizations on their dashboard, getting XML files for new datasets, and got optimal cut of points for each tree.
- LLM team is still adding in error handling and is looking to run a loop over more generations

### Personal Progress
- I first tried to seed new individuals that we are going to use across all our experiments.
   - Elias ran a full run and took the pareto front individuals of that result and created a seeding file with them.
   - When I tried to run that file, I was getting malformed node errors with seeding
      - This is likely due to something that isn't defined, however I did not find anything
- Attended the Hackathon this week to make a good amount of progress
- I also worked towards fixing my issue with the master process.
   - Initially had the intention of looking into new primitives to add and look into future work
   - However, I started by individually adding seeded individuals to a seeding file: [resnet_small](https://github.gatech.edu/rpatil73/AADImages/blob/main/resnet_small%20(2)). I simply commented them all out and seeded them one by one. Note this was a seeding file that worked fine in the past and got me a full run. After doing this, I ran a full loop to see if anything hopefully changed, and magically it worked! My master started working again.
- Next, I worked on creating a new seeding file that had some of the seeded individuals that were going to be baseline seeds
   - I manually added individuals that worked from our common seeding file. I also added Inception Layer individuals. Here is the completed file: [here](https://github.gatech.edu/rpatil73/AADImages/blob/main/experiment_testing)
   - I plan to use this file for all my runs with the new compile_layerlist
- Next, I worked on incorporating the changes from the test-gen-nnlearner branch.
   - These changes allowed for the initial generation of random individuals will all be valid allowing for a better spread of individuals for generation 0. It adds variance to our runs which is good.
- Additionally, as a subteam we decided to change our objectives to F1 score error and evaluation time. This is because we notices that recall and precision error were always resulting in the same values for individuals and points in our pareto front graph followed a linear trend. For example, here is a pareto front that shows this.
   - <img width="569" alt="Screenshot 2024-03-10 at 8 34 09 PM" src="https://github.gatech.edu/storage/user/67530/files/231f55dc-8205-46b2-bbea-6fc7d6ef3ad3">
   - Thus, I implemented these changes to our objectives on my codebase before starting runs.
- I also got many runs with the compile_layerlist changes with our common seeding file.
   - My first run, only got to generation 4. I checked the slurm out file for the master and after about two hours the parents just continuously failed. The output of my master is as shown below.
      - <img width="504" alt="Screenshot 2024-03-10 at 4 50 50 PM" src="https://github.gatech.edu/storage/user/67530/files/d7f355b0-0cdf-49fd-9c0e-7017a3185a35">
      - Not entirely sure what this means or how I can proceed to fix this, but I figured it was fixable with changes to my evolution parameters.
      - <img width="876" alt="Screenshot 2024-03-09 at 8 41 54 PM" src="https://github.gatech.edu/storage/user/67530/files/d9bc5dbf-3896-4a96-8d63-ae401d005a36">
      - This is what my sql database looked like for this run
      - <img width="325" alt="Screenshot 2024-03-10 at 5 02 00 PM" src="https://github.gatech.edu/storage/user/67530/files/f86ff0d7-0a93-4df7-b964-75af12653a21">
      - This is the pareto front for the run
      - I decided to change my evolution parameters to have an initial pop. size of 5, an elite pool size of 5 and a launch size of 8.
   - Changing these parameters I tried another run and got much better results. Planning to show these for midterm presentations
      - I got a run with 113 generations as shown below
         - <img width="334" alt="Screenshot 2024-03-10 at 4 59 10 PM" src="https://github.gatech.edu/storage/user/67530/files/b687f675-801c-4fa3-9209-d156663263b2">
      - Got a run with 121 runs as well: (Capped it at 100 for postprocessing to keep it constant across subteams)
         - <img width="331" alt="Screenshot 2024-03-10 at 5 00 47 PM" src="https://github.gatech.edu/storage/user/67530/files/1245cbe8-5b9c-4767-b753-6aade8468dfb">
      - Run with 138 generations
         - <img width="330" alt="Screenshot 2024-03-10 at 8 29 05 PM" src="https://github.gatech.edu/storage/user/67530/files/a6cdb184-4423-4bcd-8f60-3729b1258bee">
   - A copy of the postprocessing script to generate these figures can be found [here](https://github.gatech.edu/rpatil73/AADImages/blob/main/get_experiment_data%20(1).py)
      - This file was made by Elias to help us see the AUC between F1 score and evaluation time.

- Worked on creating slides for midterms. Here is the final result of the [slides](https://docs.google.com/presentation/d/1fFlLP0oHFkh8U6w6_8OvzpeOjkqYwEelSHpN5UPXPzE/edit#slide=id.g2c19e5bfa49_0_0)


### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Fix Master Process| Complete | Mar 4| Mar 11 | Mar 9 |
| Get Elias's Seeding File and Add Inception Layer Individuals | Complete | Mar 4| Mar 11 | Mar 9 |
| Refactor objectives in input xml to minimize f1 score error and eval time | Complete | Mar 4| Mar 11 | Mar 9 |
| Perform Runs with new Seeding File | Complete | Mar 4| Mar 11 | Mar 9 |
| Get AUC graphs for runs | Complete | Mar 4| Mar 11 | Mar 9 |
| Incorporate genNNLearner changes to generate successfully evaluating individuals at start of evo | Complete | Mar 4| Mar 11 | Mar 9 |
| Make Slides for Midterms | Complete | Mar 4| Mar 11 | Mar 10 |


## Week of Feb 26

### Team Meeting
- Midterms in 2 weeks
- Self Driving Team successfully dockerized EMADE, created EMADE setup guide on PACE, and found YOLOv3 object detection model.
- Our subteam is working on getting a baseline run to get seeded individuals for all future runs. Aaron recommended incorporating the type of analysis we are planning on pursuing in our midterms.
- Transfer Learning fixed issues with mutation node mismatching and MySQL. They were able to get EMADE working
- Island Migration added island pareto fronts and did a test run, using elbow method for analyzing dendograms, created a combined diversity metric
- LLM changed prompts to be more specific and include more examples, their accuracies are improving


### Personal Progress

- Kevin eventually got a file for seeded individuals based on the original seeding file I sent him. 
   - After receiving this file, I planned on trying to run a loop with these new individuals. I also added some InceptionLayer individuals so that the evolutionary process will pick the InceptionLayer primitive once in a while. You can find this new file [here](https://github.gatech.edu/rpatil73/AADImages/blob/main/resnet_small_new)
   - Unfortunately, only some of these individuals were able to evaluate. I was getting the following error for 3 of the 6 other individuals.
      - ``` One of the dimensions in the output is <= 0 due to downsampling in conv2d_2. Consider increasing the input size. Received input shape [None, 5, 5, 32] which would produce output shape with a zero or negative value in a dimension. ```
      - I plan to use the testing file to edit our compile_layerlist function to hopefully fix this issue.
   - Also, these individuals did take a long time to evaluate. Therefore, it might not be the best seeding file to use for future runs since some these individuals took over 1500 seconds to evaluate.
   - Additionally the master did not seem to run successfully. There were no errors in the master slurm out file, but no new individuals were being created. 
   - <img width="397" alt="Screenshot 2024-03-04 at 2 09 53 PM" src="https://github.gatech.edu/storage/user/67530/files/c4f59ce9-d186-4eb6-b2b5-ea5d8c7e2872">
- Figuring out Master Issue
   - I tried to pinpoint where the master issue was and why it was stalling and not performing evolution
   - After using a series of print statements, I found out that it was stalling at this line in Emade.py
      - ```python   
                 test_data_array = [reduce_instances(load_function(folder, use_cache=use_cache, compress=compress, hash_data=True))         
                                   for folder in self.datasetDict[dataset]['testFilenames']]
      - This confused me because this part of EMADE.py is just dataset setup.
      - Also, this part of the code executes successfully for the worker process so it is not a problem with the dataset. Not quite sure what the issue is.
- Met with Tristan to talk about progress
   - He shared some of the graphs he has been working on for post processing.
      - These include component frequency such as how often a layer is used, tree complexity over generations, acc, prec, recall evaluation.
      - You can find more details at his [notebook](https://github.gatech.edu/emade/emade/wiki/Notebook-Tristan-Jeremiah-Thakur#february-26-2024)
      - The code for these visualizations needs to be cleaned up since it is looking at things we don't want (such as occurrences of a module or the activation function). It would be more valuable to look at the different layer types.
   - Here is the code for creating these graphs: [here](https://github.gatech.edu/rpatil73/AADImages/blob/main/master_csv_viz.ipynb)
   - This is ran locally after downloading the csv. We should probably discuss with the rest of the group about the specific metrics we want to keep track of and transitioning it onto pace rather than it just being local.
       - I plan to clean up this code and also come up with new metrics to look at.
### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Get New Seeded Individuals from Kevin | Complete | Feb 26 |  Mar 4 | Mar 3|
| Add Inception Layer Individuals to new seeding file | Complete | Feb 26 |  Mar 4 | Mar 3|
| Run loop with new seeded individuals and Inception Layer Individuals | Complete | Feb 26 |  Mar 4 | Mar 3|
| Meet with Tristan for progress checks | Complete | Feb 26 |  Mar 4 | Feb 28|
| Clean up some of the postprocessing script code | Complete | Mar 1 |  Mar 4 | Mar 3|

## Week of Feb 19

### Team Meeting
- No team meeting this week since Dr.Zutty and Aaron were unable to make the meeting time.

### Personal Progress
- I decided to come up with some questions that will help direct our splitting team in a direction for midterms. Planning to ask Aaron about these.
   - 1. Should my seeded individuals be of a specific type or quality? For example, should they be all InceptionLayer individuals, no InceptionLayer individuals or a mix of both? Should the seeded individuals be of low quality(high error scores for precision, accuracy, recall)
      - A: Seeded individuals should be good individuals. Be consistent across different runs. These individuals should be pareto front individuals.
   - 2. For midterms, the plan is to create baseline runs and compare them with runs with the changes to compile_layerlist. Should the seeded individuals for both the baseline runs and the runs with the new changes be the same? If so, wouldn't that cause issues for the baseline runs since some of the seeded individuals won't be supported for the baseline runs.
      - A: The seeded individuals should be the same across different runs. The genNNLearner will generate random individuals which will hopefully give InceptionLayer individuals. Our goal is to evaluate the ability to improve on our seeded individuals.
   - 3. Is there a way to continue an evolutionary process after the worker and master has timed out? I have tried to restart the worker and master, but there is no progression in the evolution (no error in the slurm out files also) (also my reuse flag is set to 1)
      - A: Reuse flag should work, it will reset the generation to generation 0.
   - 4. The plan is to perform a various amount of baseline runs and runs with new changes. I currently have a way to get the AUC for each individual run, but how do I combine all of those into one graph for comparison?
      - A: Can use the csv after downloading the table from the run. From here you can get parameters such as hypervolume and pareto fitness scores. We should look into some other aggretation of data such as p values.
   - 5. Would it be valuable to track the number of individuals that have the new InceptionLayer that are on the pareto front for our evo run?
      - I think it would be a good metric to keep track of to see if pareto front individuals use this new primitive

- Decided to setup a meeting with Tristan to do some code review and talk about plans for midterm
   - First, talked about the splitting test file. I explained how the file is setup and how it allows us to test primitives outside of EMADE and doing a full evolutionary run. 
   - Also talked about compile_layerlist code and NNLearner while going through an example of an individual
   - Spent some time talking about plan for midterm
     - Need to ask Aaron some questions
     - I will be doing runs with compile_layerlist changes, while Tristan will do runs with the skip layer and compile_layerlist changes
   - Helped him debug some issues with post processing and the testing file

- Trying to reduce evaluation time:
   - I was hoping to reduce the evaluation time of individuals so I decided to run a little mini experiment.
   - I planned on removing the Flatten Layer primitive from all of our individuals since this could lead to the number of parameters increasing greatly leading to slower evaluation time. 
      - I just removed these individuals from the seeding file and ran another evolutionary run. The pareto front is shown below:
         - <img width="582" alt="Screenshot 2024-03-03 at 8 26 32 PM" src="https://github.gatech.edu/storage/user/67530/files/847226d5-de9a-443d-8f83-3fba44db51c9">
   - There were only 11 generations of individuals and many of the individuals had extremely long running times. This can be seen by the image below:
      - <img width="406" alt="Screenshot 2024-03-03 at 8 25 57 PM" src="https://github.gatech.edu/storage/user/67530/files/97f91398-b885-4d08-a2fc-62d93ddc0fbe">
   - The long individuals did have really good scores for accuracy, precision, and recall but due to them taking so long, the evolutionary process did not happen for long which could result in not very good results.
      - Here are some of the individuals: 
      - The following one took 3780 seconds and gave acc, prec, recall of (0.284, 0.269, 0.284): 
      - ``` NNLearner(ARG0, PassLayerList(DenseLayer(LayerUnit1024, reluActivation, No_Normalization, GlobalMaxPoolingLayer2D(InceptionLayer(mod_36(mod_36(mod_3(InceptionLayer(mod_34(mod_4(Input(ARG1))))))))), NoDropout)), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation)) mod_3: Module(datatype, data_dims, Conv2DLayer(LayerUnit256, reluActivation, KernelSize1, Stride1, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout) mod_4: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize1, Stride1, SamePadding, Batch_Normalization, ARG0)), NoSkipConnection4dim(), NoPooling(), Dropout50) mod_34: Module(datatype, data_dims, SeparableConv2DLayer(LayerUnit64, geluActivation, KernelSize5, Stride1, ValidPadding, Layer_Normalization, SeparableConv2DLayer(LayerUnit256, linearActivation, KernelSize5, Stride1, SamePadding, Layer_Normalization, Conv2DLayer(LayerUnit160, geluActivation, KernelSize5, Stride1, SamePadding, No_Normalization, ARG0))), Conv2DConnection(geluActivation, KernelSize5, Stride2, SamePadding, Layer_Normalization), NoPooling(), Dropout50) mod_36: Module(datatype, data_dims, SeparableConv2DLayer(LayerUnit1024, reluActivation, KernelSize7, Stride2, ValidPadding, No_Normalization, DenseLayer4dim(LayerUnit224, geluActivation, Batch_Normalization, ARG0)), DenseConnection4dim(tanhActivation, No_Normalization), MaxPool2D(PoolSize2), Dropout20)```
     - This one took 2953 seconds and gave acc, pre, recall of (0.294, 0.272, 0.294):
     - ``` NNLearner(ARG0, PassLayerList(DenseLayer(LayerUnit1024, reluActivation, No_Normalization, GlobalMaxPoolingLayer2D(InceptionLayer(mod_36(mod_36(mod_3(InceptionLayer(mod_34(mod_4(mod_1(Input(ARG1)))))))))), NoDropout)), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation)) mod_1: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize1, Stride1, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout) mod_3: Module(datatype, data_dims, Conv2DLayer(LayerUnit256, reluActivation, KernelSize1, Stride1, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout) mod_4: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize1, Stride1, SamePadding, Batch_Normalization, ARG0)), NoSkipConnection4dim(), NoPooling(), Dropout50) mod_34: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit64, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, ARG0))), SkipConnection4dim(reluActivation), NoPooling(), Dropout50) mod_36: Module(datatype, data_dims, Conv2DLayer(LayerUnit256, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit256, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, Conv2DLayer(LayerUnit256, reluActivation, KernelSize3, Stride1, SamePadding, Batch_Normalization, ARG0))), SkipConnection4dim(reluActivation), NoPooling(), Dropout50) ```
     - Later I definitely want to look at why these are taking so long. (Honestly it's probably because they are really big individuals)



### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Figure out answers to the questions numbered above | Complete | Feb 19 |  Feb 26 | Feb 23|
| Edit Seeding File to remove flattenLayer individuals | Complete | Feb 19 |  Feb 26 | Feb 25|
| Test Evo Run without Flatten Layer to improve eval time | Complete | Feb 19 |  Feb 26 | Feb 25|
| Meet with Tristan to talk about midterm & code review | Complete | Feb 19 |  Feb 26 | Feb 21|


## Week of Feb 12

### Team Meeting
- Started with a lecture on statistics in EMADE
   - How to tell if differences are due to randomness in trials or due to a new primitive or addition
   - What our group NAS can do: do x NAS baseline runs and performs statistics on it (mean, variance, standard deviation etc)
      - What can you do with these stats?
   - Hypothesis Testing
      - P(sample | hypothesis) called P-value
      - say we know the mean and standard deviation and we run EMADE 10 times and get a slightly different mean and standard deviation
         - What is the chance that our mean and standard deviation is just a portion of the hypothesis mean and standard deviation
   - We perform a test on the likelihood of observing our mean of 99.7 when our hypothesis is that mean is 100.
      - We compute a t-statistis
      - 1 tail(when null hypothesis "is one mean greater than another") vs 2 tail statistic (show two distributions are not equal (typically stronger))
   - can compute p value from t statistic with python (scipy.stats.t.sf(np.abs(t statistic), degrees of freedom) * 2
      - Tells us there is a p value percentage chance to observe at least a mean of x away from hypothesis
   - Suggested Using Welsh's T-Test for statistics
- NAS successfully got their master working for the InceptionLayer; we are running baseline runs for comparison for midterms; ViT team is working on merging splitting changes
- Self Driving laid out a series of tasks to work on; Got EMADE on Pace but are having setup issues with emade
- Transfer Learning added pre-trained models to their work and changed their naming conventions
- Island Migration added individualized mutation and crossover, new pareto fronts, and normalizing how pareto fronts are added
- LLM team is working on making API calls to codellama

### Personal Progress
- First thing I did this week was to analyze some of the individuals from the full evolutionary run that I ran last week
   - As a reminder, this run was a run with the new compile_layerlist implemented and without the skip layer changes
      - The seeded individuals were individuals that did not contain any IncpetionLayer primitives
   - Looking at the individuals that were under evolution, I noticed that none of the new individuals had the InceptionLayer primitive
      - Led me to think that maybe mutations weren't working correctly, or it was just unlucky that no InceptionLayer individuals were being generated
      - Due to this result, there was no way of making sure that InceptionLayer individuals work in the evolutionary process. So to check this I ran the full evolutionary loop with the new resnet seeding file individuals I made.
   - Here is the pareto front for this run
      - <img width="589" alt="Screenshot 2024-02-17 at 7 29 34 PM" src="https://github.gatech.edu/storage/user/67530/files/a656d8ed-64da-4795-8c1d-a2bffa0a81f4">
- Running evolution on new [resnet seeding file](https://github.gatech.edu/rpatil73/AADImages/blob/main/resnet_small%20(2))
   - The seeded individuals contain both really good performing and really bad performing neural networks
   - After running the full evolutionary run, I could see new individuals being created with the InceptionLayer primitive!
      - For example here is an individual made from generation 5
         - `NNLearner(ARG0, PassLayerList(DenseLayer(LayerUnit1024, reluActivation, No_Normalization, GlobalMaxPoolingLayer2D(InceptionLayer(mod_36(mod_36(InceptionLayer(mod_34(mod_23(Input(ARG1)))))))), NoDropout)), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation)) mod_23: Module(datatype, data_dims, Conv2DLayer(LayerUnit64, reluActivation, KernelSize7, Stride2, ValidPadding, No_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout) mod_34: Module(datatype, data_dims, SeparableConv2DLayer(LayerUnit192, reluActivation, KernelSize5, Stride2, ValidPadding, Layer_Normalization, DenseLayer4dim(LayerUnit160, tanhActivation, Batch_Normalization, SeparableConv2DLayer(LayerUnit1536, linearActivation, KernelSize7, Stride2, ValidPadding, No_Normalization, SeparableConv2DLayer(LayerUnit1536, reluActivation, KernelSize3, Stride2, SamePadding, Batch_Normalization, ARG0)))), Conv2DConnection(linearActivation, KernelSize3, Stride2, SamePadding, Batch_Normalization), AvgPool2D(PoolSize2), NoDropout) mod_36: Module(datatype, data_dims, SeparableConv2DLayer(LayerUnit1280, reluActivation, KernelSize7, Stride2, SamePadding, Layer_Normalization, DenseLayer4dim(LayerUnit1536, tanhActivation, Layer_Normalization, ARG0)), SkipConnection4dim(reluActivation), NoPooling(), Dropout20)`
      - The pareto front for this run came out to be as shown below
         - <img width="608" alt="Screenshot 2024-02-18 at 8 38 11 AM" src="https://github.gatech.edu/storage/user/67530/files/bcfa095a-e23c-4b25-b4e4-5a31cce72b52">
      - The pareto front has a small range of AUC values. This is probably because we seeded well performing individuals. Need to ask about the quality of individuals I should be using for seeding. Also look into the types of seeded individuals to use, such as with or without InceptionLayer.
- Fixing [postprocessing_viz](https://github.gatech.edu/rpatil73/AADImages/blob/main/postprocessing_viz.py) file for visualizing pareto front/ AUC graph.
   - Needed to make some changes to the postprocessing file to get it to work. The bulk of the change was removing some of the old code and adding in the following
      - ```python 
        paretoFrontTable = np.vstack(([[0,0,1],[0,1,0], [1,0,0]], paretoFrontTable))
        # paretoFrontTable = np.vstack(([[0,1],[1,0]], paretoFrontTable))
        print(paretoFrontTable)
        myPareto, isPareto = find_pareto(np.array(paretoFrontTable))
        #myPareto = myPareto[np.argsort(myPareto[:,0])]
        print(myPareto, isPareto)
        #Figures out what tree produced the min-distance point on pareto-front
        myParetoList = myPareto.tolist()
        min_entry = min(myParetoList, key=lambda x: math.sqrt(x[0]**2 + x[1]**2 + x[2]**2))
        for entry in paretoFrontTreeTable:
            if entry[0] == min_entry[0] and entry[1] == min_entry[1]:
                print(entry[0], entry[1], entry[2])
   - Also I chose to parametrize the number of generation for the loop in our postprocessing script so that other members can simply just run the file without having to manually change values. 
      - ```python
        max_gen = con.execute('Select max(evaluation_gen) from individuals')
        max_gen = max_gen.fetchone()[0]
   - Also better understood how connections are made. The connection statement is brokendown as follows:
      - ```python
        #//<user>:<mysql_password>@<mysql_node_host>:<mysql_port>/<mysql_schema>
        engine = create_engine('mysql+pymysql://rpatil73:patil@atl1-1-02-003-19-1:3073/stocks')
      
### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Long Term Goal: Get Full Evolutionary Run with InceptionLayer Primitive | Complete | Jan 29 |  Mar 11 | Feb 12|
| Fix PostProcessing File to correctly make Pareto Front | Complete | Feb 12 |  Feb 19 | Feb 17|
| Analyze Individuals from full evo run with no InceptionLayer seeded individuals | Complete | Feb 12 | Feb 19| Feb 14|
| Run Full Evolutionary Loop with InceptionLayer Seeded Individuals | Complete | Feb 12 |  Feb 19 | Feb 16|
| Plot Pareto Front for evolutionary runs | Complete | Feb 12 |  Feb 19 | Feb 17|

## Week of Feb 5

### Team Meeting
- Dr.Zutty talked to us about two goals/experimental procedures that we should focus on throughout the semester
   - 1. Have a seeded run and try and beat that run with our improvements/changes
   - 2. Start with a baseline and show how our changes improve the baseline run.
   - We will be performing the second with NAS. We will have the old NAS team's full evolutionary loop from last semester as the baseline run. Then, we will try and combine all of our subteams and perform another evolutionary run to show improvements.
- Self Driving
   - They decided to work on incorporating object detection into EMADE.
   - Using YOLOv7, and want to eventually incorporate this into EMADE.
- NAS
   - ViT branch merged with splitting since they are planning on using some of the splitting work I worked on last semester.
   - Our mating/mutating team is working on getting an environment setup for testing mating and mutating outside of full evo runs
- Transfer Learning
   - Fixed their terminal mismatching issue
   - Having issues with connection to MySQL
- Island Migration
   - Having bugs with individual island selection
- LLM
   - Made prompts to ask LLM. Found out issues were with initial population.

### Personal Progress
- First, since I have been struggling with getting my master to work, I wanted to make sure that the issue isn't with just my computer, or if it is an issue with the code. To check for this I chose to run a full evolutionary loop with our old NAS code(the same runs as the baseline runs Kevin is working on).
   - Thankfully, I was able to get a full evolutionary run with the reverted code which means my issue wasn't with my system, but it was with something that was changed.
- After figuring that out, I worked on trying to get my master to work if I got rid of all the skip layer changes, thinking that the issue was with these changes. 
   - Took me a while to comment out all the skip layer changes
   - Was getting some issues with skip layer, even though everything was commented out
      - This ended up being an issue with one of the seeded individuals. Fixed it by changing the connection to a Dense or Conv connection
   - Eventually, I was able to get the master working after removing the skip layer changes!
      - This run was with seeded individuals that did not have the new InceptionLayer primitive
      - We can see that the generations are increasing
      - <img width="655" alt="Screenshot 2024-02-20 at 2 06 35 PM" src="https://github.gatech.edu/storage/user/67530/files/c7ffb87a-1fb9-4160-b68f-7ee9d701edcf">
- Plan for midterms
   - Since I was able to get the evolutionary run working, I was thinking about what we should present for midterms
   - I think getting our baseline runs without any modifications is the first step
   - Then, I was planning on running runs with the new modifications to compile_layerlist and look into how these change the overall results
   - After talking with Tristan, I found out his master worked with the changes to compile_layerlist to support splitting AND the changes to skip layer. So, I think getting runs with this will also be good to show for our midterms.

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Long Term Goal: Get Full Evolutionary Run with InceptionLayer Primitive | Complete | Jan 29 |  Mar 11 | Feb 12 |
| Test Evolutionary Run without SkipLayer Changes | Complete | Feb 5 |  Feb 12 | Feb 11 |
| Come up with plan for midterms for InceptionLayer side | Complete | Feb 5 |  Feb 12| Feb 11 |
| Sanity Check: Test master with old compile_layerlist | Complete | Feb 5 |  Feb 12 | Feb 11 |

## Week of Jan 29

### Team Meeting
- NAS shared our updates with the rest of the group
   - GenNNLearner team had a hacky fix for generating individuals that had appropriate dimensions
      - Just keep retrying until a valid individual was generated (There is a cap on this)
      - Aaron gave a suggestion about using LazyConv
   - Attention Team is adding Hugh since disbanding stats subteam
   - InceptionLayer team seeded and evaluated individuals successfully and is now going to work on getting a full run.
- Self Driving found eval function and a list of potential primitives and object detection models
- Transfer Learning is looking into SQL connection issues and documentation for a type mismatching problem
- Island migration had some bugs with individualized migration and are also looking into dynamic migration
- LLM is performing a lit review on increasing diversity other than their pool of prompts

### Personal Progress
- Adding/Updating New Primitive Testing File
   - Like mentioned in previous week updates, there were some errors with our testing file. 
   - These errors were resolved.
   - I spent some time this week adding documentation to this file so that other parts of our team can use the file to test new primitives in the future as the file gives a way to test primitives outside of performing a full evolutionary loop or seeding individuals.
   - Also cleaned up some of the code to make it more readable
   - Here is what the file looks like now: [New Primitive Testing](https://github.gatech.edu/rpatil73/AADImages/blob/main/splitting_test_dup.py)
     - I tried pushing this file to our github repo, but was facing an issue with locking support and bad object error. We might have to make a new github repo.
       - <img width="1156" alt="Screenshot 2024-02-05 at 4 18 50 PM" src="https://github.gatech.edu/storage/user/67530/files/0f46f614-c5bc-4e4f-859e-5167579b7d9f">

- Attempting to get an evolutionary run (Testing what's wrong)
   - First I tested running the master file with the seeded individuals from last week
      - I got the following output from the master file
      - <img width="1015" alt="Screenshot 2024-02-06 at 4 05 33 PM" src="https://github.gatech.edu/storage/user/67530/files/33b526fb-685f-47fd-9c2c-594e0aa5ba68">
      - This message continued repeating throughout the entire file
      - There was no issue that stopped the master file from running (It ran the full 8 hours)
      - However, no new individuals were being created during the evolution process. My SQL Database just had the original seeded individuals and the 5 new generated individuals from the start of the evolution.
      - Looking at the message from the slurm out file, It repeats that there were too many values to unpack. 
         - I have gotten this error before in regards to compile_layerlist. This is because this function was changed to return 3 variables rather than 2. [Here](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/src/GPFramework/neural_network_methods.py) is a reminder of the function (lines 1535-1730).
         - This leads me to believe that the issue is with a call to compile_layerlist somewhere, but I'm not sure where.
   - With the output from above, I wanted to check whether the same would hold when I only seeded individuals that had the InceptionLayer primitive
     - Unfortunately, the same result occurred.
   - Next, I needed to make sure that the evolutionary run still works without the new primitive, so I tested the evolutionary run with only seeded individuals that were known to work and didn't have the InceptionLayer primitive.
      - I got a similar output in my slurm file, where the master ran the entire time, but no new individuals/generations were being created.
      - <img width="1010" alt="Screenshot 2024-02-06 at 4 16 49 PM" src="https://github.gatech.edu/storage/user/67530/files/fff432dc-c621-4c4c-853a-25a35ed5bcfd">
      - Now, I am really confused as to were the issue is, but I have a good feeling that it has to do with the call to compile_layerlist.
   - Next week, I will further test by removing the skiplist changes, reverting compile_layerlist to the old version, and other modifications to truly find the issue.

- I talked with Tristan about some tasks that he could work on.
   - Tasked him with trying to seed and evaluate individuals on his end (Sent him my seeding file)
      - He was having issues with this last semester
   - Worked with him to fix a few errors. Will continue next week and hopefully get him caught up by next week.


- Quick Literature Survey to determine new things we could work on
   - During my literature search, I came across DropPath which we could look into implementing later.
      - Will probably look into research papers on this later.
   - Additionally, parallelizing our models rather than having them being serial can be more beneficial to our NAS



### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Long Term Goal: Get Full Evolutionary Run with InceptionLayer Primitive | Complete | Jan 29 |  Mar 11 | Feb 12|
| Add Documentation to New Primitive Testing File | Complete | Jan 29 |  Feb 5 | Feb 4 |
| Literature Survey on NAS | Complete | Jan 29 |  Feb 5 | Feb 3 |
| Test full evo run with seeded individuals from last week | Complete | Jan 29 |  Feb 5 | Feb 1 |
| Test full evo run with only InceptionLayer Individuals | Complete | Jan 29 |  Feb 5 | Feb 2 |
| Test full evo run with no InceptionLayer Individuals | Complete | Jan 29 |  Feb 5 | Feb 3 |
## Week of Jan 22
### Team Meeting
- We shared each teams individual updates with the entire group.
   - NAS
     - We are continuing our Literature Survey on NAS
     - Sai is planning on adding convolutions to attention primitive for evolution
     - Elias is leading the mate/mutate team, but first fixed genNNLearner
     - Further talked about getting rid of the stats subteam temporarily
       - Talked with Aaron about this, and he gave some ideas about what the team could do if it continued
   - Self Driving
      - Self Driving found a dataset they could use for their problem
      - Also are planning on splitting into 3 subteams for their work
         - They haven't decided who is on which subteam, but will do so later in the meeting
   - Transfer Learning
      - Will continue their work from last semester
   - Island Migration
      - They are continuing their leftover work from last semester and are partitioning tasks among people
   - LLM
      - The team dropped down to just 1 member now
      - They were able to run their loop and get good results.
- Each team was tasked with answering 6 questions that helped us formulate goals and organization of teams for the semester
   - We all shared our answers to these questions

### Personal Progress
- Getting the Primitive Testing File Working:
   - I continued trying to get this file working.
   - One error I encountered was the following
     - <img width="627" alt="Screenshot 2024-01-30 at 6 24 50 PM" src="https://github.gatech.edu/storage/user/67530/files/6fca620e-29c2-4805-8952-4c07345ab685">
     - This error was related to returning 3 values from compile_layerlist
     - I fixed it by adding a new variable to account for skip_lists
        - ```python
                    curr_layer, input_layers, skip_list = nnm.compile_layerlist(layerlist, [], data_dims, datatype)
   - This along with some other changes got the testing file to work again!

- Seeding New Individuals
   - I created new individuals that contain the Inception Layer as well as individuals that didn't
     - I added these to the resnet_small seeding file
   - Here is my master resnet file with all the individuals that I am using for seeding/evaluation: [commit](https://github.gatech.edu/rpatil73/AADImages/blob/main/resnet_small%20(2))
     - Also created new modules
   - Here are the individuals populated in the database:
     - <img width="1054" alt="Screenshot 2024-01-30 at 6 36 38 PM" src="https://github.gatech.edu/storage/user/67530/files/78e70fef-7a28-460a-a510-657495bea08e">
     - They were successfully parsed and inserted into the db

- Evaluating Individuals:
   - After running the command to run the worker process, I was able to successfully evaluate these seeded individuals from above
   - Here is the outputs for accuracy, precision, recall and the evaluation times
     - <img width="637" alt="Screenshot 2024-01-30 at 6 39 22 PM" src="https://github.gatech.edu/storage/user/67530/files/70a56053-87b2-4c3f-b530-1a293c00b5d5">
     - <img width="460" alt="Screenshot 2024-01-30 at 6 39 45 PM" src="https://github.gatech.edu/storage/user/67530/files/71484af8-4a81-4d95-bd31-9bfb6c8ca1f9">
   - You can see that some of our individuals are performing really well
     - This is because some of these individuals were created by Tristan who modeled them after research papers that have good neural networks for image classification
   - Some of the individuals take a very long time to evaluate as you can see in the image
      - This could be an issue during the full evolutionary run since the master process will only run for a set amount of time and it getting stuck on large individuals could lead to fewer epochs which would hurt the overall NAS


### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Literature Survey on NAS | Complete |  Jan 22 |  Feb 5 | Feb 4 |
| Get Concatenation Primitive Testing File Working | Complete |  Jan 22 |  Jan 29 | Jan 28 |
| Successfully seed new individuals with the inception layer| Complete |  Jan 22 |  Jan 29 | Jan 28 |
| Successfully evaluate new seeded individuals| Complete |  Jan 22 |  Jan 29 | Jan 28 |

## Week of Jan 8
### Team Meeting
- Started with Dr.Zutty talking about midterm and final presentation dates
- Talked about whether teams are planning on continuing or not
   - NAS will continue!
- Each team gave a brief overview of where their current work is and what they do
- For the next two weeks, as a group we want to be able to answer the following questions
  - What problem are you trying to solve?
  - What is the data you will evaluate your algorithms against?
  - What algorithms currently exist to solve the problem? How well do they do?
  - How will you break down the problem into tasks for your group?
  - What does success look like for this semester?
  - How and when will your subteam meetings take place?
### Personal Progress
- My personal answers to these question:
  - 1. We are trying to evolve neural networks with a neural architecture search approach that uses evolution to develop new neural networks. We will use EMADE as the evolutionary algorithm.
  - 2. We are using CIFAR10 which is a very popular image classification dataset that categorizes images into 10 different categories. A potential future goal could be to extend our Neural Architecture Search to stock and other data.
  - 3. Currently NAS is done using reinforcement learning, evolution, and bayesian optimization to name a few.
  - 4. We are forming subteams to handle different parts of our problem. Currently we have an attention subgroup, a branching subgroup, a mate/mutate group, and a stats subteam. These subgroups are led by Sai, me, Elias, and Kevin respectively.
  - 5. Success this semester comes in many forms. More generally, however, hopefully we will be able to run a full evolutionary loop with all our subteams combined together.
  - 6. We will be meeting on Fridays at 4:30 pm. This will be an online meeting over zoom.
- We also made a document for our shared answers to these questions. It is at near the top of [this document](https://docs.google.com/document/d/1qrdqzRk_D_n78UIUH5o12ZS4pLSsO9c097KT5zAWLXU/edit#heading=h.8ky0tzrk2e3j)

- First step was to check if the scratch and github repo was still intact
   - Thankfully everything was still there!
     - I had a backup of scratch saved on my local computer, but luckily didn't need it
   - Also, Tristan's github still exists so the plan is to continue to work of a branch on that repo
   - However, when I started testing some of my old files from last semester, some things had changed which was weird. This is reiterated below.

- Working on Fixing our InceptionLayer testing file
   - When I ran our InceptionLayer testing file, I got several errors that did not occur last semester, leading me to believe some things changed from last semester. Below are errors and my fixes. [Here is the file](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/splitting_test_dup.py) for reference.
     - <img width="924" alt="Screenshot 2024-01-30 at 3 52 27 PM" src="https://github.gatech.edu/storage/user/67530/files/75075c56-7c26-42a1-a1e8-0b774a489ee8">
       - This was the first error I got when running the file. It indicates that one of the individuals I was testing was not represented appropriately as a string.
       - I realized that the individual I was testing incorporated a FlattenLayer which we got rid of last semester.
       - I brought this primitive back just to make sure this was the only error but it was not. So for now I chose to keep flatten layer. Initially, we chose to get rid of flattenLayer since it adds a lot more trainable params to our model that slowed down evaluation significantly.
    - I was still getting the error above after fixing FlattenLayer. I checked my nn_pset for modules to see what modules exist and below is an image depicting this.
       - <img width="942" alt="Screenshot 2024-01-30 at 3 57 39 PM" src="https://github.gatech.edu/storage/user/67530/files/8cac3a93-24f8-41cd-8874-a797f2237207">
       - Notably, two of the modules that were created for testing individuals last semester, mod 32 and mod 45 are no longer in the pset.
       - So the nn_pset changed from semester to semester.
       - I fixed this, by adding in the old modules to our global mods file with code in lines 115-162 of the [testing file](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/splitting_test_dup.py).
    - Still had more errors that I will work on fixing next week.

- Thinking about future goals for the semester
   - I was thinking that actually getting a full evolutionary run with the InceptionLayer primitive is one of the first things that we should be working on this semester.
   - Additionally, we want to fix/make sure our mating and mutating functions still work appropriately.
   - Want to look into better upsampling and downsampling techniques to better keep our matrix data. Right now, we just add padding or use tf.resize to make our tensor's dimensions appropriate for concatenation and splitting.
     - A better technique should allow for a better score for precision, accuracy, and recall for our individuals during our NAS
   - Another potential goal is to add a new addition primitive that instead of concatenating will add the individual values within a matrix.
      - Instead of [x, x] concat [x, x] = [x, x, x, x], we would have a primitive that would do the following: [x, x] add [x, x] = [2x, 2x]
   - Also, I think being able to bring all of our subteams together by the end of the semester would be amazing
      - Currently, we are working on seperate things, but if we can find a way to connect all of our subteams for a full evolutionary run that incorporates all of our subteams, that would be ideal.


### Subteam Meeting - Jan 12
- Our first subteam meeting of the semester
- Discussed the progress that was made at the end of last semester
- We also talked about what are some potential goals for the semester
- Started answering the 6 questions for our problem of Neural Architecture Search

### Subteam Meeting - Jan 19
- We didn't have a full group meeting on Monday due to Holiday, but we still got together as a subteam that Friday.
- We discussed some of our issues that our sub subteams were having
   - I was having issues with our primitive testing file that wouldn't evaluate Inception Layer individuals
   - Elias had some issues with genNNLearner, but he knew how to fix it. It was a quick fix in regards to generation of individuals.
- Talked about potentially disbanding our stats subteam since they don't have much data to work with at the moment. We will bring back this team after we have gotten useful data.

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Answer the above questions for NAS | Complete |  Jan 8 |  Jan 22 | Jan 12 |
| Fill Out LettuceMeet to determine NAS meeting time| Complete |  Jan 8 |  Jan 12 | Jan 10 |
| Think about and come up with goals for the semester | Complete |  Jan 8 |  Jan 22 | Jan 14 |
| Regain/Setup github repo for our work | Complete |  Jan 8 |  Jan 22 | Jan 14 |
| Work on the getting our concatenation testing file working | Complete|  Jan 19 |  Jan 29 | Jan 28|

# Fall 2023

## December 8
### Final Presentation Notes
- We(NAS) presented first and overall, it went well
- Engagement Detection
   - Their Problem: video content isn't engaging for education so they wan't to detect engagement
   - Using DAISEE Dataset
      - Issues: Diversity, Age, and Gender
   - They gave us background on RNN's and LSTM's which they are using in their problem
   - Their Model:
      - Input: 10 sec video clip
      - Apply CNN in parallel to split up frames from video clip
      - Pass that through an LSTM
      - Apply Dense Layers to get final prediction
   - Performed Literature Surveys on Labeling Methods (For subjects and videos) that can be relevant to engagement detection
   - Integration into EMADE
      - Integrating Dataset into EMADE: made a python file to use a ternary classification for labeling of data
   - Using Mean Absolute Error and Quadratic Weighted Kappa methods for evaluation
   - Added Needed Primitives to EMADE
      - LSTM, Dense Layers, Embeddings and a pre-trained VGG Net model
   - Results: model was severely overfitting
      - They set up a team to deal with finding out why and how to resolve this
   - They worked on converting Shuvo's model to keras
   - Future Steps: running keras model in emade,  testing primitives, convert runner.py file to Keras
- Island Migration
   - Technique to create better evolutionary algorithms
   - Their work this semester
      - Created dashboard to see real time pareto front plots
      - Implemented framework for individualized islands
         - Figured out how to have separate objectives for islands, separate psets and separate toolboxes
         - Used a wrapper for a selection function. Take out objectives that don't matter. Then use NSGA2 selection on other objectives.
         - Individualized mating/mutating
      - Implemented phenotypic and genotypic measures
         - phenotypic: partition population according to fitness value
         - genotypic: find distance between different string representations
   - With 4 Individualized Islands, migration starts around 30 or 50(two runs) which is where diversity spikes
   - Used Levenshtein distance calculation to determine diversity score for genotypic
   - Individualized Vs Normal Islands
      - Towards end of generation, Individualized just drops off while Normal has multiple individuals on pareto front toward end
      - AUC for Normal was much lower
   - Want to bring everything that everyone worked on together next semester
- Transfer Learning
   - Goal: Beat CheXNet's results
   - Tensorflow Model Results
      - Very similar results with training loss of 1.7 and validation loss of around 0.2
   - Another thing they were working on was debugging standalone tree evaluator
      - debugging auc_score, output dimension, and model string
   - Dataset Changes
      - Pace(Old): grayscale images, single labeling, int
      - Jupyter: RGB images, multilabel, decimal
   - Future of TL: adding new primitives and pretrained models and parametrize more variables
   - Added EfficientNet and ConvNeXt as pretrained models
      - Added Resnet and Xception as well
- LLM Integration
   - Using LLM to create custom algorithms
   - Using CodeLlama
   - Using the Cifar10 Dataset
   - They have downloaded the 34B CodeLlama model
   - They created a basic GP loop
   - When combining models, codellama would simply fit model 1, fit model 2 then add their scores together
      - They didn't want this
   - They created a DNN models GP loop that is functional with mating, mutation and initialization
      - Models created by this loop were mostly just multiple dense layers. One of the models was a sequential layer with two of these dense layers
   - Their models sort of converge to one value in the end
      - Mean accuracy slowly improves over generations while variance in accuracy decreases over generations
   - They also set up a cifar 10 loop and ran it to get results
- Stocks
   - Problem: Bitcoin price ternary classification problem
   - Main tasks after midterm is scraping more data for sentiment analysis and tweaking FinBert to take in more news data
   - Used new HFT Data which tells price and quantity for the best ask and bid prices at timestamps
   - New Primitives
      - Average Three: compute over a longer range to get better prediction
      - Average True Range: Technical Analysis Indicator to measure market volatility
      - Parabolic Stop and Reverse: good indicator of entry and exit points and stock loss placement(stock sell at price)
      - Smoothed Relative Strength Index: momentum indicator that measures speed and change of price movements
      - Triple Exponential Moving Average: trend following indicator that reacts quickly to price changes
      - Relative Volatility Index: degree of variation of price of a stock
   - Data Modifications
      - take blocks of 6 and have window of 40 periods looking back for those blocks of 6
      - Using past observations as features
      - Added a sentiment score(doesn't work right now)
   - Symmetric Thermal Optimal Path Method
      - Ideal for news headline stock data
      - Designed to analyze lead-lag relationship between time series data
   - Results(reduced from ternary to binary problem due to time):
      - obtained over 1500 individuals
      - AUC of 0.459465
   - Created new dataset with 1st order difference
      - Resulted in AUC of 0.3189
     


## Week of Dec 4
### Team Meeting
- Class decided to skip scrums today and turn it into a work day.
- Unfortunately wasn't able to allocate a GPU node so wasn't able to test my code
- I did however, start on some tasks
   - I am going make our concat primitive be able to support multiple modules with different dimensions when concatenating
   - Started writing out the code for this in neural_network_methods.py
   - Here is the Code(I still need to test if it works, but this will hopefully work):
```python
            max_dim = max([layer.shape[1] for layer in output_layers])
            max_dim = max([layer.shape[1:3] for layer in output_layers])
            print("max_dim", max_dim)

            # Loop through each output layer
            for i, layer in enumerate(output_layers):
                # If the layer's dimensions are smaller
                if layer.shape[1] < max_dim:
                    # Calculate the difference
                    shape_diff = max_dim - layer.shape[1]

                    # Determine the padding
                    if shape_diff % 2 == 0:
                        # Can add symmetric padding
                        padding = shape_diff // 2
                    else:
                        smaller = int(np.floor(shape_diff / 2))
                        padding = ((smaller, smaller + 1), (smaller, smaller + 1))

                    # Add padding to the layer
                    output_layers[i] = ZeroPadding2D(padding=padding)(layer)
```



### Personal Progress
- To allow our concat primitive to work for multiple layers I tested the code above and modified to make it work. I wrote the following code which now works for the concat primitive when output_layer dimensions do not match.
   - Currently the fix was to use padding to modify smaller dimensions to match the larger dimension
   - We should change this to some better upsampling method later(padding only adds in 0's which is not ideal). Could be a next semester task
   - We want to use some other method that will add better information in the upscaling
   - Key points in the code below:
      - first finding the layer with the greatest dimension sizes(just using width * height to determine this)
      - looping through each output layer and adding ZeroPadding2D to each that needs more padding
```python
            max_area_layer = max(output_layers, key=lambda layer: layer.shape[1] * layer.shape[2])
            print(max_area_layer.shape)
            print("Layer with greatest dimensions: ", max_area_layer)
            max_width = max_area_layer.shape[1]
            max_height = max_area_layer.shape[2]
            print("Max_Width:", max_width)
            print("Max_Height:", max_height)

            # Loop through each output layer
            for i, out_layer in enumerate(output_layers):
                # If the layer's dimensions are smaller
                if out_layer.shape[1] < max_width or out_layer.shape[2] < max_height:
                    # Calculate the difference in width and height
                    width_diff = max_width - out_layer.shape[1]
                    height_diff = max_height - out_layer.shape[2]

                    # Determine the padding for width
                    if width_diff % 2 == 0:
                        # Can add symmetric padding
                        width_padding = (width_diff // 2, width_diff // 2)
                    else:
                        smaller = width_diff // 2
                        width_padding = (smaller, smaller + 1)

                    # Determine the padding for height
                    if height_diff % 2 == 0:
                        # Can add symmetric padding
                        height_padding = (height_diff // 2, height_diff // 2)
                    else:
                        smaller = height_diff // 2
                        height_padding = (smaller, smaller + 1)
                    padding = (width_padding, height_padding)
                    # Add padding to the layer
                    output_layers[i] = ZeroPadding2D(padding=padding)(output_layers[i])
```
- Testing different individuals
   - Testing concat individual with three modules
      - ```"NNLearner(ARG0, PassLayerList(FlattenLayer(concat_test(mod_46(mod_45(mod_32(Input(ARG1))))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))"```
         - This individual compiled and evaluated completely fine which is great to see
      - ```"NNLearner(ARG0, PassLayerList(FlattenLayer(concat_test(mod_32(mod_46(mod_32(Input(ARG1))))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))"```
         - This individual compiled, but failed to evaluate due to mod_46 changing the ouputsize resulting in a mismatch of output to input shape when putting the data through to the next layer. I fixed this by adding in a downsampling and upsampling method to match height and width. The code is below:
         - <img width="958" alt="Screenshot 2023-12-05 at 5 31 58 PM" src="https://github.gatech.edu/storage/user/67530/files/b3842713-2575-4cbb-b40c-fefe0191ad25">

         - ```python

           for i in range(1, n):
                x = splits[i - 1]

                # If the height or width doesn't match, adjust the size
                if x.shape[1:3] != layer[i].input_shape[1:3]:
                    height_diff = layer[i].input_shape[1] - x.shape[1]
                    width_diff = layer[i].input_shape[2] - x.shape[2]
                    print("expected input shape:", layer[i].input_shape[1:3])
                    # If the size of x is larger, downsize it using MaxPooling2D
                    if height_diff < 0 or width_diff < 0:
                        x = tf.image.resize(x, layer[i].input_shape[1:3])
                        print(x)
                    else:  # If the size of x is smaller, add padding
                        height_padding = (height_diff // 2, height_diff - height_diff // 2)
                        width_padding = (width_diff // 2, width_diff - width_diff // 2)

                        x = ZeroPadding2D(padding=(height_padding, width_padding))(x)

                # If the channels don't match, use 1x1 convolution
                if x.shape[-1] != layer[i].input_shape[-1]:
                    x = Conv2D(layer[i].input_shape[-1], 1)(x)

                x = layer[i](x)
                output_layers.append(x)
   - Tested individuals with modules after the concat primitive
      - ```"NNLearner(ARG0, PassLayerList(FlattenLayer(mod_45(concat_test(mod_32(mod_32(Input(ARG1))))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))"```
      - ```"NNLearner(ARG0, PassLayerList(FlattenLayer(mod_46(concat_test(mod_32(mod_32(Input(ARG1))))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))"```
      - I was able to compile and evaluate these individuals!!!
   - I also tested individuals without concat primitives to make sure those still work and they did
- [Here](https://github.gatech.edu/tpeat3/emade/commit/051cfc1fa654245f9f3a5221a3ca8eb84be6f52a) is the commit I made for the changes mentioned above
- Next step was to add this concat primitive to EMADE.
   - I did this by adding the ConcatLayer definition to neural_network_methods.py and adding the primitive in gp_framework_helper.py.
   - [Here](https://github.gatech.edu/tpeat3/emade/commit/c69c852cdeda2400935f08bc405820f565f0cf8f) is the commit that shows this
      - I initially added the primitive to the addADFPrimitives method in gp_framework_helper.py
         - This caused the seeding of individuals to fail
         - It works when I added the primitive to the addNNLearnerPrimitivies method instead (since this successfully adds the primitive to the correct pset)
- When trying to run a full evolutionary run I was unsuccessful
   - I was able to successfully seed and evaluation individual that were concatenated individuals(some good individuals below)
      - <img width="470" alt="Screenshot 2023-12-08 at 7 26 57 PM" src="https://github.gatech.edu/storage/user/67530/files/142f3fc3-b518-4965-bd02-968f2e0cf76e">
   - My master failed when running the full evolutionary run and didn't have a fix
- Created my presentation slide for finals. 
   - Going to talk about splitting and concatenation
### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Test Concat Primitive with >2 modules | Complete |  December 4 |  December 8 | December 5 |
| Broader testing of concat primitive | Complete |  December 4 |  December 8 | December 5 |
| Add concat primitive to EMADE | Complete |  December 4 |  December 8 | December 6 |
| Use Concat in full evolutionary run | Incomplete|  December 4 |  December 8 | December 8 |
| Allow for output_layers dimensions to be modified so concat will work | Complete |  December 4 |  December 8 | December 5 |
| Create Presentation Slide for Final | Complete |  December 4 |  December 8 | December 7 |

## Week of Nov 27
### Team Meeting
- We shared our subteam progress
- Our subteam completions:
   - we added a healing function to support our concat primitive
   - patch embedding was added to EMADE and works
   - genNNLearner now generates individuals with NNLearner but now a seperate issue arose
      - there are shape mismatches that are causing issues
- Our subteam tasks in progress:
   - We still need to test our concatenation primitive with more modules
   - we want to fix skip connections
       - want them to skip back a variable amount within our list
   - hopefully combine the ViT with the splitting of a tensor work we accomplished within EMADE
- Other teams are continuing to make progress on their respective tasks
   - Stocks is working on new member Pace setup, HFT group is trying to get EMADE runs, NLP is working on running EMADE with integrated stocks data
   - Engagement Detection almost done with Keras conversions, Shuvo's model is working now, and they added more primitives to repo(LSTM, Dense Layer, etc)
   - Island Migration is data preprocessing and is working with Dash(frontend framework)

### Personal Progress
- This week, when I ran the [splitting_test_dup.py](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/splitting_test_dup.py) file, I was still able to compile a concatenated individual but was getting an error when evaluating the concatenated individual.
   - Error: It seems that TensorFlow's XLA compiler was unable to find the libdevice. (Weird since it was working find before)
   - <img width="1060" alt="Screenshot 2023-12-03 at 10 42 35 AM" src="https://github.gatech.edu/storage/user/67530/files/ffcb418e-6949-4761-a0ef-621548d5dabd">
   - I fixed it by first finding verifying that CUDA was actually installed
      - ```nvcc -version```
   - Then, I found where the libdevice was
      - ```echo $CUDA_HOME```
      - from here you can cd into nvvm/libdevice to find the actual libdevice
   - Then, I set the XLA_FLAGS variable to point to correct CUDA directory
       - ```export XLA_FLAGS=--xla_gpu_cuda_data_dir=/path/to/cuda```
       - ```export XLA_FLAGS=--xla_gpu_cuda_data_dir=/usr/local/pace-apps/spack/packages/linux-rhel7-x86_64/gcc-4.8.5/cuda-11.7.0-7sdye3id7ahz34mzhyzzqbxowjxgxkhu```
   - This resolved my error and allowed me to evaluate individuals again
- I performed much more testing of the concat primitive
   - I tested different modules and different parameters within layers
- When I was testing the concatenation primitive I found an issue when concatenating the following modules:
   - ```mod_32: Module(datatype, data_dims, Conv2DLayer(LayerUnit32, reluActivation, KernelSize1, Stride1, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout)```
   - ```mod_46: Module(datatype, data_dims, Conv2DLayer(LayerUnit32, reluActivation, KernelSize5, Stride2, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout)```
   - The issue was that the concatenation primitive requires matching shapes for concatenating
      - <img width="1349" alt="Screenshot 2023-12-03 at 9 19 36 PM" src="https://github.gatech.edu/storage/user/67530/files/3f4b7ce9-3901-42b8-aab6-30c90a2f912f">
   - I fixed this by adding padding to the smaller module dimension to match the input of the larger module dimension
      - This is the [commit](https://github.gatech.edu/tpeat3/emade/commit/1c007bf0fcb8c503412b7692f933feae0197d130)
      - I specifically added ZeroPadding2D. Currently it only will work for concatenating two modules. Later we can update this to take in a variable amount of modules and add padding to all of them to concat them.
      - Here is my code modifications:
```python
if output_layers[0].shape[1:3] != output_layers[1].shape[1:3]:
    print("outputs[0].shape[1:3] ", output_layers[0].shape[1:3])
    print("outputs[1].shape[1:3] ", output_layers[1].shape[1:3])
    dims = [output_layers[0].shape[1], output_layers[1].shape[1]]
    lower = np.argmin(dims) # add padding to smaller shape
    if lower == 0:
        shape_diff = output_layers[1].shape[1] - output_layers[0].shape[1]
    else:
        shape_diff = output_layers[0].shape[1] - output_layers[1].shape[1]
    print(shape_diff)
    if shape_diff % 2 == 0:
        # can add symmetric padding
        padding = shape_diff//2
    else:
        smaller = int(np.floor(shape_diff/2))
        padding = ((smaller, smaller+1), (smaller, smaller+1))

    if lower == 0:
        output_layers[0] = ZeroPadding2D(padding=padding)(output_layers[0])
    else:
        output_layers[1] = ZeroPadding2D(padding=padding)(output_layers[1])
```
- With this modification I was able to evaluate a concatenated individual that uses the two modules above. Here is the output:
   - <img width="1369" alt="Screenshot 2023-12-03 at 9 28 05 PM" src="https://github.gatech.edu/storage/user/67530/files/7df8b723-d8be-4231-8644-2a82cade97a6">


### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Further Test Concatenation Primitive | Complete |  November 27 |  December 4 |  December 4  |
| Update Concatenation Primitive to work for more modules | Complete  |  November 27 |  December 4 |  December 3 |
| Research Attention Primitive and better understand how it works | Complete  |  November 27 |  December 4 | December 2 |
| Test Concatenation Primitive in evolutionary run | Incomplete  |  Dec 1 |  December 8 |  December 8  |


## Week of Nov 20
### Team Meeting
- Our subteam accomplishments are as follows(We shared these with the entire group)
   - Brandon was able to add multihead attention which sai is going to be testing
   - The two Tristan's and I worked on updating compile_layerlist in nnm to support splitting
   - genNNLearner was fixed and now individuals that are generated have a NNLearner on it
   - Kevin created graphs for visualizing diversity among individuals
   - New members are still working on getting setup on pace and being able to seed and evaluate individuals
- Transfer Learning is still struggling with EMADE runs since their test classes are not properly being loaded. They are also getting new members onboarded.
- Engagement Detection finished their Citi Training modules
- Island Migration are continuing to get more members' EMADE working and have made progress in the different parts of their analysis(Genotypic diversity, Phenotypic Diversity, Visualization, etc)
- Stocks' HFT team switched branches and are setting up new members on PACE. NLP team is fixing issue with Finbert to process more data.

### Personal Progress
- Testing Concatenation Primitive
   - I tested the concatenation with new and different modules. (More work needs to be done on this next week)
   - Found issues with modules that contain connections. For example below are two that gave errors:
      - ```mod_22: Module(datatype, data_dims, ARG0, Conv2DConnection(tanhActivation, KernelSize3, Stride1, SamePadding, No_Normalization), NoPooling(), NoDropout)```
      - ```mod_15: Module(datatype, data_dims, ARG0, DenseConnection4dim(geluActivation, No_Normalization), AvgPool2D(PoolSize2), NoDropout)```
      - The error was as shown below: 
         - From what I understand, it is an issue with skip connections
         - Specifically, it fails with finding the layer index with the activation function.
         - This is an issue we need to fix for concatenation as well as attention and addition
      - <img width="972" alt="Screenshot 2023-11-27 at 5 18 50 PM" src="https://github.gatech.edu/storage/user/67530/files/1cd444c9-701a-4fdd-aded-bfe54194b33b">

   - Works for dense layer and conv2d layer modules
      - For example with the following individual and modules I was able to get the following summary
```
Got Individual:  NNLearner(ARG0, PassLayerList(FlattenLayer(concat_test(mod_45(mod_33(Input(ARG1)))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))
mod_33: Module(datatype, data_dims, Conv2DLayer(LayerUnit32, reluActivation, KernelSize1, Stride1, ValidPadding, Batch_Normalization, ARG0), NoSkipConnection4dim(), NoPooling(), NoDropout)
mod_45: Module(datatype, data_dims, DenseLayer4dim(LayerUnit32, tanhActivation, No_Normalization, DenseLayer4dim(LayerUnit1280, geluActivation, No_Normalization, SeparableConv2DLayer(LayerUnit2048, reluActivation, KernelSize1, Stride2, ValidPadding, Batch_Normalization, DenseLayer4dim(LayerUnit256, reluActivation, No_Normalization, ARG0)))), DenseConnection4dim(geluActivation, Batch_Normalization), NoPooling(), Dropout20)
```
<img width="1289" alt="Screenshot 2023-11-27 at 5 14 50 PM" src="https://github.gatech.edu/storage/user/67530/files/bc9633fe-9115-45d5-8085-095324f5e882">

- Getting Rid of Hard Coding in Tensor Splitting
   - Context: Within compile_layerlist(), I was currently using a hardcoded value for the channels of our input tensor. This hardcoded value would be what our input tensor would be healed to in order to support splitting. For example, with the code below, I had new_c set to 6, so when I pass in a concat individual with two modules being concatenated, it would first heal the input tensor to (32,32,6) from (32,32,3) and then split the tensor into two subtensors which will be passed into the two layers(modules).
```python
n = len(layer)
# c must be divisible by n when dividing into l
c = curr_layer.shape[-1]
if c % (n - 1) != 0:
   new_c = 6
   # heal shape by 1x1 conv to divisible output dim
   curr_layer = Conv2D(new_c, 1)(curr_layer)
print("curr_layer: ",curr_layer)
print("curr_layer_shape: ",curr_layer.shape)
splits = tf.split(curr_layer, n - 1, axis=-1)
```
   - To fix this I created a new function to calculate the closest divisible number that can be divided evenly into the number of layers that we will pass each subtensor to and then healed our tensor to that number. Here is the [commit](https://github.gatech.edu/tpeat3/emade/commit/ab4fcdec27b7094fe36a02799bc016a945f55bed)
```python
def closest_divisible_number(c, n):
    return c if c % n == 0 else c + n - c % n
```
   - Updated Code:
```python
n = len(layer)
# c must be divisible by n when dividing into l
c = curr_layer.shape[-1]
if c % (n - 1) != 0:
   new_c = closest_divisible_number(c, n-1)
   print("new_c: ", new_c)
   curr_layer = Conv2D(new_c, (1, 1), padding='same')(curr_layer)
splits = tf.split(curr_layer, n - 1, axis=-1)
```

- Meeting About Next Steps
   - Talked with Tristan Peat and Tristan Thakur about overall next steps and progress
   - Talked about my changes to compile_layerlist, neural_network_methods, and the new python file mentioned above and in the previous weeks notes
   - Future Steps:
      - Getting Concat working in a full evolutionary run and more testing
         - Probably going to be really funky with how mutations work and how it will work with attention. We need to look into this further
      - Adding in and Add primitive
         - This will work like concat except instead of adding to the end of the layerlist, it will modify the tensors directly(add)
         - This will involve a lot of dimension checking and healing which can cause our models to become really messy with all the healing
         - We need to look into changing our space
             - Downsampling: (Ex. (32x32 to 8x8))
                - MaxPooling, Average Pooling, Conv2d, DenseConnection
             - UpSampling: (Ex. (8x8 to 32x32))
                - Conv2dTranspose
      - Goal for finals:
          - Try and get a full vision transformer
          - Use the splitting that we made to choose the keys, queries, and values for attention
          - Ultimately, try and bring all our subteams together with our progress

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Test Concatenation Primitive with different Modules | Complete  |  November 20 |  November 27 |  November 22  |
| Meet about next steps regarding entire group coming together | Complete  |  November 20 |  November 27 |  November 27   |
| Get rid of the hard coding for healing input tensor | Complete | November 20 | November 27 | November 23 |


## Week of Nov 13
### Team Meeting
- Everyone shared their subteams progress throughout the week
   - Our subteam's completions:
      - Patch embedding was added to attention primitive by Sai
      - Tristan and I setup framework for new tree evaluator so we can work on splitting
      - New member are getting setup on EMADE/PACE(4/5 members)
      - Attention branch merged with overall nas23 branch
      - Currently working on getting multiheaded attention added
   - Engagement Detection met with Shuvo and Shuvo provided tasks to complete for everyone(exploring primitive, eye detection algo, etc)
   - Stocks' HFT team is writing scripts to convert HFT data. NLP team is scraping stocks data and sentiment data. They are still working on Pace/EMADE installation.
   - Transfer Learning having issues with SQL, and running EMADE. New members for them are setting up MySQL.
   - Island Migration is updating emade-viz repo, figuring out how to extract individuals to apply genotypic diversity algo, and researching adding topologies.


### Personal Progress
- Here is the file that I made: 
- I pulled changed and tried to get splitting_test.py to work on my end
   - Issue: When creating a module, the name has to be unique otherwise it error
   - Was able to get model.summary() to show for new modules and individuals that used these modules
- Adding Concat Layer primitive to pset
   - Accomplished this with the following code I added
   - Pushed a new file to test concatenation primitive called [splitting_test_dup.py](https://github.gatech.edu/tpeat3/emade/commit/889849f74b05c7d22f0237125c188bb8f8ddbd36) to the splitting test branch
```python
def ConcatLayer(*argv):
    empty_layerlist = nnm.InputLayer()
    concatlist = [Concatenate(axis=-1)]
    # slice over by 1 to avoid "input"
    for arg in argv:
        concatlist += arg.mylist[1:]
#     concatlist = concatlist + arg.mylist[1:] for arg in argv
    empty_layerlist.mylist.append(concatlist)
    return empty_layerlist


ll = nnm.InputLayer()
ll =  nnm.DenseLayer(3, nnm.Activation.RELU, nnm.Normalization.NONE, ll)
ll = nnm.Conv2DLayer(3,  nnm.Activation.RELU, 1, 1, 'valid', nnm.Normalization.NONE, ll)
# add concat layer
ll = ConcatLayer(ll)
print(ll.mylist)


ind2 = "NNLearner(ARG0, PassLayerList(FlattenLayer(concat_test(mod_32(mod_32(Input(ARG1)))))), AdamOptimizer, ImageAugmentation(data_dims, NoFlip, NoRotation, NoZoom, NoTranslation))"
# add concat layer to nn pset
pset.addPrimitive(ConcatLayer, [nnm.LayerListM], nnm.LayerListM, name='concat_test')
pset.context.update({'concat_test': ConcatLayer})

nn_pset_info = get_pset_info(pset)
# print(nn_pset_info['primitives'].keys())
# print(nn_pset_info['primitives']['concat_test'])

concat_func, i = parse_tree(ind2, nn_pset_info)

# construct a deap primitive tree and individual from the given list
concat_tree = gp.PrimitiveTree(concat_func)
concat_individual = creator.Individual([concat_tree])
```

- Testing Concat Primitive and Individual:
   - There were issues with our compile_layerlist method when splitting our tensor
      - Fix was to create helper method to calculate correct number of channels to split our tensor correctly
      - For now this value is hardcoded
   - Issue: Dimension for input to modules was giving an error(image shown below)
      - To fix this, I sort of had a hacky solution that checks the expected input size and had a healer(which was just a 2DConv) that would get our tensor to be the correct dimension.
<img width="1000" alt="Screenshot 2023-11-19 at 7 59 30 PM" src="https://github.gatech.edu/storage/user/67530/files/08d28908-14ba-48e9-b031-478f2b924eac">

   - Fix to compile layer list shown below
```python
if (x.shape[-1] != layer[i].input_shape[-1]):
    x = Conv2D(layer[i].input_shape[-1], 1)(x)
    print("Healed x:", x)
x = layer[i](x)
```

   - I was able to compile a concatenated individual and got the following summary for the individual
<img width="1125" alt="Screenshot 2023-11-19 at 8 03 32 PM" src="https://github.gatech.edu/storage/user/67530/files/0298885f-9c22-466f-8593-357d41ee8e83">



### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Get splitting_test.py file working | Complete  |  November 13 |  November 20 |  November 14   |
| Add Concat Layer primitive to pset | Complete  |  November 13 |  November 20 |  November 15   |
| Update Neural Network Methods with new compile_layerlist to support splitting | Complete | November 13 | November 20 | November 17 |
| Test Concatenation Primitive and get model.summary() for concatenated individual | Complete  |  November 13 |  November 20 |  November 18 |





## Week of Nov 6
### Team Meeting
- Set up hackathon time for finals
- Stocks Updates
  - Did new member onboarding at a high level
  - Currently having issues with setting up on pace (conda env issues, and permissions errors)
- Engagement Detection
  - Shuvo tasked their group with new tasks such as building out a model for extracting information from the webcam
- Transfer Learning
  - Fixed their GPU issue, and made setup guide for PACE
  - They are running standalone and have overfitting issues
- Island 
  - started working on island topologies
  - researching genetic diversity measures
- Our Teams Updates(NAS):
  - Tristan and I setup a python file to test splitting and concatenation
     - Added code to compile_layerlist to support splitting
  - Brandon made PR for attention block primitive
  - Kevin continuing to research more metrics we can use for statistics
  - Elias still working on fixing genNNLearner
- Shared our teams updates with the rest of the group as well

### Personal Progress

- Setting up jupyter notebook
  - I had some issues with making sure the kernel was set up with my conda environment
     - Resolved this with the following commands
     - ```conda install -c anaconda ipykernel```
     - ```python -m ipykernel install --user --name=nas```
- Tristan created a jupyter notebook file to test primitives and splitting: [jupyter notebook](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/spliting_pset.ipynb)
   - Currently doesn't work entirely
   - I updated some of the code to run appropriately.
      - Modifications include appropriate ordering of commands and additional additions from EMADE. An example is listed below
```python
glob_mods = {}
# load Global_MODS file (will always exist because we've run emade.create_representation)
with open("Global_MODS", "rb") as mod_file:
    glob_mods = dill.load(mod_file)
    
print(glob_mods)
```

- Compiling a Module and seeing model.summary() for it
   - I first implemented print statements within the jupyter notebook to understand how modules work currently
   - I created a python file for understanding how to hard compile a module (linked below).
       - [module_compilation_test](https://github.gatech.edu/rpatil73/AADImages/blob/main/mod_21_compiling_test.py)
   - With that, I implemented changes to the jupyter notebook file to compile a module.
       - Currently the module compiles as a whole rather than the specific layers in a module
          - The parameters and trainable params match so this is correct as shown below. I am working to make the summary show specific layers.
       
<img width="500" alt="Screenshot 2023-11-13 at 5 32 44 PM" src="https://github.gatech.edu/storage/user/67530/files/8b173957-aaee-4a73-bb7c-1ced71ff4b1a">
<img width="490" alt="Screenshot 2023-11-13 at 5 33 03 PM" src="https://github.gatech.edu/storage/user/67530/files/1ebffb26-701e-4b10-9de7-58abb309da11">


   - Below is the specific code I made for this:

```python
#compile a module
#print(glob_mods['mod_22'][1][0])
tree = glob_mods['mod_26'][1][0]
func = gp.compile(tree, mod_pset_info['pset'])
print(tree)
layerlist = func(nnm.InputLayer())
layers, _ = nnm.compile_layerlist(layerlist, [], data_dims, datatype)
reshape = np.subtract(data_dims, layers.shape[1:])
my_mod.reshape = reshape

model = Model(inputs=_, outputs=layers, name=mod_name)
model.summary()
```
- Adding a Concat Primitive
   - Added the following to add concatenate layer to pset. Still need to check that it works as we want it to work.
```
pset.addPrimitive(nnm.ConcatenateLayer, [nnm.LayerList, nnm.LayerList], nnm.LayerList, name='ConcatenateLayer')
```

-Here is the updated jupyter notebook file with all of my changes: [splitting test](https://github.gatech.edu/rpatil73/AADImages/blob/main/spliting_pset.ipynb)


### Subteam Meeting Notes:

- New members will be trying to seed an individual by Monday
- Current members continue working on respective tasks
- Everyone shared their current progress

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Test split_test.py with real primitives from GPFramework(jupyter notebook) | Complete | November 6   | November 20  |  November 20  |
| Understand how modules are added to pset | Complete    | November 6   | November 13  |  November 7   |
| Try and compile a vanilla module | Complete  | November 6   | November 13  |  November 12 |
| Add a concat primitive to pset | Complete  | November 6   | November 13  |  November 9  |

## Week of Oct 30
### Team Meeting
- New members joined NAS
  - Made tasks for new members to work on
- Tristan and I are working on implementing a cell-block-branch structure to our models
- Brandon and Sai are working on getting the attention to work
- We realized early stopping is not helping that much
- Everyone shared subteams updated progress with the entire group
  - Stocks working on installation errors. They are planning on having an onboarding meeting with new members
  - Engagement Detection is working with Shuvo who gave them a model to work with. 
  - Island Models is planning on supporting more islands, bettering metrics for genotypic and phenotypic diversity, and implementing individualized islands
  - Transfer Learning still working on GPU issue and created documentation for implementing transfer learning in EMADE.

### Personal Progress
- Review [split_test.py](https://github.gatech.edu/tpeat3/emade/blob/splitting-test/splitting_test.py)
  - This is a file that Tristan created that created a new implementation of compile_layerlist which allows for splitting a tensor
  - I added new print statements and other modifications to better understand the code
  - Redefinition of compile_layer_list to support splitting up a layerlist
    - takes in layerlist that looks like ```['input', [<keras.layers.core.dense.Dense object at 0x7ffff0adb5e0>, <keras.layers.convolutional.conv2d.Conv2D object at 0x7fffdc1c3250>, <keras.layers.core.activation.Activation object at 0x7ffff0ad7220>]]```
    - creates InputLayer() for 'input' and splits tensor into 3 tensors for the dense, conv2d and activation layers. Then concats back together.
- Here is the code for split_test.py with my changes
```python
import GPFramework.neural_network_methods as nnm
import tensorflow as tf
from tensorflow.keras import Model
from tensorflow.keras.layers import Input, Dropout, Concatenate

data_dims = [32, 32, 3]
datatype = 'imagedata'

"""
Custom layer list to support branching

"""
def compile_layerlist(layerlist, input_layers, data_dim, datatype, isNNLearner=False):
    curr_layer = None
    for layer_index, layer in enumerate(layerlist):
        if isinstance(layer, list):
            """
            Design choice, anytime there is a nested list
            [combining function, mod1, mod2, ...]
            """
            print(curr_layer)
            n = len(layer)
            splits = tf.split(curr_layer, n, axis=-1)
            output_layers = []
            for i in range(n):
                x = splits[i]
                x = layer[i](x)
                output_layers.append(x)
            print(output_layers)
            curr_layer = Concatenate()(output_layers)
        else:
            if isinstance(layer, tf.Tensor):
                input_layers.append(layer)
                curr_layer = layer
            
            # Handle input/output layer
            if isinstance(layer, str):
                if layer == 'input' and curr_layer == None:
                    s = data_dim # input shape is (32, 32, 3) for images
                    if (len(s) == 2):
                        s = (s[0], s[0], 1)
                    new_layer = Input(shape=s)
                input_layers.append(new_layer)
                curr_layer = new_layer
            else:
                if curr_layer == None:
                    curr_layer = layer
                    input_layers.append(layer)
                else:
                    if isNNLearner and type(layer) == keras.engine.functional.Functional:
                        layer = change_model(layer, curr_layer.shape)
                    curr_layer = layer(curr_layer)
    return curr_layer, input_layers


def change_model(model, new_input_shape):
    # replace input shape of first layer
    model.layers[0]._batch_input_shape = new_input_shape

    # rebuild model architecture by exporting and importing via json
    new_model = keras.models.model_from_json(model.to_json())
    #new_model.summary()

    # copy weights from old model to new one
    for layer in new_model.layers:
        try:
            layer.set_weights(model.get_layer(name=layer.name).get_weights())
        except:
            print("Could not transfer weights for layer {}".format(layer.name))

    return new_model

def add_dropout(ll):
    ll.mylist.append(Dropout(0.5))
    return ll

def add_identity(ll):
    layer = tf.keras.layers.Activation('linear')
    ll.mylist.append(layer)
    return ll

"""
Main tests
"""

def get_sequential():
    ll = nnm.InputLayer()
    ll =  nnm.DenseLayer(32, nnm.Activation.RELU, nnm.Normalization.NONE, ll)
    ll = nnm.DenseLayer(64, nnm.Activation.RELU, nnm.Normalization.NONE, ll)
    return ll

def get_branched():
    ll = nnm.InputLayer()
    # split and goes two ways (nested lists)
    ll2 = nnm.LayerList()
    ll2 =  nnm.DenseLayer(3, nnm.Activation.RELU, nnm.Normalization.NONE, ll2)
    ll2 = nnm.Conv2DLayer(3,  nnm.Activation.RELU, 1, 1, 'valid', nnm.Normalization.NONE, ll2)
    ll2 = add_identity(ll2)
    ll.mylist.append(ll2.mylist)
    return ll

def get_concat():
    ll = nnm.InputLayer()
    ll = nnm.ConcatenateLayer(ll)
    return ll

ll = get_branched()

print(ll.mylist)

curr_layer, input_layers = compile_layerlist(ll, [], data_dims, datatype)
print(curr_layer, input_layers)

model = Model(inputs=input_layers, outputs=curr_layer)

model.summary()

# batched tensor of datadims shape
x = tf.random.uniform([1, 32, 32, 3])
# print(x)

output = model(x)

# print(ll.mylist)
```

### Subteam Meeting Notes
- Check in with new members progress
  - Currently we have them getting set up on pace
    - Cloning repo, setting up conda env, setting up sql
- Shared what new members are working on

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Review split_test.py | Complete    | October 23    | November 6  |  November 4 |
| Better understand EMADE pset and mod_pset generation | Complete | October 23    | November 6  |  November 6 |

## Week of Oct 23
### Team Meeting
- Midterm Presentations
- Transfer Learning
  - Utilizing a pre-trained mature model as a starting point
  - Using DenseNet1212 as Base Model
  - Created new Primitives (densenet121)
  - Still Working to get everyone's emade working
  - Looking to seed DenseNet121 Model they trained and compare results
- Group 4 Titanic
  - Used Random Forest, Logistic Regression, Neural Network, SVM, K nearest for ML
    - 0.32 AUC
  - MOGP
    - AUC of 0.177
  - Got AUC of 0.1999 for EMADE
    - 55 generations
- Engagement Detection
  - Problem: Take in a segment of time that determines how engaged a student is with learning content
  - Using the DAISEE dataset: 9000 video sequences from 112 unique individuals
- Group 3 Titanic
  - ML: Gaussian Naive Bayes, SVM, Random Forest, Stochastic Gradient Descent, Gaussian Process Classifies, MLP Classifier
    - AUC of 0.22
  - MOGP: Loosely Typed, NSGA2 Selection
    - AUC of 0.11
  - EMADE
    - AUC of 0.17
- Stocks
  - Exploring a new model: FinBERT(pre-trained transformer based-model)
  - Looking at High frequency multiorder data
  - Made new primitives: Spread Cross Indicator, Kurtosis Measures, etc
- Titanic Group 2
  - ML Models: Gaussian Naive Bayes, Gaussian Process Model, etc
    - AUC: 0.28
  - MOGP: NSGA2 Selection, Node Replacement, Strongly Typed, Constrained Tree Height
    - AUC: 0.109
  - EMADE: Ran 160 generations
    - AUC: 0.16
- Group 1 Titanic
  - ML Models: Random Forest, Ridge Classifier, MLP, etc
  - MOGP: AUC of 0.106
- Island Migration
  - Pros: Divide and Conquer, Global Diversity
  - Last year had a migration model but it was a rounded approach
  - Planning on testing migration topologies
  - Levenshtein distance calculation between individuals
- LLM Integration
  - Using Cifar10 dataset
  - Want to have LLM do the genetic processes
  - Next steps: Better Prompts, completing the GP Loop, Dealing with LLM predictability, Data Preprocessing in LLM, Correct Error Handling
- Team 5 Titanic
  - Hyperparameter Tuning
    - Used GridsearchCV
  - MOGP: Selection SPEA2
  - MOGP performed better than ML
  - EMADE: ran for 81 generations, AUC of 0.299
  - MOGP < EMADE < ML

### Personal Progress
- Currently reviewing EMADE code to better understand emade
  - Specifically looking into compile layer list and the different kinds of layers.
- Was working towards better understanding how compile_layerlist works outside of EMADE
  - My understanding is that an individual is represented as a layerlist and compile_layerlist will take that layerlist and implement the actual components of the individual in the form of layers.
  - Here is the code that I used to better understand this function:
```python
import GPFramework.neural_network_methods as nnm
import tensorflow as tf
from tensorflow.keras import Model

data_dims = [32, 32, 3]
datatype = 'imagedata'

ll2 = nnm.InputLayer()

ll = nnm.InputLayer()
ll2 =  nnm.DenseLayer(32, nnm.Activation.RELU, nnm.Normalization.NONE, ll2)
ll = nnm.DenseLayer(32, nnm.Activation.GELU, nnm.Normalization.NONE, ll)

ll = nnm.ConcatenateLayer(ll, ll2)

print(ll.mylist)
print(ll2.mylist)

curr_layer, input_layers = nnm.compile_layerlist(ll, [], data_dims, datatype)
input_layers[1] = input_layers[0]
print(curr_layer, input_layers)

model = Model(inputs=input_layers, outputs=curr_layer)
model.summary()

x = tf.random.uniform(data_dims)
print(x)

output = model(x)

print(ll.mylist)
```
  

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Play around with layerlists outside of emade | Complete   | October 23    | October 30 | October 28 |
| Better Understand the code behind EMADE(seeding_from_file, etc.) | Complete   | October 23    | October 30 | October 27 |
| Understand how compile_layerlist currently works | Complete   | October 23    | October 30 | October 27 |

## Week of Oct 16
### Team Meeting
- Shared our progress with the rest of the group
  - Overall, most people were able to run a full evolutionary run
     - Elias and I are able to run for many generations
     - Sai is dealing with an error
  - Going to start splitting up tasks to individual people

### Personal Progress
- Understanding Cell, Branch, Block Structure.
  - Planning on having our branches be layer lists, blocks will contain multiple branches. These branches combine through a combination function to create a larger layer list and pass that through to the next block. Image below depicts this.
  ![Image](https://github.gatech.edu/rpatil73/AADImages/blob/main/Screenshot%202023-10-23%20at%209.51.31%20PM.png)

### Subteam Meeting Notes
- Met to talk about Cell, Branch, Block Structure and possible implementation for it.
  - Issues with Layer Splitting that we will probably be working on for the next couple of weeks

### Hackathon
- Had a hackathon to finish our presentation and further discuss individual tasks

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Make Midterm Presentation        | Complete       | October 16    | October 23    | October 22    |
| Better Understand Cell, Block, Branch Structure | Complete       | October 16    | October 30    | October 22    |

## Week of Oct 2
### Team Meeting
- Shared our team's progress with the rest of the group
- Performed code review looking at outputs from running an evolutionary loop and different individuals.
   - Learned how NNLearners work
   - Learned about changes to PaceDebug branch

### Personal Progress
- I have generated new individuals and created new modules for individuals
  - Modified activation functions, and other parameters for modules
- Successfully ran a full evolutionary loop
  - Something I noticed is that after a number of generations, the individuals that are chosen are very similar in the mod sets that are used.
  - Probably need to diversify the modules even more to obtain even better results
  ![AUC Graph](https://github.gatech.edu/storage/user/67530/files/fced71bb-b8e3-4faf-8c99-87b8cb42a0ec)

### Subteam Meeting Notes
- Met with the team to discuss progress and outline next potential steps
- Looked at potential things for team members to do and made a list for things to do
- Tristan made a file to connect to the SQL database and create an AUC curve from the run
  - Goal is to perform this run and obtain an AUC graph

### Self Evaluation Fall 2023
[Link to Notebook Self Evaluation](https://drive.google.com/file/d/1iouvI7sLrToDDFZfWAsLGLeKS88_uenD/view)

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Create Pareto Front for evolutionary run | Complete       | October 2     | October 16    | October 15    |
| Run a full evolutionary loop after creating new individuals and modules | Complete       | October 2     | October 16    | October 12    |
| Complete Peer Evals              | Completed      | October 2     | October 5     | October 4     |

## Week of Sep 25
### Team Meeting
- Shared our teams' progress with the rest of the group
- Talked a bit about future goals and things that need to be done by next week
  - Successfully evaluate an individual
- We need to setup time for code review with Tristan so we can understand the current code

### Personal Progress
- Seeding an Individual
  - Found out that I was not on the master branch instead of nas23, causing template errors
    - Switched to the correct branch and downloaded appropriate zip files for the train and test datasets and was able to seed an individual.
  - Command after sallocing a GPU node and importing necessary modules:
    - python src/GPFramework/seeding_from_file.py templates/input_cifar_rpatil73.xml resnet_small
- Evaluating an Individual
  - Successfully evaluated an Individual
  - Command:
    - python src/GPFramework/launchEMADE.py templates/input_cifar_rpatil73.xml -w
- Next Steps: Run a full evolutionary loop

### Subteam Meeting Notes
- Some possible things to work on
  - Run on cifar10 dataset without EMADE
  - Parametrize the memory limit variable
    - Currently, hard-coded value for memory but want to parametrize and add to the XML file to maybe insert as a param
- Went through some of the seeding_from_file code

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Seeding an Individual | Completed  | September 18  | September 29 | September 28  |
| Evaluate a seeded Individual | Completed  | September 18  | September 29 | September 28  |

## Week of Sep 18
### Team Meeting
- Shared our teams' progress with the rest of the group
- Tristan made some changes to the nas23 branch which we need to clone
- Going to be trying to get individuals from the Seeding_From_File.py file
- Our team got everyone connected to pace and most people can run titanic
- Other teams are having trouble connecting to mysql workbench
### Personal Progress
- Cloning Tristan's nas23 fork
  - Setup
    - Successfully set up all the necessary files and ran bash reinstall.sh successfully.
  - Seeding an Individual: python src/GPFramework/seeding_from_file.py templates/input_cifar_rpatil73.xml resnet_small
    - Error: ImportError: cannot import name 'img_to_array' from 'keras.preprocessing.image' (/home/hice1/rpatil73/.conda/envs/nas/lib/python3.9/site-packages/keras/preprocessing/image.py)
      - Fix: Change keras.preprocessing.image to tensorflow.keras.utils in GPFramwork/data.py
    - Error: lxml.etree.DocumentInvalid: Element 'cacheConfig': This element is not expected. Expected is ( datasets )., line 17
- Read the following [paper](https://arxiv.org/abs/1902.02390) on RNNs which led me to do more research on what RNN's are and how they are used

### Subteam Meeting Notes
- No subteam meeting this week

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Clone new nas23 branch into Pace | Complete       | September 18  | September 29 | September 19  |
| Read Paper on RNNs              | Complete       | September 18  | September 25 | September 19  |

## Week of Sep 11
### Team Meeting
- Learned about the different team's progress for the last 2 weeks
- Had some time to debug errors with Aaron
  - Apparently had only read access to old emade directory that I was trying to delete
    - Aaron helped give edit access and then was able to delete the directory
      - Command was chmod -R 777 emade
      - and then to remove was rm -rf emade
    - Freed up around 6 GB of space, allowing me to get started with setting up a conda environment

### Progress
- Fixed error with tensorflow not finding GPU Node
  - There was an issue with deleting the conda environment resulting in corrupted files from the CUDA install
  - Correctly deleted the conda env and redid everything but got it to work
- Successfully ran Titanic with some changes
  - Changed input_titanic file with appropriate params
  - Made some other changes to ignore the exclude nodes feature

### Subteam Meeting Notes Friday, Sep 16
- Gave personal updates
- Talked about next steps
  - Creating a fork and cloning into the scratch directory
  - Read Research Paper by Monday
    - Evolutionary NAS for RNN-like models
- Had a debugging session in order to run Titanic after the meeting
  - Unfortunately no progress with running Titanic at the debugging meeting
  - Later after the meeting figured out the error and got Titanic running.

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Continuing Literature Survey on Technologies that we might need for NAS | Complete | September 11 | September 18 | September 17 |
| Setup Conda Environment          | Complete       | September 11  | September 16 | September 15 |
| Run Titanic                      | Complete       | September 11  | September 16 | September 17 |

## Week of Aug 28
### Team Meeting
- Learned about Shuvo's engagement detection project
  - Challenges Faced
    - Image vs Video Recognition
    - Noisy/Improper Labeling
    - Unbalanced Datasets
  - Process
    - Take in frames from a video snipper
    - Pass frames through a frame-wise feature attraction
    - Then pass through temporal network and generate a prediction
- Made new subteams with members
  - I joined the NAS subteam
    - We chose to continue to use the stocks dataset for our data
    - Planning on doing a literature survey before next time we meet

### Progress
- Set up MySQL connection to connect to a new node
  - Created Bash Script File to set up MySQL (script provided by Tristan Peat)
    - Then run chmod  +x dbsetup.sh and then ./dbsetup.sh to run the shell file
    - Then run sbatch launchMysql.sbatch which will run the sbatch script created and start a MySQL server instance
    - Next Establish Connection Params (Image below)
      - MySQLHostName obtained from running squeue -u rpatil73
      - Port obtained from launchMysql.sbatch file
- Overall, steps I have completed on getting a successful Titanic run so far
  - Cloned emade into the scratch directory
  - Set up SQL connection to connect to a new node
  - Got errors with space issues when creating my conda environment
  - Still need to free up more space and run Titanic

### Subteam Meeting Notes
- Learning about current code
  - Instead of q table use machine learning
  - We are creating neural networks and using a loss function
  - Input: n stocks by num features (currently 6 - open, close, loopback window, etc)
  - Output: vector of weights of the problem (weights that add to 1)
  - Setup of what an NN learner looks like below
    - Primative: DenseLayer
    - LSTMLayer: time series data

![Screenshot](https://github.gatech.edu/storage/user/67530/files/4d72d6d4-6d13-4b9f-8a59-1e31c6ecfae1)

- Current tasks: Get everyone fully set up on emade
- Semester Goals: expand the capabilities of NNLearner (Get rid of modules which will allow us to mutate, come up with new architectures, and skip connections)

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Literature Survey on Technologies that we might need for NAS | Complete | August 28 | September 11 | September 10 |
| MySql Setup for connecting to a new node | Complete | August 28 | September 11 | August 29 |

## Week of Aug 21
### Team Meeting
- First VIP Meeting of Fall 2023!!!
- Discussed new possible subteams
  - Pipelines, LLM, NAS, Image Processing, Scoliosis, Stocks, DevOps, Island Migration, Transfer Learning
  - Personally, going to stick with Stocks and look a bit into NAS
- Reviewed new changes to PACE-ICE
  - Now on SLURM instead of PBS
  - New ssh command: ssh &lt;GT_username&gt;@login-ice.pace.gatech.edu
  - Increased Nodes and GPUs on PACE
- Met briefly with stocks subteam to talk about possible goals and tasks
  - Discussed increasing data sets

### Action Items
| Task                            | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------------|----------------|---------------|--------------|---------------|
| Try to run Titanic on new PACE  | Complete       | August 21     | September 16 | September 17 |

# Spring 2023
## Week of April 24th

### Team Meeting

- This is finals week.
- We have our final presentation on April 28th.
  - New members will talk about issues and problems they have encountered with setup, while existing members will talk about their progress.
- At the team meeting, I tried to set up a remote connection.
  - First, I needed to get the remote development extension on VSCode.
    - This prompted me to sign in to Github, which I was unable to do with my Github Enterprise account, so I connected my personal account.
    - Next, there should be a green button on the bottom left of VSCode where you can establish a remote connection.
    - From there, you click "connect to host" and enter the SSH command to get into PACE.
    - It will prompt you for your password, but once you do so, you should be able to open files in PACE in VSCode.
- Now that I have a remote connection set up, my next step is to set up a MySQL connection by obtaining my Port ID from running InstallEMADE.

### Finals Presentation Notes

#### Scoliosis

- Main goal is to determine cobb angle from images quickly and accurately.
- Used the Vertebra-Focused Landmark Detection for Scoliosis Assessment research paper in their experiment.
- Evaluation functions were based on Symmetric Mean Squared Error and Mean Squared Error.
- Still using Azure.
- Used AASCE and Shriner's dataset.
- 3 Main Layers: Resnet, DecNet, Decoder.
- Constructed their own version of NNLearner.
- Also recreated the model in Keras and compared it to the PyTorch model.

#### DevOps

- Objectives: Simplify, Reliability, and Unification of EMADE processes.
- Initially sent out a survey to gather user opinions on EMADE installation.
- Created a GitHub repo for a centralized place for all DevOps materials.
  - Contains M1 installation scripts and other guides.
- EMADE installation on WINDOWS.
  - Created a video for installation.
  - Hope to develop a script that will download everything for EMADE in the future.
- Also made updates to installing EMADE on M1.
- Made a file transfer guide for transferring files to PACE-ICE using FileZilla.
- Made a MySQL guide with instructions on installation, making schemas, and remote connections.
- Created a Git Guide for installation, authentication, and using git.
- Goals for the future include overall unification by cleaning up the EMADE GitHub, creating new unit tests, and implementing new labs for boot camp members.

#### Image Processing

- Tries to solve the identification of 14 different diseases as well as X-rays using genetic programming.
- Uses AUCROC as their evaluation method.
- Used ChestX-ray 14 dataset, which includes many images of 14 pathologies.
- Focus of this semester was to use transfer learning to improve their performance.
  - Problems with high accuracies and low AUCs.
    - Can be fixed with changes to Augmentation, Architecture, Class Weights, and Loss Function.
- Research modeled after ChexNet research paper.
- New members worked on new primitives for preprocessing.
  - Resizing, Cropping, Translation, and Brightness.
- Use Fast Failing to rule out bad individuals and stop the evaluation quickly.
- Lexicase selection for solving highly modal problems.
  - Struggles with EMADE integration with this.

#### Stocks

- This was our presentation.
- A link to this presentation can be found [here](https://docs.google.com/presentation/d/1ZtbbWuKQiPYx6DyWzdFNs-7ailvNJkmzV-eapBtkIpE/edit#slide=id.p).
- I presented about new members' process of running the `seeding_from_file.py` and the issues that we encountered.

#### Island Migration

- Goals were to get a working version of islands, develop a way to create migration, and get multiple iterations running simultaneously.
- Island migration is another technique to create better evolutionary algorithms.
- Benefits:
  - Divide and Conquer improves efficiency.
  - Greater Diversity.
- Queried based on island number.
- New input file parameters:
  - `numIslands`, `migrationFrequency`, `migrationStart`.
    - Migration Start because EMADE can take a while to generate useful individuals.
- Implementation:
  - Migrate in a ring.
  - Send best individuals from the pool.
- Performed 3 test runs of 1024 individuals varying parameters and the number of islands.
- Future goals include altering islands to have different objectives, creating different migration pathways, and a history feature for individuals visiting islands.

### Action Items

| Task                                      | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ----------------------------------------- | -------------- | ------------- | ------------- | ------------- |
| Setup remote connection for VS-Code to PACE | Complete       | April 10th    | April 24th    | April 24th    |
| Create Finals Presentation Slide          | Complete       | April 24th    | April 28th    | April 27th    |
| Successfully set up MySQL connection      | In Progress    | April 24th    | May 1st       |               |

## Week of April 17th

### Team Meeting

- We have a hackathon on Saturday the 22nd to prepare for finals.
- Existing members shared updates.
  - Price Trends team is pretty much done with their EMADE runs on old ta-lib primitives and is looking to start the EMADE runs of the finalized data.
  - On the RL Side:
    - AddLayer, RemoveLayer, MutateTerminal unit tests are working.
    - Also, the issue with genNNLearner was fixed.
- New members continued to work on their respective tasks.

### Personal Progress Throughout the Week

- By the start of this week, I have successfully SCP'd the `stocks-nn-vip` branch to PACE.
  - Throughout this week, I continued to make progress on the steps that were written the previous week.
- Setting Up Conda Environment for `stocks-nn-vip` branch:
  - I attempted to create a new Conda environment on PACE using the `2023_stocks_linux_env.yml` file.
    - When I ran this, I ran into a disk quota exceeded error.
      - I resolved this by deleting some of the previous Conda environments I had created on PACE before.
        - `conda remove -n ENV_NAME --all`
    - When I tried to make the environment again, there was an error with getting `gpframework`.
      - I found out that I am supposed to get this by running `bash reinstall.sh` after I get everything else in the YAML file.
      - I manually pip-installed the items in the YAML file and then ran `bash reinstall.sh`.
      - I was getting permission denied errors when doing this, but the following command made this work.
        - `chmod u+rx,go-w *`
- From here, I attempted to run the `seeding_from_file.py` file.
  - When I ran this, I received the following error:
    ```
    Training...
    Traceback (most recent call last):
    File "seeding_from_file.py", line 70, in <module>
      main()
    File "seeding_from_file.py", line 66, in main
      model = train_model()
    File "seeding_from_file.py", line 19, in train_model
      learner = nnGP.GPLearner(ds)
    AttributeError: module 'gpnn.nnGP' has no attribute 'GPLearner'
    ```
  - I discussed this error with Dr. Silva and Dr. Minsky.
    - I discovered I was running the script in the wrong Conda environment.
    - After setting up the conda environment correctly, the script ran successfully.

### Action Items

| Task                                      | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ----------------------------------------- | -------------- | ------------- | ------------- | ------------- |
| Setup remote connection for VS-Code to PACE | Complete       | April 10th    | April 24th    | April 24th    |
| Create Finals Presentation Slide          | In Progress    | April 24th    | April 28th    |               |
| Successfully set up MySQL connection      | In Progress    | April 24th    | May 1st       |               |
| SCP stocks-nn-vip branch to PACE           | Complete       | April 17th    | April 17th    | April 17th    |
| Set up Conda Environment                   | Complete       | April 17th    | April 17th    | April 17th    |
| Successfully run seeding_from_file.py      | Complete       | April 17th    | April 24th    | April 24th    |

## Week of April 10th

### Team Meeting

- Existing members shared their progress with the entire research group.
  - Price Trend side looked into Pushshift for Reddit scraping.
  - On the RL side, there is still some trouble with genNNLearner.
    - Additionally, mutations are being worked on for AddLayer.
- New members still have their own respective tasks to complete.

### Personal Progress

- Since I am now going to be working on the `stocks-nn-vip` branch, I do not have to run `installEMADE.sh` yet.
- The ultimate goal for me personally is to be able to run `seeding_from_file.py`, but this requires a lot of setup first.
- First, I need to clone the branch to my local device and use the Secure Copy Protocol to transfer the branch to PACE:
  - This worked fine with the usual instructions, so not much debugging was needed.
- Then, I needed to create a new Conda environment with the YAML file from this new branch.
- Then, I needed to run `bash reinstall.sh`.
- Then, I needed to set up a remote connection to PACE from VS Code.

### Action Items

| Task                                     | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ---------------------------------------- | -------------- | ------------- | ------------- | ------------- |
| Setup PACE for `stocks-nn-vip` branch    | Complete       | April 10th    | April 17th    | April 13th    |
| Setup Conda Environment                  | Complete       | April 10th    | April 24th    | April 19th    |
| Setup remote connection for VS Code to PACE | Complete       | April 10th    | April 24th    | April 24th    |
| Attempt to run `seeding_from_file.py`     | Complete       | April 10th    | April 28th    | April 22nd    |

## Week of April 3rd

### Team Meeting

- Existing members gave updates on their work to the entire group.
  - On the RL team, genNNLearner progress is occurring, but there is trouble with starting and ending processes.
  - On the Price-Trends Prediction side, they set up the tasks for the semester.
- New members continued working on installation and setup and reading the papers.
- Stocks subteam meets on Fridays at noon to deliver further updates.
  - New members had a meeting later in the day to cover the rest of onboarding and determine which stocks subteam they are interested in (based on research paper interest).

### New Member Meeting: Friday, April 7th

- Shared problems with permission errors; no definitive fix was found within the team.
- New members decided which subteam to join, either stocks price prediction or reinforcement learning, based on their interest in reading the previous stocks team's paper or the deep learning paper.
  - Notes from these papers can be found below.
- Joined the RL subteam and was assigned to set up PACE on the `nn-stocks-vip` branch.

### Research Paper Notes

**Previous Stocks Team Paper**
- Used methodology similar to Chang et al., using a Piecewise linear representation to develop a continuous trading signal.
- Used the same datasets as other models for accurate comparisons.
- Had four main objective functions: Overall Profit Percentage (maximized), Average Profit per Transaction (maximized), Variance of Profit per Transaction (minimized), and Monte Carlo Distribution Complementary Cumulative Distribution Function (minimized).
- Performed runs with different combinations of the objective functions.
- Showed that individuals evolved through EMADE provided compelling results.

**Deep Learning for Portfolio Optimization**
- Main focus was to optimize the portfolio itself.
- Used four market indices: US Total Stock Index, US aggregate bond Index, US commodity index, Volatility Index.
- Attempted to maximize Sharpe Ratio (return per risk of the portfolio) through gradient ascent.
- Model architecture included an Input Layer, Neural Layer, and an Output Layer.
- Compared their method with other popular algorithms and found promising results.

### Action Items

| Task                                      | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ----------------------------------------- | -------------- | ------------- | ------------- | ------------- |
| Setup PACE for `nn-stocks-vip` branch      | Complete       | April 3rd     | April 17th    | April 13th    |
| Read the Research Papers                  | Complete       | April 3rd     | April 10th    | April 5th     |

## Week of March 27th

### Team Meeting

- Assigned subteams in this meeting.
  - I was assigned to the stocks subteam.
- Stocks subteam received its first task, detailed [here](https://docs.google.com/document/d/1mPcm-u2qera0fT9nzYhT9Mu_p_92wcPM5PJgjAy7SwY/edit).
  - The task involved setting up PACE-ICE and starting to read two research papers.
- PACE-ICE setup:
  - Followed the PACE setup guide [here](https://github.gatech.edu/tfeeney7/emade/blob/stocks-fall-2022/pace/README.md).
  - Successfully cloned the stocks 2022 branch locally and used Secure Copy Protocol to transfer the folder into PACE.
- PACE debugging session on Saturday, April 1st:
  - Encountered issues when downloading dependencies into a Conda environment.
  - Solved issues with the order of installing setuptools in the YAML file.
  - Faced permission denied errors when running `sh installEMADE.sh`.

### Action Items

| Task                                | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ----------------------------------- | -------------- | ------------- | ------------- | ------------- |
| Setup PACE entirely on stocks branch | Complete       | March 27th    | April 3rd     | April 2nd     |
| Read the Research Papers             | Complete       | March 27th    | April 10th    | April 5th     |

## Week of March 13th

### Team Meeting

- Today we had presentations for both bootcamp members as well as preexisting members.
- The link to our presentation can be found [here](https://docs.google.com/presentation/d/1Q0UBSn9q3uZqIkEbN7pCSxWzW50Jh_fP7UAP4QP7Fm4/edit#slide=id.p):
  - We reviewed our ML and MOGP results and also talked about our EMADE runs.
  - I ran the run for True Positive and True Negative Rates and found an AOC that was worse than both MOGP and ML results.
    - According to Dr. Zutty, this might have been due to an error in the source code for maximizing TPR and TNR.
- Other Bootcamp teams shared their results, and it was nice to see some groups achieve better results using EMADE.
  - Many groups had trouble with EMADE setup, so this might be a good thing to improve in documentation.
- I had to leave early due to an academic conflict; however, I was able to stay for the Scoliosis Team presentation, which was interesting.
- I need to look at other subteam's presentations to better see what I am interested in.
  - Edit: After looking at the subteam presentations, I am most interested in stocks and image processing.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Look into subteams and decide which subteam I want to join | Completed | Mar 13th | Mar 27th | Mar 14th |
| Fill out subteam preference form | Completed | Mar 13th | Mar 27th | Mar 15th |

## Week of March 8th

### Team Meeting

- Meeting turned into another work session since many people still had yet to get EMADE working locally and remotely.

### Installing EMADE

- I continued through the process of installing EMADE.
- Eventually, I got EMADE to work after making some changes to EMADE files and dependencies:
  - I downgraded my version of `sqlalchemy` to 1.4 since version 2.0 did not allow for files to execute in EMADE.
  - Changed `np.float` in `data.py` to `np.float64`.
  - Made zip file into a list before reversing.
- With the changes above, as well as properly installing through the correct channels, I was able to get EMADE running locally.

### EMADE Analyses for Titanic

- As a group, we were unable to get remote connections working for everyone, so we decided to run locally.
- I ran over 200 generations locally and only generated about 15 individuals.
- Changes I made to the `evalfunctions` file and input file are shown in the images below:
  - ![Image 1](https://github.gatech.edu/storage/user/67530/files/474dc79e-b1af-4e5b-a356-b2a5b73cf8e5)
  - ![Image 2](https://github-gatech.edu/storage/user/67530/files/e27641a6-f9b3-4d0e-baad-e0d5f2c9fb70)
  - ![Image 3](https://github.gatech.edu/storage/user/67530/files/20a1d56f-f055-4c23-84c2-fda79346b601)
    - Changed the input file to maximize true positive and true negative rate for objectives and created functions for calculating these rates.
- Having only gained 15 individuals for over 200 generations led me to think something was wrong, so I ran further analyses on the data.
- I ran SQL queries to generate the table shown below:
  - ![Table](https://github.gatech.edu/storage/user/67530/files/ae1d7011-94e1-4b2d-a046-088d08caeb3d)
  
### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Get EMADE installed correctly | Complete | Mar 8th | Mar 13th | Mar 10th |
| Modify EMADE for Titanic dataset | Complete | Mar 8th | Mar 13th | Mar 11th |
| Create Presentation for EMADE run with Titanic | Complete | Mar 8th | Mar 13th | Mar 12th |

## Week of March 1st

### Team Meeting

- As of the meeting start, only a couple of people were able to get EMADE running locally, and no one was able to create a master process and connect remotely through workers.
- As a result of this, the meeting became a workday for everyone to get closer to installing EMADE.
- I had installed all the dependencies needed for EMADE, but I realized that they were not installed through a certain channel (conda-forge or pyip).
  - Additionally, looking at my group members' cloned folders of EMADE, there were some differences as I didn't have a `src` folder.
  - I was unable to resolve this, so I decided to restart the entire installation process starting from cloning the EMADE repository.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Reclone EMADE repo and try to install EMADE | Complete | Mar 1st | Mar 8th | Mar 10th |
| Play around with EMADE using the Titanic Dataset | Complete | Mar 1st | Mar 8th | Mar 11th |

## Week of February 22

### Team Meeting

#### EMADE Notes:

- EMADE (Evolutionary Multi-objective Algorithm Design Engine) combines a multi-objective evolutionary search with high-level primitives to automate the designing of machine learning algorithms.
- Running EMADE:
  - Navigate to the top-level directory and run:
  - `python.src/GPFramework/launchGTMOEP.py templates/input_titanic.xml`
    - Do this if you are the master process.
    - If you are a worker, add a `-w` to the above command.
- Input File:
  - XML file that configures all moving parts of EMADE.
  - Blocks:
    1. Configuring Python:
       - For my purposes, I only have to modify the first line (`localPythonCommand`) to run EMADE.
    2. Configuring a MySQL connection:
       - Interactions between master and workers are done through this.
       - Need server, username, password, and database.
       - Want to accept remote connections.
       - `reuse` allows starting from the Pareto front where you left off.
    3. Datasets:
       - EMADE takes the average of folds.
       - EMADE reserves the last column for fitting models.
       - This is the survived column for the Titanic dataset.
    4. Objectives:
       - Names, weights, eval function.
    5. Other Params:
       - `memoryLimit` (limits memory space of an individual).
       - `workersPerHost` (how many evolutions to run in parallel).
       - Helps restrict individuals and runs.
    6. Evolution Parameters:
       - `elitePoolSize`.
       - Selection for the next generation is from `elitePoolSize` and the current offspring.
       - `minQueueSize`.
         - When the size is below this value, produce `launchSize` new individuals.
- Understanding EMADE results:
  - Connect to the MySQL server.
    - Use MySQL commands to look at results and tables.
  - If you use `reuse`:
    - Optimization will be a unique integer for each reuse.
    - Generations restart from 0 when reused.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Get EMADE up and running locally | Complete | Feb 20th | Mar 1st | Mar 10th |
| Play around with EMADE using the Titanic Dataset | Complete | Feb 20th | Mar 1st | Mar 11th |

## Week of February 15th

### Team Meeting

- We presented our ML and GP presentations regarding the Titanic Dataset.
- Learned about how different groups chose to preprocess their data, what ML models other groups were able to obtain on their Pareto front, and how others implemented their genetic programming.
- It was interesting to see the different implementations of genetic programming that groups used such as different primitives and evaluation functions.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Make sure EMADE is properly installed | Complete | February 15th | February 22nd | February 19th |
|                                             |                |                |                |                |

*Edit: Afterwards, I realized that EMADE was not installed properly as I thought it was.*

## Week of February 8th

### Team Meeting

- New assignment with Titanic data set, except this time with genetic programming techniques.
- Reviewed important concepts for presentations and tasked to create a presentation comparing ML vs GP techniques:
  - Visible Graphs
  - Takeaways
  - Technical Presentation Differences.
- Learned how to calculate Pareto Optimal.
- Learned how to calculate Area Under Curve.

### Titanic GP

- We used the same preprocessed data from the ML part with a few changes:
  - Made it so that all columns only have boolean values (a 1 or a 0).
  - Did this by using `.get_dummies()`.
  - Changed `fare`, `age*class`, `age`, and `Pclass` to this one hot encoded version.
- The specifics of our algorithm can be found at [this link](https://github.gatech.edu/khayashi31/Titanic_ML_Group_5).
- We based our genetic algorithm off of DEAP's `eaMuPlusLambda`.
- Final Results are shown below:
  ![Results](https://github.gatech.edu/storage/user/67530/files/222a4272-05d4-4c35-ba35-58cc5a252ab8)
- Specifically, I implemented possible changes to our algorithm in order to enhance it:
  - These include changes to mutation functions, generational changes as in population size and probabilities of crossover and mutation, and selection changes.
  - Found that `selNSGA2` actually performed better than our preexisting `selSPEA2`.
  - Results of some of these changes are seen below:
    ![MOGP Changes](https://github.gatech.edu/storage/user/67530/files/664f7bd8-c6d7-43e5-80ae-57d1ee79da09)
- Link to our entire presentation detailing our ML and GP on the Titanic Dataset can be found [here](https://docs.google.com/presentation/d/16L7X0c29cpSKTEVh0wN8n92Bt1ZeNAWI8KkQF8R8jcE/edit?usp=sharing).

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| GP w/ Titanic Dataset | Complete | February 8th | February 15th | February 13th |
| Create GP + ML Presentation for Titanic | Complete | February 8th | February 15th | February 14th |

## Week of February 1st

### Team Meeting

- Assigned to groups for ML assignment.
- Introduced to Kaggle and Scikit Learn.
- Introduction to Titanic Data Set Problem:
  - Preprocess data
  - Use FPR and FNR in determining optimal models
  - Create an optimal Pareto front with ML models.

### Self Evaluation

[Link to Notebook Self Evaluation](https://drive.google.com/file/d/1mzsU4zYAs6TbJPjHvveKMuh0XMucZVgE/view?usp=sharing)

### Titanic/ML Assignment

- As a group we agreed on a common dataset after preprocessing.
  - Thanks to [Keigo](https://github.gatech.edu/emade/emade/wiki/Notebook-Keigo-Hayashi) for implementing it.
- I ran several ML models to find a model that fits on a Pareto front with my group members' models (data is shown below).
- Logistic Regression Confusion Matrix
  ![Logistic Regression Matrix](https://github.gatech.edu/storage/user/67530/files/7cb82a5e-b9fd-4f15-98c6-355a1cb4c007)
- Forest of Randomized Trees
  ![Random Forest Matrix](https://github.gatech.edu/storage/user/67530/files/17c693e9-f597-4913-a64d-195715e5ad63)
- Neural Networks
  ![Neural Network Matrix](https://github.gatech.edu/storage/user/67530/files/d3e0d216-04cd-4082-9cbd-2ebfbe9895ef)
- K Nearest Neighbors
  ![KNN Matrix](https://github.gatech.edu/storage/user/67530/files/4996c4cf-dee5-4cd6-8acf-360654fef3fc)
  The individual that placed on our Pareto front that maximizes true positive and/or true negative rates is the K Nearest Neighbors.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Notebook Self Assessment | Complete | February 1st | February 8th | February 4th |
| Titanic ML Assignment | Complete | February 1st | February 8th | February 8th |

## Week of January 25th

### Team Meeting

#### Multiple Objective Notes:

- Life Circle:
  - Gene Pool:
    - The set of genomes to be evaluated during the current generation.
      - Genome: genotypic description of the individual.
      - Search Space: all possible genomes.
  - Evaluation + Genes w/Scores:
    - Evaluation of a genome is assigning the individual with a set of scores.
      - True Positive Score: how often we are identifying the desired object.
      - False Positive Score: how often we identify something else as the desired object.
      - True Negative
      - False Negative.
    - Objective Space is synonymous with phenotype.
    - Binary Classifier: Two options for classification.

- Maximization Measures:
  - Sensitivity or True Positive Rate (TPR):
    - Num of true positives over all positive objects.
      - TPR = TP/P = TP/(TP+FN).
    - Also called hit rate or recall.
  - Specificity (SPC) or True Negative Rate (TNR):
    - TNR = TN/N = T/(TN + FP).

- Minimizing Measures:
  - False Negative Rate (FNR):
    - FNR = 1 - TPR.
    - FNR = FN/P = FN/(TP + FN).
  - Fallout or False Positive Rate (FPR):
    - FPR = 1 - TNR = 1 - SPC.
  - Overall, just whatever the attribute we are looking at over the total number of actual positives or negatives.

- Other Measures:
  - Precision or Positive Predictive Value (PPV):
    - True positive over the predicted positive totals.
      - PPV = TP / (TP + FP).
    - Bigger is better.
  - False Discovery Rate (FDR):
    - Num of false positives overall all positives.
      - FDR = FP/ (TP + FP).
    - Smaller is better.
    - FDR = 1 - PPV.
  - Negative Prediction Value is the opposite of PPV.
  - Accuracy (ACC):
    - Num correct you get over all examples.
    - Bigger is better.

- Pareto Optimality:
  - The individuals that are the best individuals found so far.
    - When you have multiple individuals, they present trade-offs where one individual is better in certain areas than others.
  - Individuals that are the best are non-dominant solutions.
    - No individual is better than the individual.
  - Minimizing - Pareto front is closest to bottom.
    - Rotated L shapes.
  - Maximizing - Pareto front gets closer to the top.
    - Line has L shapes.

- Algorithms for Multiple Objective:
  - Non Dominated Sorting Genetic Algorithm II (NSGA II):
    - Separate pop into non-dominated ranks.
      - Create Pareto optimal lines for each group of individuals.
    - When breaking a tie between individuals on the same front:
      - Use Crowding Distance.
        - Individual distance from other individuals on the front.
        - Farther away -> better.
  - Strength Pareto Evolutionary Algorithm 2 (SPEA2):
    - Each individual is given a strength.
      - Strength is determined by the number of individuals the current individual dominates.
    - Then each individual receives a rank.
      - Rank - sum of strengths of individuals that dominate it.
      - Pareto individuals get a rank of 0.
      - Lower rank is better.
    - Tiebreak:
      - Reward individuals that are further than other individuals.
      - Compute rank as R + 1/(dist to nearest neighbor + 2).

#### Lab 2: Part 2 Genetic Programming and Multiple Objectives

- With Multiple Objectives, we are trying to maximize or minimize multiple factors or traits.
  - For this lab, we are minimizing our mean squared error and size of the tree.
    - So when creating our fitness class, we have our weights as weights = (-1.0,-1.0).

- Process:
  - Similar structure to single objective, but has some differences with methods.
    - Symbolic Regression function is much more complex and returns mean squared error and size of the tree.
      - We had a more complex function to show more evolution over time.
    - Pareto Dominance function:
      - A function to check if an individual is better than another.
    - Create population and a separate individual to compare population individuals to.
      - Separate population into groups that dominate, get dominated, and can't be compared to the separate individual.
      - After graphing, we can see that the individuals that dominate the separate individual are closer to bottom left, since we are minimizing both attributes.
      - Individuals that get dominated are farther from the bottom left than the compared individual.

- Analysis:
  - While trying to find a way to minimize the area under the Pareto front, I found that using `mutInsert()` reduced the area.
    - Best individual is: negative(cos(add(x, x))) with fitness: (0.2924802565130735, 5.0)
    - ![Results 1](https://github.gatech.edu/rpatil73/AADImages/blob/main/MultObj1.png)
    - ![Results 2](https://githubgategit hub.gatech.edu/rpatil73/AADImages/blob/main/MultObj2.png)

- Strongly Typed Genetic Programming:
  - Use `PrimitiveSetTyped(arg1 = name, arg2 = inputTypes, arg3 = outputType)` for strongly typed GP.
  - Output type must match input type.

- Ephemeral Constants:
  - Terminals/Constants created by a function.

- Bloat Control:
  - Def: Individuals "bloat" and grow in size through each generation.
  - This is bad since DEAP trees have a set max of 91 depth.
  - To Control:
    - Use static limits.
    - Set the objective to minimize tree size.
    - Make bloated trees get worse fitness by changing the eval function.

### Action Items

| Task                                       | Current Status | Date Assigned | Suspense Date | Date Resolved |
| ------------------------------------------ | -------------- | ------------- | ------------- | ------------- |
| Finish Lab 2: Part 2 | Complete | Jan 25th | Feb 1st | Jan 27th |
| Complete Assignment for python/ML skills | Complete | Jan 25th | Feb 1st | Jan 27th |
| Update Meeting Notes | Complete | Jan 25th | Feb 1st | Jan 25th |

## Week of January 16th

### Team Meeting

#### Genetic Programming Presentation Notes:

- Basis of Genetic Programming
  - Instead of taking an individual and feeding it through an evaluator to obtain an objective score, the individual is the function itself
- Genomes are represented through a tree structure
  - Nodes are called primitives (represent function) (these are the operators) (takes in input)
  - Leafs are called terminals (represent parameters) (doesn’t take in input)
- How is the tree stored
  - It is converted to a lisp preordered parse tree
  - Basically, a list that is the tree represented as a preorder traversal
- Crossover in GP
  - Crossover in a tree-based GP is exchanging subtrees
  - Randomly pick a node on the tree and swap with another node to produce children
- Mutation in GP
  - Can involve
    - Inserting a node or subtree
    - Deleting a node or subtree
    - Changing a node
- Symbolic Regression
  - Taking a function and trying to map the function you create to the output of the function
- Evaluating a tree
  - Take a bunch of trials and compare error between estimated values and actual values
  - Find the square number to represent how "bad" our function estimates the actual function

#### Lab 2: Part 1 Genetic Programming and Symbolic Regression

- Genetic Programming is the tool we use for Automated Algorithm Design
- General Structure of Program is similar to Lab 1
  - We still create and initialize an individual
  - Define an evaluation function
  - Register Genetic Operators (Evaluate, Select, Mate, Mutate)
  - Evaluate individuals with new fitnesses
  - Display stats of generation
- Major differences
  - The individual inherits from the PrimitveTree class in DEAP
    - Trees are a common method of displaying individual in Genetic Programming
  - Add primitives to the tree by creating a PrimitiveSet
    - Definition: Arity - num arguments each primitive takes
  - Register an "expr" and a "compile" function to toolbox
    - `expr` returns a tree based on the primitive set
    - `compile` compiles trees into the toolbox
- Evaluation Function
  - Compile the tree into a function var and calculate the mean squared error between the function and actual function
  - This is the concept of symbolic regression
    - We are trying to optimize the function by minimizing mean squared error
- Analysis
  - After Running Original Program
    - The Individual with the best fitness has a score of 1.0736236036501015e-16
    - Graph is shown below
    [SymbolicRegressionOG](https://github.gatech.edu/rpatil73/AADImages/blob/main/SymbolicRegressionOG.png)
  - After Adding New Primitives
    - Added `np.positive()` with arity of 1 and `np.square()` with arity of 1
    - The Individual with the best fitness has a score of 9.522005638492831e-17
    - Graph is shown below
    [SymbolicRegressionNewPrimatives](https://github.gatech.edu/rpatil73/AADImages/blob/main/SymbolicRegressionNewPrimatives.png)
  - After Using a different Mutation
    - Used `mutNodeReplacement` which replaces a random primitive of an individual with another primitive with the same arity from pset of individual.
    - The Individual with the best fitness has a score of 1.2723517629119777e-16
    - Graph is shown below
    [SymbolicRegressionNewMutation](https://github.gatech.edu/rpatil73/AADImages/blob/main/SymbolicRegressionNewMutation.png)
  - The graphs shown above do not exactly reflect the genetic programming for all populations
  - When running the program multiple times, you can see that there is a lot of variation from run to run

### Action Items

| Task                              | Current Status | Date Assigned | Suspense Date | Date Resolved |
|-----------------------------------|----------------|---------------|---------------|---------------|
| Download Necessary Software       | Complete       | January 11th  | January 25th  | January 20th  |
| Update Notebook with Team Meeting Notes | Complete | January 18th | January 25th | January 20th |
| 1st Half of Lab 2                 | Complete       | January 18th  | January 25th  | January 21st  |

## Week of January 9th

### Team Meeting

#### Administrative Details:

- Students attend a 10-week bootcamp to learn about the processes involved with AAD
- Students maintain a living notebook to highlight progress and work accomplished

#### Genetic Algorithm Presentation Notes:

- Genetic Algorithms produce the best individual through a series of generational changes
  - These include mating, mutating, and crossing over
- Important Definitions
  - Individual: a single candidate with properties
  - Population: A group of individuals
  - Objective: a value that we are trying to maximize or minimize
  - Fitness: a measure of how well an individual compares to another (relative)
  - Evaluation: a function to compute the objective of an individual
  - Selection: survival of the fittest
    - Fitness Proportionate: higher fitness value -> higher probability of being selected
    - Tournament: tournaments among individuals -> winners selected
  - Mutate: Random modifications
  - Crossover: swapping of attributes between two individuals

#### Lab 1: One Max Problem

- Objective: Find a bit string containing all 1s from a randomly generated bit string
- Process:
  - Necessary Imports (random, base, creator, tools)
  - Define objective and Individual class
    - Used creator.create() to define these
    - Weights should equal 1.0 since we want the objective to maximize fitness
    - Note that in defining the objective, we must have fitness weights be a tuple so multi-objective and single-objective are treated the same
  - Define functions for randomization, creating an individual, and population (Setup)
    - Used toolbox.register()
    - Randomization - function to randomly decide 0 or 1
    - Individual - generates an individual with a random bit string of the desired length and puts it in the container created in step 2
    - Population - allows for a desired number of individuals to be created
  - Create functions for advancing generations
    - Evaluate fitness, Mating (crossover two-point), Mutate (mutFlipBit), Select (selTournament)
  - Start the Evolutionary Process
    - Define population size (in our case, we want to start with a population of 300 individuals)
    - Assign each individual their fitness value from evaluating it
    - Create a loop to run for a set number of generations (40)
      - Select the next-gen individuals and clone them
        - VERY IMPORTANT TO CLONE: necessary for crossover to occur successfully
      - For each generation, perform crossover and mutation functions if applicable (a random number is less than the probability of these occurring)
      - For individuals that had mutation or crossover, reevaluate fitness and assign it to the individual
      - Replace the population with newly generated offspring
      - Create stats for the population to understand data
- Analysis
  - After several runs, I noticed that successful evolution occurs mostly before the 40th generation and has an average of 97-99 with a standard deviation of about 2
  - Curiosities/Queries
    - How does the algorithm tend towards individuals with more 1's as generations progress? (From the initial fitness objective but how exactly?)

#### The N Queens Problem

- Objective: Determine a configuration of n queens on an nxn chessboard where no queen can be taken
- Process:
  - Initialize Fitness and Queen class
    - Fitness weight is now -1.0 (want to minimize conflicts)
  - Create Functions for creating the population
  - Define Evaluation Function
    - Many ways to do this, but the goal is to determine the number of conflicts between queens
    - Can have each queen assigned to a column/row and then count conflicts in diagonal
  - Define Crossover Function
    - Perform partially matched crossover instead of one or two-point crossover as it is more effective
  - Define Mutant Function
    - Swap two indexes if the random value is less than indpb (probability we choose for mutation to occur)
    - Wrote my own mutant function that used random.shuffle() to randomize all indexes at once if a random value was generated less than indpb
  - Define Select Function
    - Tournament of size 3 to select the best individual
  - Define the main evolutionary loop
    - Initialize a population of size 300 and evaluate and assign fitness to individuals
    - Select the next generation (tournament), crossover, and mutate as needed (depends on the probability of it occurring)
    - Evaluate and assign new fitness for individuals with crossing over and mutations
    - Replace the population with new offspring and generate stats for each generation.
- Analysis
  - After running the code numerous times, I found that the minimum is reached around generation 20-25 (gen = range(100)), however, this varies
  - Something interesting I noticed was when using my own mutation method, the minimum was reached at an earlier generation on average
    - I used random.shuffle() for my mutation
    - Not entirely sure why this happens, but it might be due to the entirety of the individual being shuffled instead of just two indexes being swapped
    - The results can be seen below (Original on the left, new mutate function on the right)
  - [NQueensOriginal](https://github.gatech.edu/rpatil73/AADImages/blob/main/NQueensOriginal.png) [NQueensNewMutate](https://github.gatech.edu/rpatil73/AADImages/blob/main/NQueensNewMutate.png)

#### Action Items

| Task                      | Current Status | Date Assigned | Suspense Date | Date Resolved |
|---------------------------|----------------|---------------|---------------|---------------|
| Join Slack                | Completed      | January 11th  | January 18th  | January 11th  |
| Set up Notebook           | Completed      | January 11th  | January 18th  | January 16th  |
| Download Necessary Software | Complete    | January 11th  | January 18th  | January 24th  |
| Lab 1                     | Completed      | January 11th  | January 18th  | January 16th  |
