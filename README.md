# Understanding the Bug Characteristics and Fix Strategies of Federated Learning Systems

This repository consists of three main folders: Dataset_Init, Manual_Labelling and Quantitative_study.

1. **Dataset_Init** folder: The list of initially mined Issues and Pull Rquests(after **Step 1**) for each framework from GitHub is presented in the file `GitHub_init/{frameworkname}/issues_init.csv` and `GitHub_init/{frameworkname}/PRs_init.csv`.

    Total data and data collection process of 6 federated learning frameworks (Data collection until October 1, 2021):
    <table>
        <tr>
            <th rowspan="2">Framework</th>
            <th colspan="5"><div align="center">Total</div></th>
            <th colspan="2"><div align="center">Step1</div></th>
            <th colspan="2"><div align="center">Step2</div></th>
            <th colspan="2"><div align="center">Step3</div></th>
        </tr>
        <tr>
            <td><div align="right">LOC</div></td>
            <td><div align="right">Forks</div></td>
            <td><div align="right">Stars</div></td>
            <td><div align="right">Issues</div></td>
            <td><div align="right">PRs</div></td>
            <td><div align="right">Issues</div></td>
            <td><div align="right">PRs</div></td>
            <td><div align="right">Issues</div></td>
            <td><div align="right">PRs</div></td>
            <td><div align="right">Issues</div></td>
            <td><div align="right">PRs</div></td>
        </tr>
        <tr>
            <td>
                <div align="center">PySyft</div>
                <div align="center">FATE</div>
                <div align="center">TFF</div>
                <div align="center">Flower</div>
                <div align="center">Fedlearner</div>
                <div align="center">PaddleFL</div>
            </td>
            <td>
                <div align="right">3.7m</div>
                <div align="right">490.9k</div>
                <div align="right">199.3k</div>
                <div align="right">41.5k</div>
                <div align="right">209.1k</div>
                <div align="right">87.0k</div>
            </td>
            <td>
                <div align="right">1,777</div>
                <div align="right">1,167</div>
                <div align="right">431</div>
                <div align="right">192</div>
                <div align="right">152</div>
                <div align="right">85</div>
            </td>
            <td>
                <div align="right">7,935</div>
                <div align="right">3,929</div>
                <div align="right">1,762</div>
                <div align="right">756</div>
                <div align="right">739</div>
                <div align="right">350</div>
            </td>
            <td>
                <div align="right">2,753</div>
                <div align="right">621</div>
                <div align="right">211</div>
                <div align="right">70</div>
                <div align="right">20</div>
                <div align="right">60</div>
            </td>
            <td>
                <div align="right">2,950</div>
                <div align="right">2,173</div>
                <div align="right">1,616</div>
                <div align="right">652</div>
                <div align="right">841</div>
                <div align="right">135</div>
            </td>
            <td>
                <div align="right">402</div>
                <div align="right">177</div>
                <div align="right">145</div>
                <div align="right">18</div>
                <div align="right">6</div>
                <div align="right">22</div>
            </td>
            <td>
                <div align="right">577</div>
                <div align="right">143</div>
                <div align="right">166</div>
                <div align="right">9</div>
                <div align="right">31</div>
                <div align="right">11</div>
            </td>
            <td>
                <div align="right">253</div>
                <div align="right">142</div>
                <div align="right">59</div>
                <div align="right">14</div>
                <div align="right">4</div>
                <div align="right">10</div>
            </td>
            <td>
                <div align="right">346</div>
                <div align="right">117</div>
                <div align="right">94</div>
                <div align="right">6</div>
                <div align="right">25</div>
                <div align="right">10</div>
            </td>
            <td>
                <div align="right">83</div>
                <div align="right">72</div>
                <div align="right">22</div>
                <div align="right">7</div>
                <div align="right">2</div>
                <div align="right">2</div>
            </td>
            <td>
                <div align="right">85</div>
                <div align="right">53</div>
                <div align="right">38</div>
                <div align="right">3</div>
                <div align="right">11</div>
                <div align="right">6</div>
            </td>
        </tr>
        <tr>
            <td><div align="center">Sum</div></td>
            <td><div align="center">-</div></td>
            <td><div align="right">3,804</div></td>
            <td><div align="right">15,471</div></td>
            <td><div align="right">3,753</div></td>
            <td><div align="right">8,367</div></td>
            <td><div align="right">770</div></td>
            <td><div align="right">937</div></td>
            <td><div align="right">482</div></td>
            <td><div align="right">598</div></td>
            <td><div align="right">188</div></td>
            <td><div align="right">196</div></td>
    </table>

    The list of StackOverflow bugs based on tag and keywords is presented in the file [Dataset_init/SO_init/SO_init.csv](Dataset_init/SO_init/SO_init.csv).
2. **Manual_Labelling** folder: In this folder, we have placed all the files associated with our manual labelled result. For the bugs, we further annotate `Symptom`, `Source of Bug`, `Bug Type` and `Root cause`.

    Noted that bugs in `Documentation` and `Others` are excluded from root cause analysis because of their irrelevance to the core FL functions, and bugs from Pull Requests (PRs) are excluded from `Symptom` because in our observations, most PRs are submitted by framework developers or maintainers with limited information.
3. **Quantitative_Study** folder: In this folder, we have placed the source data from Quantitative Study in Section 7.1. In the lifecycle file from Github, we annotate the creation time, closing time and lifecycle.
   In the lifecycle file from StackOverflow, we annotate the creation time, last active time and lifecycle.

    In files of patch size, we annotate the number of added lines, deleted lines, the total number of lines, and changed files.

For the fix strategy, since some instances do not have a clear fix strategy, we summarize some common fix strategies and analyze which root cause can be fixed by them.

**The relationship table between symptom and root cause**:  

<div align=center>
    <img src="Relationship_between_symptom_and_root_cause.svg" width="650">
</div>

**The relationship table between fix strategy and root cause**:  

<div align=center>
    <img src="Relationship_between_fix_and_root_cause.svg" width="650">
</div>

