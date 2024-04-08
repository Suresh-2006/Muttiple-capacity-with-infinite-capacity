# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)

### Developed by : SURESH S
### Register number : 212223040215

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.


![318243325-b1e9bf7c-ee14-48ef-87b1-6c9be6b654f8](https://github.com/Suresh-2006/Muttiple-capacity-with-infinite-capacity/assets/149347611/76c7e07e-5672-440b-8218-8bdc97ffd9be)



## Procedure :
![318243327-5275a16e-343a-4dae-8de7-510e7c9dba60](https://github.com/Suresh-2006/Muttiple-capacity-with-infinite-capacity/assets/149347611/a8ffe8d5-47b1-421e-906f-3f8a52388ed7)





## Experiment:
![318243321-c8a25380-76d9-4510-800d-72fbb8519b26](https://github.com/Suresh-2006/Muttiple-capacity-with-infinite-capacity/assets/149347611/44c66d5b-9c6f-4eed-87a5-242cf18ba2cc)


![318243337-2c60c02f-ff8e-4804-b4e6-08e666f9272b](https://github.com/Suresh-2006/Muttiple-capacity-with-infinite-capacity/assets/149347611/3324fc42-17ab-4ebb-a33a-1403b971352e)

## Program :
```
import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
c=int(input("Number of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```

## Output :
![318243210-7d546668-1c2c-4483-9b01-45d174d3b45b](https://github.com/Suresh-2006/Muttiple-capacity-with-infinite-capacity/assets/149347611/9ec80389-066b-4677-af59-5130abf8bbaf)



## Result : 

Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
