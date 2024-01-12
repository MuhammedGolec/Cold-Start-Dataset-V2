# Google-Cloud-Functions---Cold-Start-DatasetV2

The dataset was created by modeling a production line that operates continuously between 09.00-18.00 between 1-6 January 2024. Every 5 minutes, the data previously disclosed in the predictive maitanace dataset, which is assumed to be taken from the sensors on the synchronous motors, is sent to the SVC ML model deployed on the server. To model a real production line, different numbers of concurrent requests were created using Apache J-Meter. The prediction results obtained from the SVC model and the logs containing transaction information are recorded with a code script to obtain a cold start dataset. In Fig X shows the cold start dataset created.
