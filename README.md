# Computational social science
World building is a super nerd hobby which I have picked upon lately. This project is by no means ready but I really enjoy it \

## What do you find in this repository
In this repository I attempt to build a simulated society in a bottom-up fashion combining with fantasy world building. In practice it means that I have thought about a superficial society living in a fantasy world, all of its constrains, societal dynamics, physical wordly setups and so on. Shortly, my society is caste based (4 castes, upper, two working and one lower) where long range transportation is highly limited. \
The bottom-up simulation means that I simulate the population first, then the households (this is where I am now), from households I can calculate certain economical values as well and I will eventually end up with all the information I need to calculate my societies GDP and other measurements. While doing this, I can simulate shock impulse response functions in, to see how an artificial war would effect my artificial society, or how bad crops would change birth rate etc. 

# How do I simulate society? 
Well, this is the tricky part. For population simulation I used certain probability functions to take samples from (like income in a society usually follows a lognormal distribution, I just had to calculate the right sigma and mu parameters. Once I have the population sample I can use that to move on to households and so on. 
