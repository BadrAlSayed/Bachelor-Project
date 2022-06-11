# ResNet Domain Adaptation for Anomalous Sounds Detection
My bachelor project code where I added modifcations on the DCASE 2021 task 2 code submmited by Paul Primus.



## Setup



1. install [miniconda](https://docs.conda.io/en/latest/miniconda.html).
2. download the [data](http://dcase.community/challenge2021/task-unsupervised-detection-of-anomalous-sounds#download)
3. store unzipped data into folder `C:/Users/{yourUser}/shared/DCASE2021/task2` 
4. change dir to root of this project
5. run `conda env create -f environment.yaml` to install the conda environment
6. activate the conda environment with `conda activate dcase2021_task2`

**Hint:** Run your experiments with the `--debug` flag to check whether your environment is set up properly. 

## Run Auxiliary Classification Experimentns

To train a classifiers based on auxiliary classification (in this example for machine type fan), simply run:

```bash
python -m experiments.train multi_section --version auxiliary_classification --proxy_outliers other_machines --proxy_outlier_lambda 0.5 --machine_type fan
```
Options for proxy_outliers are {*none*, *other_machines*}. 


## Dashboard

To view the training progress/ results, change directory to the log directory (`cd logs`) and start the mlflow dashboard with `mlflow ui`.
By default, the dashboard will be served at `http://127.0.0.1:5000`.

## My Results
Here is the [google drive link](https://drive.google.com/drive/folders/15HczFHJsUAZAzYYQWwg2C7HMEjYFWkk0?usp=sharing) with my results.

## References

- Yohei Kawaguchi, Keisuke Imoto, Yuma Koizumi, Noboru Harada, Daisuke Niizumi, Kota Dohi, Ryo Tanabe, Harsh Purohit, and Takashi Endo. [*Description and discussion on DCASE 2021 challenge task 2: unsupervised anomalous sound detection for machine condition monitoring under domain shifted conditions*](https://arxiv.org/pdf/2106.04492.pdf). In arXiv e-prints: 2106.04492, 1–5, 2021. 
- Ryo Tanabe, Harsh Purohit, Kota Dohi, Takashi Endo, Yuki Nikaido, Toshiki Nakamura, and Yohei Kawaguchi. [*MIMII DUE: sound dataset for malfunctioning industrial machine investigation and inspection with domain shifts due to changes in operational and environmental conditions*](https://arxiv.org/pdf/2105.02702.pdf). In arXiv e-prints: 2006.05822, 1–4, 2021.
- Noboru Harada, Daisuke Niizumi, Daiki Takeuchi, Yasunori Ohishi, Masahiro Yasuda, and Shoichiro Saito. [*ToyADMOS2: another dataset of miniature-machine operating sounds for anomalous sound detection under domain shift conditions*](https://arxiv.org/pdf/2106.02369.pdf). arXiv preprint arXiv:2106.02369, 2021.

## Citation
If you use any parts of the implementation please cite this report:
```
@techreport{Primus2021DCASEChallenge,
    Author      =   {Primus, Paul and Zwifl, Martin and Widmer, Gerhard},
    institution =   {{DCASE2021 Challenge}},
    title       =   {CP-JKU Submission to DCASE'21: Improving Out-of-Distribution Detectors for Machine Condition Monitoring with Proxy Outliers \& \\ Domain Adaptation via Semantic Alignment},
    month       =   {June},
    year        =   2021
}
```

If you use the ResNet model or the model implementation please cite the following paper:
```
@inproceedings{Koutini2019Receptive,
    author      =   {Koutini, Khaled and Eghbal-zadeh, Hamid and Dorfer, Matthias and Widmer, Gerhard},
    title       =   {{The Receptive Field as a Regularizer in Deep Convolutional Neural Networks for Acoustic Scene Classification}},
    booktitle   =   {Proceedings of the European Signal Processing Conference (EUSIPCO)},
    address     =   {A Coru\~{n}a, Spain},
    year        =   2019
}
```

## Links
- [DCASE Community](http://dcase.community/)
- [PyTorch Lightning](https://github.com/PyTorchLightning/pytorch-lightning)
- [mlflow](https://mlflow.org/)
