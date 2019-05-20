# RCA for AESEDI-53447

## Date
8888-08-08

## Authors
*OpsDev Team*

## Status
Closed, Resolved

## Summary
Customer XYZ data was not sent from AES EDI. Investigation revealed that 
the file with the data was sent, but it did not get processed due to an issue with the AES CIS service (*Please refer to Jira Issue No. AESCIS-38263*).

## Impact
About 486,000 records were affected and the EDI to CIS monitoring service too.

## Root Cause
File with the data was sent but did not get processed due to an issue with the AES CIS service.
Reference: Jira Issue No. AESCIS-38263

## Trigger
Jira Issue No. AESCIS-38263

## Resolution
The *AES CIS* monitoring service was reset. The file was resent and the issue got resolved. The missing records were discovered at 11:56 AM, processed at 1:00 PM.

## Detection
*No automated alert due to EDI to CIS monitoring issue. Missed records were not discovered automatically. User had to report it: Customer XYZ created ticket AESEDI-53447 to alert for the problem. 


## Action Items
| Action Item | Type | Owner | Bug |
| ----------- | ---- | ----- | --- |
| Writing of monitoring policy to detect missing records | prevent | OpsDev | **DONE** |
| Monitoring of the data ingestion and processing services (ETL) | prevent | OpsDev | (Jira Issue No: AESCIS-38263)**TODO** |

## Lessons Learned
We should never assume that files are processed successfully.
We have to add more monitoring plugins and modules to constantly monitor if the files sent via AES EDI have been successfully processed.


## Timeline

8888-08-08 (*all times UTC*)

| Time  | Description |
| ----- | ----------- |
| 11:56 | Discovering of the missing records |
| 12:00 | Troublesahooting, Restarting of the AES CIS monitoring module |
| 12:15 | Customer asked to resend file. Starting of the data processing of the records |
| 13:00 | Completion of the data processing of all the 486,000 records |
| 13:15 | Problem report created, relevant action items are created. Customer communication for follow-up actions. |

Supporting Information: 

Jira issue No. AESCIS-38263
