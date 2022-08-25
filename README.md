<h2 align="center">Sovereign Data Exchange in Cloud-Connected IoT using International Data Spaces</h2>

<div align="center">
    Raw experiment results from a data sovereign message exchange in an IoT use case.
</div>



## Table of Contents

- [About](#about)
- [Cite this work](#cite-this-work)
- [Structure](#structure)
  - [Folder Structure](#folder-structure)
  - [File Structure](#file-structure)
- [License](#license)
- [Contact](#contact)


    
## Cite This Work
    
If use this work, please cite our [paper](https://ieeexplore.ieee.org/document/9659028)
   
```
@inproceedings{qarawlus2021sovereign,
  title={Sovereign Data Exchange in Cloud-Connected IoT using International Data Spaces},
  author={Qarawlus, Haydar and Hellmeier, Malte and Pieperbeck, Johannes and Quensel, Ronja and Biehs, Steffen and Peschke, Marc},
  booktitle={2021 IEEE Cloud Summit (Cloud Summit)},
  pages={13--18},
  year={2021},
  organization={IEEE}
}
```

## About

In order to enable data sovereign message exchange, the [International Data Spaces (IDS)](https://www.isst.fraunhofer.de/en/expertise/international-data-spaces.html) is one of the biggest initiatives, led by the [International Data Spaces Association (IDSA)](https://internationaldataspaces.org/) for business ecosystems. To allow Internet of Things (IoT) devices with its limited hardware resources to join, we developed two communication schemes based on the request/response and publish/subscribe paradigms.

Both approaches are tested in a simulated use case. We have made five experiments with durations of 30, 60, 120, 180 and 240 seconds, each experiment 30 times in a row to reduce outliers. The CPU usage on consumer side, the duration and the number of exchanged IDS messages are recorded.

This repository contains all the recorded data as raw `.csv` files and partly visualized in plots.



## Structure

### Folder Structure

The structure of the repository looks as follows:

```
    .
    ├── plots                    # Visualized average CPU usage for all 5 experiments
    ├── publish-subscribe        # Raw .csv data for all publish-subscribe experiments,
    │   ├── 240seconds-30passes  # ↳ one folder for every experiment, each consists of
    │   ├── 180seconds-30passes  # ↳ one file for CPU metrics, duration and message count
    │   ├── 120seconds-30passes
    │   ├── 60seconds-30passes 
    │   └── 30seconds-30passes
    ├── request-response         # Raw .csv data for all request-response experiments,
    │   ├── 240seconds-30passes  # ↳ one folder for every experiment, each consists of
    │   ├── 180seconds-30passes  # ↳ one file for CPU metrics, duration and message count
    │   ├── 120seconds-30passes
    │   ├── 60seconds-30passes 
    │   └── 30seconds-30passes
    └── ...
```



### File Structure

Every folder in the above mentioned structure contains the following files:

- **cpu-usages.csv**: Contains the recorded CPU usage on consumer side. One row for each pass. The first column is used as an index to indicate the ID of the pass. The original data source was [Prometheus](https://github.com/prometheus/prometheus), exported with the `rate(container_cpu_user_seconds_total{name="consumer"}[6s])` command.
- **duration.csv**: Contains the message duration in seconds. One row for each pass, where the first row shows the labels. The first column is used as an index to indicate the ID of the pass.
- **message-count.csv**: Contains the number of exchanged IDS messages. One row for each pass, where the first row shows the labels. The first column is used as an index to indicate the ID of the pass.



## Contact

- [Haydar Qarawlus](https://github.com/hqarawlus) ([Fraunhofer ISST](https://www.isst.fraunhofer.de/en.html))
- [Malte Hellmeier](https://github.com/mhellmeier-ISST) ([Fraunhofer ISST](https://www.isst.fraunhofer.de/en.html))
- [Johannes Pieperbeck](https://github.com/jpieperbeck) ([Fraunhofer ISST](https://www.isst.fraunhofer.de/en.html))
- [Ronja Quensel](https://github.com/ronjaquensel) ([Fraunhofer ISST](https://www.isst.fraunhofer.de/en.html))
- [Steffen Biehs](https://github.com/steffen-biehs) ([Fraunhofer ISST](https://www.isst.fraunhofer.de/en.html))
- Marc Peschke ([Fraunhofer IML](https://www.iml.fraunhofer.de/en.html))



## License

Copyright © 2021 Fraunhofer ISST + Fraunhofer IML. Distributed under the Apache-2.0 License. See `LICENSE` for more information.



This work was partially funded by the ["Silicon Economy Logistics Ecosystem (SELE)"](https://www.silicon-economy.com/) project. The project "Silicon Economy Logistics Ecosystem" is [funded by the German Federal Ministry of Transport and Digital Infrastructure](https://www.bmvi.de/SharedDocs/DE/Artikel/DG/KI-Projekte/silicon-economy-logistics-ecosystem.html).

<div align="center">
    <a href ="https://www.bmvi.de/SharedDocs/DE/Artikel/DG/KI-Projekte/silicon-economy-logistics-ecosystem.html">
        <img src="https://user-images.githubusercontent.com/84436467/129734305-edafd0eb-81ac-4ad0-9369-47299c9c0d16.png" alt="Foerderungshinweis BMVI" width="250" />
    </a>
</div>
