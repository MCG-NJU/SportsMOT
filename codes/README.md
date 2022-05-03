# Codes for SportsMOT

Here we provide some useful codes for developers to explore SportsMOT.

## Evaluation

We perform our evaluation based on the official eval kit for MOT challenge: [TrackEval](https://github.com/JonathonLuiten/TrackEval/blob/master/docs/MOTChallenge-Official/Readme.md).
 
### How to eval

- Download this folder [TrackEval](./)
- Run your code on SportsMOT to get results     
  - Results should be in [the format of TrackEval](https://github.com/JonathonLuiten/TrackEval/blob/master/docs/MOTChallenge-Official/Readme.md#data-format).

    ```text
    4 6 589 296 51 195 -1 -1 -1 0 
    4 7 703 410 93 162 -1 -1 -1 0 
    4 8 635 289 58 178 -1 -1 -1 0 
    5 1 986 394 68 211 -1 -1 -1 0 
    5 2 432 271 129 165 -1 -1 -1 0
    ```

- Organize them by naming putting results for a certain video in a text file, which is named as `VIDEONAME.txt`


<details>
<summary>list of video tracking resulst</summary>

```text
v_-6Os86HzwCs_c001.txt
v_-6Os86HzwCs_c003.txt
v_-6Os86HzwCs_c007.txt
v_-6Os86HzwCs_c009.txt
v_2j7kLB-vEEk_c001.txt
v_2j7kLB-vEEk_c002.txt
v_2j7kLB-vEEk_c005.txt
v_2j7kLB-vEEk_c007.txt
v_2j7kLB-vEEk_c009.txt
v_2j7kLB-vEEk_c010.txt
v_4LXTUim5anY_c002.txt
v_4LXTUim5anY_c003.txt
v_4LXTUim5anY_c010.txt
v_4LXTUim5anY_c012.txt
v_4LXTUim5anY_c013.txt
v_1LwtoLPw2TU_c006.txt
v_1LwtoLPw2TU_c012.txt
v_1LwtoLPw2TU_c014.txt
v_1LwtoLPw2TU_c016.txt
v_ApPxnw_Jffg_c001.txt
v_ApPxnw_Jffg_c002.txt
v_ApPxnw_Jffg_c009.txt
v_ApPxnw_Jffg_c015.txt
v_ApPxnw_Jffg_c016.txt
v_CW0mQbgYIF4_c004.txt
v_CW0mQbgYIF4_c005.txt
v_CW0mQbgYIF4_c006.txt
v_dChHNGIfm4Y_c003.txt
v_Dk3EpDDa3o0_c002.txt
v_Dk3EpDDa3o0_c007.txt
v_1yHWGw8DH4A_c029.txt
v_1yHWGw8DH4A_c047.txt
v_1yHWGw8DH4A_c077.txt
v_1yHWGw8DH4A_c601.txt
v_1yHWGw8DH4A_c609.txt
v_1yHWGw8DH4A_c610.txt
v_gQNyhv8y0QY_c003.txt
v_gQNyhv8y0QY_c012.txt
v_gQNyhv8y0QY_c013.txt
v_HdiyOtliFiw_c003.txt
v_HdiyOtliFiw_c004.txt
v_HdiyOtliFiw_c008.txt
v_HdiyOtliFiw_c010.txt
v_HdiyOtliFiw_c602.txt
v_iIMOsCGH58_c013.txt
```
</details>

- **Put re-organized results into `TrackEval/data/res/sportsmot-val/tracker_to_eval/data`**
- Install dependencies `TrackEval/requirements.txt` or `minimum_requirements.txt`
  - you can also validate results on training set by setting `--SPLIT_TO_EVAL val` to `train`
- `cd path/to/TrackEval`
- `bash evaluate.sh`

In `path/to/TrackEval/data`, there are two folders.

- `res` is supposed to contain your tracking results.
  - e.g. `path/to/TrackEval/data/res/sportsmot-val/tracker_to_eval/data` should contain results for training data.
  - Note that this nested folder hierarchy,`sportsmot-val/tracker_to_eval/data`, is corresponding to the default format of TrackEval. 
- `ref` contains re-organized reference ground truths, which can also be found in the full dataset.

**Customization:** In `evaluate.sh`, we set default arguments to `--GT_FOLDER ./data/ref --TRACKERS_FOLDER ./data/res --OUTPUT_FOLDER ./output/`. This correspond to current folder hierarchy in `TrackEval/data`

> All of the arguments can be changed. 
> This kit is merely an encapsulation of TrackEval.

## Conversion

SportsMOT is originally of [MOT17](https://motchallenge.net/data/MOT17/)/[20](https://motchallenge.net/data/MOT20/) format. Currently, we provide codes for converting data to COCO format. 

