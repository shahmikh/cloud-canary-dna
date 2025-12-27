## Day 2 – Step 2: S3 Data Events for Canary Activity

Enabled CloudTrail S3 Data Events to capture:
- PutObject
- GetObject

Verified by inspecting raw CloudTrail log files in S3.
Event History UI did not reliably show data events.

This step ensures accurate detection of canary file access.

