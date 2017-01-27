# Update-NiFi-Connection-via-API

## Short Description

Recently a customer asked me how to change destinate of a connection which still contains data, but the destination is stopped, I am trying to demonstrate the same from command line.

## Introduction

Using NiFi REST Api we can change the flow, here in this article I am trying to capture steps to update destination of a connection using REST API.

## Prerequisites

1) Make sure HDF-2.x version of NiFi is up an running
2) Minimum 3 processors are on the canvas with connection like below:

![alt tag](https://github.com/jobinthompu/Update-NiFi-Connection-via-API/blob/master/Images/data_flow_before.jpg)

3) Note the destination's uuid [In my case 'PutNext' processor's uuid]

![alt tag](https://github.com/jobinthompu/Update-NiFi-Connection-via-API/blob/master/Images/PutNext_uuid.jpg)

4) Note the uuid of the connection that has to be made to the 'PutNext' processor

![alt tag](https://github.com/jobinthompu/Update-NiFi-Connection-via-API/blob/master/Images/Connection.jpg)

## 'GET'ing the details of connection

1) Execute the below command on your terminal with uuid of the connection:

```
curl -i -X GET http://localhost:8080/nifi-api/connections/dcbee9dd-0159-1000-45a7-8306c28f2786 
```

2) 