---
title: CLUE-LDS
---

- [Overview](#overview)
- [Environment](#environment)
- [Activity](#activity)
- [Contained Data](#contained-data)
- [Papers](#papers)
- [Links](#links)
- [Example Data](#example-data)

| <!-- -->                 | <!-- -->                                                             |
|--------------------------|----------------------------------------------------------------------|
| **Network Log Source**   | -                                                                    |
| **Network Logs Labeled** | -                                                                    |
| **Host Log Source**      | Events generated from usage of storage solution "hBox"               |
| **Host Logs Labeled**    | No, data generated in production -> no known attacks                 |
|                          |                                                                      |
| **Overall Setting**      | Enterprise IT                                                        |
| **OS Types**             | _n/a_ (focus on subsystem "hBox")                                    |
| **Number of Machines**   | _n/a_ (5000 distinct users)                                          |
| **Total Runtime**        | 1910 days                                                            |
| **Year of Collection**   | 2017-2022                                                            |
| **Attack Categories**    | _n/a_                                                                |
| **User Emulation**       | Real users                                                           |
|                          |                                                                      |
| **Packed Size**          | 640 MB                                                               |
| **Unpacked Size**        | 14,9 GB                                                              |
| **Download Link**        | [goto](https://zenodo.org/records/7119953/files/clue.zip?download=1) |

***

### Overview

CLUE-LDS (CLoud-based User Entity behavior analytics Log Data Set - that acronym really is a stretch but okay)is a
dataset generated by real user activity at the premise of an Austrian IT service provider over the span of five years.
It is intended to be used for User and Entity Behavior Analytics (UEBA), which tries to detect cases where an attacker
accesses a system through legitimate means, for example by using leaked credentials.
Since this doesn't ring any bells for systems designed to detect malware, exploits, etc., the goal is to recognize
this "illegal" access by determining if a user suddenly changed its behavior, which is monitored in form of events
originating from that user.

### Environment

The environment is that of a live production network of an Austrian IT provider, hosting the storage solution "hBox".

### Activity

Activity consists of actual users accessing and using a cloud storage (hBox) over the span of roughly five years,
leading to ~50 million events created by more than 5000 distinct users.

### Contained Data

The dataset has been anonymized, though the authors state that his has been done in such a way that no information was
lost (see section 3.B in paper).
Each event contains a user, the associated action and a couple other relevant fields such as location or paths.
More details regarding those fields are linked below.
Since this was collected in a productive environment, there are no known attacks contained in this dataset.

### Papers

- [A User and Entity Behavior Analytics Log Data Set for Anomaly Detection in Cloud Computing (2022)](https://doi.org/10.1109/bigdata55660.2022.10020672)

### Links

- [Homepage](https://zenodo.org/records/7119953)

### Example Data

Event logs from `clue.json`

```json
[...]
{
  "params": {
    "user": "marvellous-amaranth-fowl-accountant"
  },
  "type": "login_successful",
  "time": "2017-07-07T09:05:57Z",
  "uid": "marvellous-amaranth-fowl-accountant",
  "id": 58,
  "uidType": "name"
}
{
  "params": {
    "path": "/chinese-teal-meerkat-garagemanager/chosen-blue-marmoset-metallurgist/little-scarlet-warbler-reflexologist"
  },
  "type": "file_accessed",
  "time": "2017-07-07T09:06:00Z",
  "uid": "marvellous-amaranth-fowl-accountant",
  "id": 59,
  "uidType": "name"
}
{
  "params": {
    "path": "/chinese-teal-meerkat-garagemanager/chosen-blue-marmoset-metallurgist/thoughtful-blush-meerkat-producesupervisor"
  },
  "type": "file_accessed",
  "time": "2017-07-07T09:06:00Z",
  "uid": "marvellous-amaranth-fowl-accountant",
  "id": 60,
  "uidType": "name"
}
[...]
```