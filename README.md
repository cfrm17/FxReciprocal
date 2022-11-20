# Pricing FX Reciprocal Average Rate Contract


This article presents a valuation model for Noon Average Rate Contract (NRC) and Reciprocal Average Rate Contract (NRC 1). NRC is a forward contract on average foreign exchange rate and NRC 1 is a forward contract on reciprocal of average foreign exchange rate.

Consider a forward contract on the average foreign exchange rate.  Notations used as follows.

t	Valuation Date
T	Maturity Date
 
Settlement Date
 
Spot Exchange Rate at time  

 
Risk-free discount rate of currency Ccy
 
Averaging start date
K	Strike price
 
Historical exchange rate at time  

 
Forward exchange rate for time interval (t,  ), where  

N	Notional amount

The average exchange rate,  , with m historical rate averaging points and n spot rate averaging points, is computed as

     if   ,  and        if   .

where  ,   and   if  , and   if  .  

The average forward rate,  , is then computed as

   if   ,  and      if   

and the forward exchange rate is computed as  , where  . 

The actual pricing (Mark-to-Market) is done at the inventory level and is in the base currency, which is usually USD. 

Direct quote 

The rates are quoted as  . There are 4 possible cases depending on the notional currency and payoff currency. 


1.   and payoff currency = USD : NRC

The payoff at the maturity is defined as   in USD. Thus, the expected payoff is calculated as  . The arbitrage-free price of the contract in USD is then obtained by discounting the expected payoff from the settlement date to the valuation date.

 		(1)

where   is the USD discount factor between the settlement date to the valuation date.

2.   and payoff currency = EUR : NRC 1

The payoff at the maturity is defined as   in EUR and the expected payoff is then calculated as  . Here, the approximation   used in this relation, in general, does not hold.  

However, this is a good approximation when the volatility of   is relatively small, which is usually the case for exchange rates. The arbitrage-free price of the contract in USD is then obtained by multiplying the expected payoff by the forward rate,  , and by discounting it with USD from the settlement date to the valuation date.

        	  	           (2)

3.   and payoff currency = USD : NRC

The payoff at the maturity is defined as   in USD and the expected payoff is  . The arbitrage-free price of the contract in USD is then given by

 		(3)

4.   and payoff currency = EUR : NRC 1

The payoff at the maturity is defined as   in EUR and the expected payoff is approximated as  . Again, the arbitrage-free price of the contract in USD is obtained by multiplying the expected payoff by the forward rate,  , and by discounting it with USD. Thus, 

   	           (4)


where   (1 or –1) is the long/short indicator. For all of the above cases, the dollar value Delta in USD is computed as

USD Delta                                         (5)

where   is the spot exchange rate and the perturbation on the spot rate   is set to be 0.00005. This dollar value delta is used for daily hedging. 


Indirect quote

The rates are quoted as  . Again, there are 4 possible cases depending on the notional currency and payoff currency.

1.   and payoff currency = CAD : NRC

The payoff at the maturity is defined as   in CAD and the expected payoff is then calculated as  . The price of the contract in USD is obtained by dividing the expected payoff by the forward rate,  , and by discounting it with USD

 	  	  (6)

2.   and payoff currency = USD : NRC 1

The payoff at the maturity is defined as   in USD and the expected payoff is approximated as  . The price of the contract in USD is then given by

    	             (7)

3.   and payoff currency = CAD : NRC

The payoff at the maturity is defined as   in CAD. Similar to case 1, the price of the contract in USD is then given by

  		     (8)

 
4.   and payoff currency = USD : NRC 1

The payoff at the maturity is defined as   in USD. Similar to case 2, the price of the contract in USD is then given by

      		      (9)

The price of the contract and the perturbation of the spot rate in delta calculation is in USD/CAD. Thus, the perturbation of the spot is done as   and   where  . Thus, for all of the above cases, the USD Delta is defined by

USD Delta =                                          (10)

It is possible that matured NRC could be in the system (not paid out to clients) and, thus, daily Mark-to-Market and Delta calculation are also done on those matured NRCs. The first case in table 1 and 2 deals with a matured NRC and the pricing of 4 sub cases need to be modified. The equations (1) to (4) are modified for a matured NRC as follows.

 	,	    for Payoff Currency = USD    	(11)
   ,           for Payoff Currency = EUR     (12)
  ,	    for Payoff Currency = USD    	(13)
   ,           for Payoff Currency = EUR      (14)

where   is calculated only from historical rates. Note that the forward rate in equation (2) and (4) becomes the spot rate   in the above equations (12) and (14). Since the pricing in equations (12) and (14) involves the spot price which varies day-to-day, there is non-zero delta values on these cases (see 2nd and 4th sub cases of case 1 in table 2). 
 
Similarly, testing results for indirect quote are summarized in table 3 (pricing) and table 4 (USD delta). The pricing modification for a matured NRC is done as following.

  ,	    for Payoff Currency = CAD     	 (15)
  ,	    for Payoff Currency = USD       (16)
    ,     for Payoff Currency = CAD       (17)
   ,	    for Payoff Currency = USD       (18)

Again,   is calculated only from historical rates and the forward rate in equation (6) and (8) becomes the spot rate   in the above equations (15) and (17). Since the pricing in equations (15) and (17) involves the spot price which varies day-to-day, there is non-zero delta values on these cases (see https://finpricing.com/lib/EqBarrier.html). 

The 2nd case for both direct and indirect quote examines the case where the average rate includes historical rates as well as forward rates. The last 3 cases test with various maturity dates and strike prices. The results indicate that the QA model calculates consistently to FX NRC and NRC 1.  
