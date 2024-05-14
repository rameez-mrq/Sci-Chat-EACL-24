# SciChat Mturk Data
The data collected from Mturk for the SciChat workshop is provided as `data_anonymised.json`. The data structure for the same is mentioned below.

## Data Structure
1. Directory `data/` contains `data_anonymised.json` details of which is explained below:
    + `metadata`: stores the metadata for scores and models
      - ***score*** - stores scorename attributes pairs
        - ***scorename*** - the name of ratings, such as robotic and interesting in our experiment, with following attributes
          - ***positive***: bool - `false` means this score needs reversion before computing
          - ***qc***: bool - `true` means the current score will be used for quality control
          - ***max***: number - It is used for reversing scores with attribute `positive=false` by `max-original_score`. `100` for evaluation.
      - ***model***: a list of models to be evaluated (except the quality-control model). Please refer the workshop findings for more information on models used.   
    + ***data***: a list of result per HIT - Each element has the following structure
      - ***result***: a list of collected data from the HIT - each element means the result of a model. In our experiment, it contains eight elements: 7 competing models and a quality control model.
        - ***model***: name of current model
        - ***score***: scorenames with numerical values - For example, {robotic: 100, interesting: 37, ...}
        - ***persona***:  List of personas.
        - ***dialogue***: Textual conversations between workers and models.
        - ***topics***: Presented topics to the user to choose from.
      - ***hit*** - HIT ID
      - ***assignment*** - Assignment ID
      - ***worker*** - Worker ID
      - ***duration in seconds*** - elapsed time of a HIT in seconds
      - ***feedback***: optional - Feedback from the worker.


