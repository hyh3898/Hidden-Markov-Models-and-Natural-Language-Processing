# Hidden-Markov-Models-and-Natural-Language-Processing

build a basic English sentence recognizer based on hidden Markov models ("HMMs"), which is expected to recognize and parse sentences that use the certain vocabulary.

## To do:
  To read the HMM from sentence.hmm and observations from example1.obs on commend line: <br />
    ```
    python recognize.py sentence.hmm example1.obs 
    ```
    ```
    python statepath.py sentence.hmm example1.obs
    ```

  To read the HMM from sentence.hmm and observations from example2.obs, and save the optimized version of the HMM in sentence-optimized.hmm:<br />
    ```
    python optimize.py sentence.hmm example2.obs sentence-optimized.hmm
    ```
  
  Each line reports P(O | lambda) for that HMM, e.g,:<br />
    ```
    python recognize.py sentence.hmm example1.obs 
    ```
    ```
    0.027 
    ```
    ```
    0.0288
    ```
    ```
    0.0
    ```
  
  
  
  Each line again corresponds to a data set:  In this case, the program outputs the "optimal" state path, i.e., the path with the highest probability P(O, I | lambda) and, if the probability is greater than zero, the state sequence.  For example: <br />
    ```
    python statepath.py sentence.hmm example1.obs 
    ```
    ```
    0.027 SUBJECT PREDICATE OBJECT
    ```
    ```
    0.0288 SUBJECT PREDICATE OBJECT
    ```
    ```
    0
    ```
  
  
  
  This program optimizes the HMM using one iteration of the Baum-Welch algorithm.  After all data sets are processed, optimize saves the optimized HMMs in a new file as specified by the command-line argument.
  For each data set, optimize prints out P(O | lambda) for the old HMM before optimization, and P(O | lambda) for the new HMM after optimization: <br />
    ```
    python optimize.py sentence.hmm example2.obs sentence-opti.hmm 
    ```
    ```
    0.000588 0.037037
    ```
    
  
