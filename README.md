# Lead Smelter's Production Time Estimator
## Background
* the company have 17 smelter with 11 primary kettle and 6 refining/alloying kettle
* every primary kettle had to smelt with specific material, and every material have different process step(1-3 step),as following : 

![Figure 1](https://github.com/boxside/Lead_Smelter-s_Production_Time_Estimator/blob/main/2.png)

* every material have different chemical composition, and different adjusted spesification time process.
* need to estimate smelting process due to prevent production delay caused by waiting time from 1 kettle to another kettle (max waiting time 1 hour)
##  problem
* make formulas to estimate time finished for every kettle with 4 batch daily
* make time conflicts detector from kettle that still in progress
* make auto querry adjusted spec. process time from material spec. index

##  methodology
* this estimator is made with ms. excel 2019
* formulas is used such as IF, Vlookup, Hlookup, conditional formatting, small, iferror,etc.
## results
 
 ![Figure 1](https://github.com/boxside/Lead_Smelter-s_Production_Time_Estimator/blob/main/4.png)

Column Dictionary :
* Proses : name of process
* Batch : spec of material
* No.kettle : index of kettle
* Tanggal : date process
* [Blank index] : additional a second due to preventive time conflicts each kettle
* Start Time : time process start
* Penyesuaian Spek : adjusted process time by spec.
* Process Done : time process end
* Waiting time : additional time due to waiting for tapping
* Transfer To : for transfer of material that need further process
* Tapping To : for tranfer to continuous casting 

Case 1 : kettle 1 first and second batch indicate that cc1 have conflict time with other(indicate the red cell in "tapping to" column), as we can see the detail conflict below:
 
 ![Figure 1](https://github.com/boxside/Lead_Smelter-s_Production_Time_Estimator/blob/main/6.png)
 
 Column Dictionary :
* Tapping Done : time of tapping done 
* Near batch tap : tapping done from the previous queue
* Queue No. : number of queue of continuous casting that want to tapping to

as we can see, k1a(kettle 1 ,1st batch) process is done at 01:15. it get number of queue is 7, which is must tapping after queue no 6, but no 6 tapping done in 02:00,
to prevent this conflict we need make k1a waiting to 02:00 (45mins) to tapping. it's still under the waiting limit (1 hour), then we have to input waiting time to 
this form and results as follow : 
 
  ![Figure 1](https://github.com/boxside/Lead_Smelter-s_Production_Time_Estimator/blob/main/1.png)
 
