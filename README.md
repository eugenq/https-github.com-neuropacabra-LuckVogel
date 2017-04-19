# Luck & Vogel paradigm

*Short-term memory storage can be divided into separate subsystems for verbal information and visual information, and recent studies have begun to delineate the neural substrates of these working-memory systems. Although the verbal storage system has been well characterized, the storage capacity of visual working memory has not yet been established for simple, suprathreshold features or for conjunctions of features. Here we demonstrate that it is possible to retain information about only four colours or orientations in visual working memory at one time. However, it is also possible to retain both the colour and the orientation of four objects, indicating that visual working memory stores integrated objects rather than individual features. Indeed, objects defined by a conjunction of four features can be retained in working memory just as well as single-feature objects, allowing sixteen individual features to be retained when distributed across four objects. Thus, the capacity of visual working memory must be understood in terms of integrated objects rather than individual features, which places significant constraints on cognitive and neurobiological models of the temporary storage of visual information* (Luck & Vogel, 1997, p.1).

## Paradigm setup
Paradigm is fully implemented into [OpenSesame](http://www.cogsci.nl) in Python 2.7 working and tested under Windows 7 SP2 64-bit and macOS 10.12.4.

In this paradigm we present some subset of complexity based on previous behavioral pilot study as 3, 4 and 6, 8 boxes.

First administrator is supposed to run NIC software to record EEG signal. It has to be run on the same machine since it is hard-coded as `localhost` at port `1234`.

When connection at `host:port` is connected, done by `socket` Python module. In any case it would be in any Python distribution, otherwise install it by `pip install socket` in terminal.

[Youtube demo](https://www.youtube.com/watch?v=CH0tzhZdU2M)

## Scenario
Initial screen is dedicated for administrator with information if connection for EEG synchronization was established or not.

### Synchronize EEG 
In both cases it requires administrators key press to continue despite success or error. In case of error administrator is suppose to:

1. Shut down experiment
1. Inform participant that he/she need to adjust conenction
1. Close OpenSesame and NIC software
1. Turn off and on the StarStim EEG system
1. Re-open NIC software
1. Check bluetooth synchronization information in NIC with EEG
1. Check battery level
1. Check if port at localhost is open (in right down corner)
1. Re-open OpenSesame
1. Start experiment again
1. In any other cases (errors or crashes) feel free to contact me for support (ideally send me some image and caption what is wrong)

### Present stimuli
After synchronization procedure participant is asked to continue with any key press when he/she reads the main instruction. It is highly recommended to speak with the subject, to inform them what is going to happen and describe basics of their task and importance of clear signal.

Stimuli can occur on the screen with 10% margins from edges. It is pseudo-random order, e.g. once random possition for boxes etc. generated, then it is all the same for all subjects.

Experiment has 4 levels of complexity: 3, 4, 6 and 8 boxes (squares) which changes only 1 box color in 50% of all 120 trials in following ratio:

| Complexity | Number of trials |
|------------|------------------|
| 3 boxes    | 20 trials        |
| 4 boxes    | 20 trials        |
| 6 boxes    | 40 trials        |
| 8 boxes    | 40 trials        |

#### Boxes parameters
Boxes coordinates are generated randomly only once (pseudo-random order), same as color and property if they change in color or not. Color are used copletely randomly same as order or changing.

It is used only these eight colors:
* orange
* grey
* purple
* red
* blue
* white
* green
* yellow

Size of the box is strictly set up as `64 x 64` px at `1920 x 1080` px resolution.

### Response collection
It is collected only mouse pressed coded as `LMB = 1` and `RMB = 3` in the way of correctness in logfile which is automaticaly generated.


box 1 = 100
retention = 900
box 2 = 1000