# Series Queues with infinite capacity - Open Jackson Network

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the each conveyor of (c) waiting time of each material in the system (d) waiting time of each material in each conveyor, if the arrival  of materials follow Poisson process with the mean interval time 12 seconds, service time of  lathe machine in series follow exponential distribution  with service time  1 second, 1.5 seconds and 1.3 seconds respectively and average service time of robot is 7 seconds.

## Software required :
Visual components and Python

## Theory

![image](https://user-images.githubusercontent.com/103921593/203239736-7b81f599-71a8-4ae7-b63e-5d98acd9ea54.png)


## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203239789-bc870dce-6727-487b-a0e2-4fc3f5114889.png)


## Experiment:
![image](https://private-user-images.githubusercontent.com/94747031/243261669-9e252a77-df6b-410c-b22b-2db70a586d97.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MzExNTMsIm5iZiI6MTcwMzQzMDg1MywicGF0aCI6Ii85NDc0NzAzMS8yNDMyNjE2NjktOWUyNTJhNzctZGY2Yi00MTBjLWIyMmItMmRiNzBhNTg2ZDk3LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE1MTQxM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU4NDA3ZjljYTkwNjE2MTgzYmZkNmQ3NTgxNzFhNDAzNDBiMWU1N2VkOWE3YjU3Njc3ZTQ2ODE1MzhkOWQxN2QmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.b17do9pFRcVqSXucRy4lkVV49EtCTQpKI6t-PXL_t_A)
![image](https://private-user-images.githubusercontent.com/94747031/243261678-323ed3a3-45ed-4559-9012-23d73369af6d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MzExNTMsIm5iZiI6MTcwMzQzMDg1MywicGF0aCI6Ii85NDc0NzAzMS8yNDMyNjE2NzgtMzIzZWQzYTMtNDVlZC00NTU5LTkwMTItMjNkNzMzNjlhZjZkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE1MTQxM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWFkOWJmN2Q0YTM3YmVmOGJkODQ2Yjc2ODFiMzJmNTE2MTg4YTNiZjI2ZGQwMTJjMWIzOTQ3MWZhZjE1MTE4MDcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.XSSb3nRejDS8YWMSFj_8dwA7GkFJat76MZscFCpNFo8)

## Program
```
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time1=float(input("Enter the mean  inter service time of Lathe Machine 1 (in secs) :  "))
ser_time2=float(input("Enter the mean  inter service time of Lathe Machine 2 (in secs) :  "))
ser_time3=float(input("Enter the mean  inter service time of Lathe Machine 3 (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
lam=1/arr_time
mu1=1/(ser_time1+Robot_time)
mu2=1/(ser_time2+Robot_time)
mu3=1/(ser_time3+Robot_time)
print("-----------------------------------------------------------------------")
print("Series Queues with infinite capacity- Open Jackson Network")
print("-----------------------------------------------------------------------")
if (lam <  mu1) and (lam <  mu2) and (lam <  mu3):
    Ls1=lam/(mu1-lam)
    Ls2=lam/(mu2-lam)
    Ls3=lam/(mu3-lam)
    Ls=Ls1+Ls2+Ls3
    Lq1=Ls1-lam/mu1
    Lq2=Ls2-lam/mu2
    Lq3=Ls3-lam/mu3
    Wq1=Lq1/lam
    Wq2=Lq2/lam
    Wq3=Lq3/lam
    Ws=Ls/(3*lam)
    print("Average number of objects in the system S1 : %0.2f "%Ls1)
    print("Average number of objects in the system S2 : %0.2f "%Ls2)
    print("Average number of objects in the system S3 : %0.2f "%Ls3)
    print("Average number of objects in the overall system    : %0.2f "%Ls)
    print("Average number of objects in the conveyor S1  :  %0.2f "%Lq1)
    print("Average number of objects in the conveyor S2  :  %0.2f "%Lq2)
    print("Average number of objects in the conveyor S3  :  %0.2f "%Lq3)
    print("Average waiting time of an object in the conveyor S1 : %0.2f secs"%Wq1)
    print("Average waiting time of an object in the conveyor S2 : %0.2f secs"%Wq2)
    print("Average waiting time of an object in the conveyor S3 : %0.2f secs"%Wq3)
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("----------------------------------------------------------------------")
```

## Output
![image](https://private-user-images.githubusercontent.com/94747031/243261541-d61c45cf-04e3-4052-aeb4-ebb3cbe9ac2d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MzExNTMsIm5iZiI6MTcwMzQzMDg1MywicGF0aCI6Ii85NDc0NzAzMS8yNDMyNjE1NDEtZDYxYzQ1Y2YtMDRlMy00MDUyLWFlYjQtZWJiM2NiZTlhYzJkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE1MTQxM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTNkNjNmOGE1YjI1MmQ1OTYxN2ZiZjYyYzUwODU4MzI4N2ViYmVmMDA1YjYyMDM5ZmU0ZGJhMjhmYmQyNmY3MzkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.Cgms8hVH4mnNNsIWJIpUjmjqZGJjOwzGSvKcSzRczQQ)

## Result
The average number of material in the sysytem and in the conveyor and waiting time are successfully found.
