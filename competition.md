# Issues about the competition

## Formats

> Phase description
>
> To submit, upload a .zip file containing text files with the prediction. The results with the highest HOTA score will be used to determine the winner.
>
> **Max submissions per day: 1**
>
> **Max submissions total: 10**

Submission should be put directly in the root folder of your zip

[After unzipping]

```text
- v_XXX.txt
- v_XXX.txt
```

i.e. Submission should be in `ROOT/v_XXX.txt` instead of `ROOT/SOME_SUBFOLDER/v_XXX.txt`

:exclamation: There is limit for submissions during testing phase. Considering the sake of fairness, it's really troublesome to cope with wrong submission formats.

:exclamation: **_please CAREFULLY check the format before submitting zipped results._**

## README for test phase

### Example

These info below should be provided as the **submission description**.

```text
Name: John
Team: MCG NJU
Email: john@abc.com
Affiliation: Multimedia Computing Group, Nanjing University
Whether willing to offer report: Yes
```

_NOTE_

_Since participants may submit multiple results, the README INFO should be **kept consistent** throughout the test phase._

- `Team` is required if you are participating together with others
  - All of the participants in a team should share the same `Team` name.
- `Affiliation` should be the full name, which can be easily recognized.

### No report, no result

- 📃 `Report` means a `pdf` which clearly explains the **models**, **settings** and **tricks** supporting the results.

:white_check_mark: After the testing phase is closed, **top 3 participants** will be required to provide their **report(pdf)** as described above. It serves as the prerequisite for the results to be admitted.

:no_entry: Suppose `A,B,C,D` rank 1st to 4th when the test phase is closed, if we cannot **contact `B` via email to get the technical report**, `B`'s score will be **discarded** and thus **removed** from leaderboard. Consequently, `A,C,D` will rank 1st to 3rd if we receive report pdfs from all them three.

## Other Notifications

- :four_leaf_clover: A rising tide lifts all boats. We highly recommend **submitting results to the leaderboard**.
- There is no limit of the number of participants, and the entry is still open.
- Currently, the results shown on the leaderboard are those _voluntarily submitted to it_.
  - Test results are private by default. And HOTA is shown as the `Scores` of submissions.
  - If you want to view more detailed _metrics_, click `Download output from scoring step`.
    ![image](https://user-images.githubusercontent.com/49837632/185593382-accf96ec-067e-4e48-98ff-e0e54e1bd7bc.png)

## Errors

```text
WARNING: Your kernel does not support swap limit capabilities or the cgroup is not mounted. Memory limited without swap.
```

Just ignore this.

```text
ERROR: Could not install packages due to an EnvironmentError: [Errno 28] No space left on device
```

It's caused by the unstable server instead of the uploaded files. Resubmit, please.

## Discussion 

- Discuss at [Forum](https://codalab.lisn.upsaclay.fr/forums/4433/) [Recommended]
- Send email to xiaoyuzhao {AT} smail [Dot] nju [Dot] edu [Dot] cn

This competition will end at **Aug. 31, 2022, 11:59 p.m. UTC**

Pay attention to your **Emails** and the **Forum**.

Good luck :tada:
