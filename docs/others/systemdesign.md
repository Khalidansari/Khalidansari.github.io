---
layout: default
---
# System Design

## Reliable
Service works as expected. E.g.The service should complete the task without losing any data.

## Available
Service should not be down. Also, called as uptime.

## Minimum Latency
Should respond in 3 secs for example

## Throughput
Total data served per sec

## Consistency
E.g. a photo which I should see in my feed is available with a little delay. May be 5mins late. Latency sometimes is improved at the cost of consistency.


## Approx metrics

Total users - 500 million
Daily login - 1 million
Daily upload of data (photos/tweets) 2million = 20 per sec
