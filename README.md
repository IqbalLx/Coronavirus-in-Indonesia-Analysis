# Coronavirus-in-Indonesia-Analysis

In this repository we aim to predict the peak of coronavirus cases in Indonesia, and when this pandemic will end. The data is retrieved from https://www.kawalcovid19.id/

## Overview Cases in Indonesia
The current graph of coronavirus in Indonesia per 21 Apr 2020
![alt text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/Current%20Cases.png)<br/>
As we can see, there is **exponential trends in Indonesia cases**

## Exponential Regression
This is the worst-prediction with only using Exponential Regression
![alt text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/Exponential%20Regression.png)
<br/> By using this method only we see that the number of Infected keep increasing over time, this happens because the curve is exponential, and it is not bounded which is by the total population.

## SEIRD Model 
SEIRD model is an advancement from basic SIR model, here we add 2 new compartments, Exposed and Death.
![alt text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/SEIRD%20Infected%20Prediction.png)
<br/> Here we try to fit to the current value (real value) but the line is still not well fitted to the line because we only set the value of parameters from the model using clinical variables. We currently working about how to pick params value based on optimization to the real dataset.
We can see that **the peak of coronavirus cases in Indonesia is in 25 May**, so we're still on early cases. **And the curve flattened in somewhere between early September until the middle of September,** there is when this pandemic will predictly end in Indonesia.

This model assume the population is only 40M, not all Indonesian current population which is 267,7M. It's because SEIRD model assume that everyone in population is susceptible, so when we using higher number of population, the line is very not well-suited to the real cases. Here is the full SEIRD model graph
![alt text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/SEIRD%20ll%20Prediction.png)
<br/>

## SEIRD Model with Optimized Parameters
You can see the code belongs to this in the nightly ver file above. All parameters used for SEIRD model there being optimized to fit with the current dataset (per 21 Apr 2020 Indonesian coronavirus data). Here some different result we got from the model result <br/>
![alt-text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/ver%202/SEIRD%20Optimize%20Infected.png)<br/>
![alt-text](https://raw.githubusercontent.com/IqbalLx/Coronavirus-in-Indonesia-Analysis/master/snapshot/ver%202/SEIRD%20Optimize%20All.png)<br/>
It's say that **the peak of coronavirus cases in Indonesia is in 20 May and will last until somewhere between the end of July until early August**

## Reference project and article: 
- https://towardsdatascience.com/infectious-disease-modelling-part-i-understanding-sir-28d60e29fdfc - Basic explanation of SIR model for Infectious Disease Modeling
- https://drive.google.com/file/d/1XSBQFWstqz__vYwobC-91LQ0BYo968r8/view?usp=sharing - A SIRU model for simulating coronavirus cases in Indonesia by Ikatan Alumni Matematika Universitas Indonesia (ILUNI)
- https://towardsdatascience.com/infectious-disease-modelling-beyond-the-basic-sir-model-216369c584c4 - A guide how to code SIR model in Python
- https://www.lewuathe.com/covid-19-dynamics-with-sir-model.html - Optimize SIR parameters

## Disclaimer
**We are neither a virologist nor epidemiologist**, so we cant sure that our prediction is 100% correct. It can be faster or slower for this pandemic end in Indonesia, also the number of people Infected may higher or lower than the model prediction. This is just us who curious about the technique behind simulating an epidemic with various scenario. **All finding from the code cant be interpreted as professional advice.** To learn more about coronavirus in Indonesia please visit https://www.covid19.go.id/
