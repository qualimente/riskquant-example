# riskquant-example
This repository contains a simple example showing how to use Netflix's `riskquant` tool to calculate risk.  This code
supports the '[Computing a Risk Estimate using Netflix's riskquant](https://nodramadevops.com/2020/02/computing-a-risk-estimate-using-netflixs-riskquant/)' blog post on \#NoDrama DevOps.

See the blog post for full instructions on how to run the example.

Here's the short form:

Run riskquant inside a container:

```
docker container run --rm -it \
  -v "$(PWD)/data":/data/  \
  qualimente/riskquant --file /data/webapp.threat-model.csv
```
Check the results:

```
cat data/webapp.threat-model_prioritized.csv
``` 

which should produce something like:
```
WebLossConfPublic,Lose Prod User DB Confidentiality to Attacker,"$8,080"
WebLossAvailAnnual,Lose Availability,"$5,130"
WebLossConfInternal,Lose Prod User DB Confidentiality Internally,"$2,020"
WebLossAvailDaily,Lose Availability,$43
```
