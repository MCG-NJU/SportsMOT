# SportsMOT

![](https://deeperaction.github.io/images/sports_mot.gif)

SportsMOT: A Large-Scale Multi-Object Tracking Dataset in Sports Scenes :basketball::volleyball::soccer:

## Overview


### Demos

<iframe width="1280" height="720" src="https://www.youtube.com/embed/2wbjsyg5zbI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

📹 Jigsaw demo

<iframe width="1280" height="720" src="https://www.youtube.com/embed/C6QLjN7oVwA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

📹 Basketball Demo(NBA)

<iframe width="1280" height="720" src="https://www.youtube.com/embed/GxP0F2yhQhU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

📹 Volleyball Demo(London 2012)


<iframe width="1280" height="720" src="https://www.youtube.com/embed/dlRZDiSTdyU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

📹 Football Demo(FA Cup)

### Data Collection


**Diverse Sources**

We provide 240 sports video clips of 3 categories (i.e., basketball, football and volleyball), where are collected from Olymplic Games, NCAA Championship, and NBA on YouTube. Only the search results with **720P** resolution, **25 FPS**, and official recording are downloaded. All of the selected videos are cut into clips of **average 485 frames** manually, in which there is no shot change.

<!-- <details>
<summary>Average Frames Number</summary>
Basketball: 422
Volleyball: 360
Football: 673
</details> -->

**Diverse Scenes**

As for the diversity of video context, football games provide outdoor scenes and the rest results provide indoor scenes. Furthermore, the views of the playing courts do vary, which include common side view of crowded audience like in NBA, views from the serve zone in volleyball games, and aerial view in football games. Diverse scenes in our dataset will encourage the algorithms to generalize to different sports tracking settings
### Basic Statstics

![](https://gitee.com/ZXYFrank/picgo/raw/master/img/src/20220503193217.png)

<p style = "text-align:center;color:gray;font-size:0.7em;text-indent:0">basic statistics of videos of 3 categories.</p>

<details>
<summary>explanation for the statistics above.</summary>

- track: number of tracks per video.
- tracklen: average length/number of frames per video
- fragmentation: average number of track fragmentation per video.
- speed: average speed of the players in videos.
- density: average number of players per frame per video.
- bboxsize: average size of bounding boxes(pixels).
- defrate: average `deformationRate`


We use **deformation rate** to measure the degree of deformation. Here, $w_{min},h_{min}$ refer to the minimum width and height of bounding boxes in a track fragment.

<!-- $$\text{deformationRate}(\mathbf{b}_{i}) =  \frac{w_{max} - w_{i}}{w_{min}} + \frac{h_{max} - h_{i}}{h_{min}}$$ -->

![](https://gitee.com/ZXYFrank/picgo/raw/master/img/src/20220429153828.png)


</details>


![](https://gitee.com/ZXYFrank/picgo/raw/master/img/src/20220404134703.jpg)

<p style = "text-align:center;color:gray;font-size:0.7em;text-indent:0">Distributions(Gaussian PDF) of the fragment speed in 3 sports in SportsMOT.</p> 

## Motivation

Multi-object tracking (MOT) is a fundamental task in computer vision, aiming to estimate objects (e.g., pedestrians and vehicles) bounding boxes and identities in video sequences.

Prevailing human-tracking MOT datasets mainly focus on pedestrians in crowded street scenes (e.g., [MOT17](https://motchallenge.net/data/MOT17/)/[20](https://motchallenge.net/data/MOT20/)) or dancers in static scenes ([DanceTrack](https://github.com/DanceTrack/DanceTrack)). 

In spite of the increasing demands for sports analysis, there is a lack of multi-object tracking datasets for a variety of **sports scenes**, where the background is complicated, players possess rapid motion and the camera lens moves fast.

To this purpose, we propose a large-scale multi-object tracking dataset named SportsMOT, consisting of **240 video** clips from **3 categories** (i.e., basketball, football and volleyball). 

The objective is to only track players on the playground (i.e., except for a number of spectators, referees and coaches) in various sports scenes. We expect SportsMOT to encourage the community to concentrate more on the complicated sports scenes.

## Data Format

Data in SportsMOT is organized in the form of [MOT Challenge 17](https://motchallenge.net/).

Unzip the provided .zip file, you will get

- `splits_txt`(video-split mapping)
  - `basketball.txt`
  - `volleyball.txt`
  - `football.txt`
  - `train.txt`
    <details><summary>details</summary>

    ```text
    v_-6Os86HzwCs_c001
    v_-6Os86HzwCs_c003
    v_-6Os86HzwCs_c007
    v_-6Os86HzwCs_c009
    v_2j7kLB-vEEk_c001
    v_2j7kLB-vEEk_c002 
    ``` 
    
    </details>
  - `val.txt`
  - `test.txt`
- `scripts`
  - `mot_to_coco.py`
  - `sportsmot_to_trackeval.py`
- `dataset`(in MOT challenge format)
  - `train`
    - `VIDEO_NAME1`
      - `gt`
        <details><summary>details</summary>

        ```text
        1, 7, 749, 217, 34, 125, 1, 1, 1
        1, 8, 721, 344, 71, 120, 1, 1, 1
        1, 9, 847, 352, 50, 151, 1, 1, 1
        2, 0, 85, 421, 88, 131, 1, 1, 1 
        ``` 
        
        </details>
      - `img1`
        - `000001.jpg`
        - `000002.jpg`
      - `seqinfo.ini`
        <details><summary>details</summary>

        ```text
        [Sequence]
        name=v_-6Os86HzwCs_c001
        imDir=img1
        frameRate=25
        seqLength=825
        imWidth=1280
        imHeight=720
        imExt=.jpg
        ``` 
        
        </details>
  - `val`
    - the same hierarchy as train
  - `test`
    - `VIDEO_NAME1`
      - `img1`
        - `000001.jpg`
        - `000002.jpg`
      - `seqinfo.ini`

You can download the example for SportsMOT.

- [OneDrive](https://1drv.ms/u/s!AtjeLq7YnYGRgQRrmqGr4B-k-xsC?e=7PndU8)
- [Baidu Netdisk](https://pan.baidu.com/s/1gytkTngxoGFlmP9_DBd1xw), password: 4dnw

## Usage

### Download

Download links for SportsMOT full dataset:

- [OneDrive](https://1drv.ms/u/s!AtjeLq7YnYGRgQPmuAkwWhndOc41?e=ItJaaa)
- [Baidu Netdisk](https://pan.baidu.com/s/1wryLDorjOscBmDMrU3RThA), password: amb

### Format Conversion

Refer to [codes/conversion](./codes/conversion)

### Evaluation Kit

Refer to [codes/evaluation](./codes/conversion) for out-of-the-box evaluation based on [TrackEval](https://github.com/JonathonLuiten/TrackEval/blob/master/docs/MOTChallenge-Official/Readme.md). :joystick:

## Competition

SportsMOT is currently used for [DeeperAction@ECCV-2022](https://deeperaction.github.io/tracks/sportsmot.html). Welcome!

![](https://gitee.com/ZXYFrank/picgo/raw/master/img/src/20220503192732.png)

![](https://gitee.com/ZXYFrank/picgo/raw/master/img/src/20220503194255.jpg)

## Contact 

This track is provide by [MCG Group @ Nanjing University](http://mcg.nju.edu.cn/en/index.html), Jiangsu, China.

- [Limin Wang](http://wanglimin.github.io/)
- Yutao Cui
- Xiaoyu Zhao
- Chenkai Zeng
- Yichun Yang     

Valuable issues and chat are welcomed.
## Terms


<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.