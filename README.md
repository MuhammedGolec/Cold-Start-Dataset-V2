# Google-Cloud-Functions---Cold-Start-DatasetV2 (INDUSTRY 4.0-based)

The dataset was created by modeling a production line that operates continuously between 09.00-18.00 between 1-6 January 2024. Every 5 minutes, the data previously disclosed in the predictive maintenance dataset, which is assumed to be taken from the sensors on the synchronous motors, is sent to the SVC ML model deployed on the server. To model a real production line, different numbers of concurrent requests were created using Apache J-Meter. The prediction results obtained from the SVC model and the logs containing transaction information are recorded with a code script to obtain a cold start dataset. Fig 1 shows the cold start dataset and cold start occurs in the following three cases:

1) When the first request comes to the server. Since containers will be initialized for the first time, initializing dependencies such as function libraries requires a certain amount of time. This period causes a cold start delay.

2) When more than 300 requests come to the server. In the Industry 4.0 scenario, more than 300 requests are the time required to start a new container. This is why a cold start situation occurs.

3) If there is no request to the server for more than 15 minutes, containers are released in accordance with the policy implemented by GCP. A cold start occurs if new requests come to the released containers.

In the dataset, the latency amount was measured as 650-850 ms for cold start situations and 0-50 ms for non-cold start situations. Additionally, RAM and CPU usage rates are examined in this dataset as they may give a clue for a cold start situation. The environment parameters for GCP Cloud Functions used when creating the dataset are as follows.


Environment Parameters for GCP-Cloud Functions are as follows:


| Name     | Character |
| ---      | ---       |
| Trigger Type | HTTP  |
| RAM     |512 Mb     |
| Software Language     | Python 3.10       |
| Region     | europe- southwest1-a  |
