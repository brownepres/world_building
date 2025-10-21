In this essay I'll go through in a rather great extent in the simulation of population, the research, the whys and the maths behind it. The society of [[City 1 ( name tdb)]]  is caste based, four casts make up most of the cities population, which is a little below 400 000 souls. The casts dominate the everyday life, they all have different demographics, destinies, work they can do and so on. Therefore, it was important for me to simulate them as precisely as one possibly can. More information on the caste system and the castes is **here** (todo: add link)

By city population simulation I mean to create a system (a python class in my case) which enables me to generate an age, sex, and income representative 10% sample from the population of [[City 1 ( name tdb)]]. 

### Age
Age plays a crucial role, the destiny of societies are based upon their demographics, how many children are born, what percentage of the population is able to work, how many elderly people relies on the workers. Since in the caste system all castes are rigorously separated, they follow different demographics. 

**The fourth caste** - miners and farmers - live in the poorest conditions among all. Their demographics are pyramid like, containing more young people, due to having less access to protection, and families relying more on their children. Elderly are seldom, due to mostly inaccessible health care. Thus, originally, my idea was to use the demographics of Brazilian favelas to base the fourth caste on, however, the unreliable data convinced me otherwise. The median age for favela folks is around 30, which is similar to El Salvador, therefore the latter country has been chosen as the baseline for my fourth caste population. El Salvador's population pyramid is accessible through this [webpage](https://www.census.gov/popclock/world/es). The demographic bins and probabilities were collected in numpy arrays, and then simply sampled a demographic bin and an age from it. 

```
sampled_bin = np.random.choice(len(probabilities), size=sample_size, p=probabilities)

sampled_age = np.random.uniform(age_bins[bin_indices], age_bins[bin_indices + 1])
```

**The third caste** - physical labour workers - operates with a median age of 36, slightly older than the fourth caste. For this exact caste, Uruguay's population pyramid has been chosen as guideline, a still young, yet mostly working age population. The method was very similar than for the fourth caste. 

**The second caste** - office workers - are really similar to the third cast in the [[City 1 ( name tdb)]]. Therefore, I could not differ much in terms of age either, so I used Australia's population pyramid as a guideline, with the median age of a little below 38. 

**The first caste** - old aristocrats - immediately remind me of the elderly West-European population, like Switzerland, France, the Netherlands for example. In the end I have decided to use Germany's population pyramid, which is rapidly aging, just as my tiny aristocrat caste, with the median age of 46.7. 

[Age distribution]("age_pyramids.png")


### Income













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
	- I should probably use different mu for each cast, a little lower mean a lower a cast is. 
		- Simulation is done using age and cast dependent mu for every individual
- Family status
	- Not sure if it is necessary right now
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