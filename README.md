# Bayesian Analysis of Airline Safety

This project investigates whether fatal aviation incident rates have decreased between the periods 1985–1999 and 2000–2014. We apply **Bayesian model comparison** using two approaches:  
- Categorical model variable (`m`) in JAGS  
- Savage-Dickey density ratio  

We base our analysis on data from the [FiveThirtyEight Airline Safety dataset](https://github.com/fivethirtyeight/data/tree/master/airline-safety), originally sourced from the Flight Safety Foundation and the Aviation Safety Network.

---

## Research Question

**“Did the rate of fatal aviation incidents decrease between 1985–1999 and 2000–2014?”**

We test two models:
- `m0`: No difference in fatal incident rates (θ₁ = θ₂)
- `m1`: A difference exists (θ₁ ≠ θ₂)

---

##  Dependencies

Install system & Python packages:

```bash
# System
!apt install jags

# Python
!pip install pyjags daft matplotlib scipy numpy
```
---

## Dataset

- Airline name
- Number of incidents (1985–1999 and 2000–2014)
- Fatal incidents
- Fatalities

Dataset can be found [here](https://github.com/fivethirtyeight/data/tree/master/airline-safety).

---

## Methods
Model m0 (Null):
- Assumes no change in fatality rate
- Uses a shared θ for both periods
- Spike prior at c = 0.5
- Binomial likelihood

Model m1 (Alternative):
- Assumes θ₁ and θ₂ are different
- Uses Beta(1, 1) prior
- Binomial likelihood
- δ = θ₁ − θ₂ is calculated

---

## Conclusion
There is decisive evidence that fatal aviation incident rates have decreased between 1985–1999 and 2000–2014. Both Bayesian methods (JAGS + Savage-Dickey) consistently support the model that assumes improvement in airline safety.
