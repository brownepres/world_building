I will attempt to simulate the population of [[City 1 ( name tdb)]] along a few parameters, trying to make it representative. 
The output I expect is a csv file with 35200 + 2800 instances, to make it a 10% sample of the original population number of the city. 

Things to simulate: 
- Age
- Sex
	- Should be around 50-50 but do some research
- Job
	- Create a list of jobs with weights and randomly pick
- Monthly income
	- Use dollars and figure out money systems, how much is how much. According that make distribution for each classes monthly income, make distributions overlapping
	- Use germany income distribution for sampling: https://germanpedia.com/income-distribution-germany/
	- Based on the german income distribution I have created a lognormal distribution (mu and sigma are in the constants.py file) which then I can sample using numpy for random incomes. Now i should find a way to sample according to cast. Or should I create 4 different lognorm distributions for all 4 casts? 
- Family status
	- Not sure if it is necessary right now
- Number of kids
	- Again, distribution very right leaning, make them overlapping, it is not entirely dependent on the class itself
- Home distance from city centre (km)
	- 4th cast lives far away, others are pretty much mixed in the city. Calculate city width and use distance approximations. 


### 4th cast: 
Age: 
	- Median is 30
	- Ageing index is 45.0
	- Simulate it using El Salvadors popoulation age pyramid: https://www.census.gov/popclock/world/es
	- Sampling is done through weighted uniform sampling, different weights for women and men
- Sex: 
	- 49-51 for women
- Job: 
- Monthly income
	- Around 17% lower than the average 
- Family status
- Number of kids
- Home distance from city centre

### 3rd cast: 
Age: 
	- Using urugay as a still young yet older than El Salvador in terms of population. 
	- Median age is 36
- Sex: 
	- 49-51 for women
- Job: 
- Monthly income
- Family status
- Number of kids
- Home distance from city centre

### 2nd cast: 
Age: 
	- Using Australia as an example for population pyramid
	- Median age: 38
- Sex: 
	- 49.5-51.5 for women
- Job: 
- Monthly income
- Family status
- Number of kids
- Home distance from city centre

### 1st cast: 
Age: 
	- Using Germany as an example for population pyramid, as a rapidly aging population
	- Median age: 46.7
- Sex: 
	- 49-51 for women
- Job: 
- Monthly income
- Family status
- Home distance from city centre