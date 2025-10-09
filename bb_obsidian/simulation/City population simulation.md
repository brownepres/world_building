I will attempt to simulate the population of [[City 1 ( name tdb)]] along a few parameters, trying to make it representative. 
The output I expect is a csv file with 35200 + 2800 instances, to make it a 10% sample of the original population number of the city. 

Things to simulate: 
- Age
	- Find a distribution for each cast, lower class generally younger while aristocrats are older
	- Lower cast: 
		- Median is 30
		- Ageing index is 45.0
		- Simulate it using El Salvadors popoulation age pyramid: https://www.census.gov/popclock/world/es
- Sex
	- Should be around 50-50 but do some research
- Job
	- Create a list of jobs with weights and randomly pick
- Monthly income
	- Use dollars and figure out money systems, how much is how much. According that make distribution for each classes monthly income, make distributions overlapping
- Family status
	- Not sure if it is necessary right now
- Number of kids
	- Again, distribution very right leaning, make them overlapping, it is not entirely dependent on the class itself
- Home distance from city centre (km)
	- 4th cast lives far away, others are pretty much mixed in the city. Calculate city width and use distance approximations. 
