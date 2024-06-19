# Tax Overview 

If the customer is not tax exempt and the product and variant are taxable, then the tax check is begun.

## Review !!!!

There are 2 tax options, each are mutualy exclusive: taxByState where each state has a different tax rate, or generic taxRate for all states.

If taxByState is enabled and there is a record that matches this carts shipping address, then the taxrate set in that record will be calculated against each cartProduct.

If taxByState is not enabled AND the taxRate (siteSettings table) is set above 0, each cartProduct is checked to see that the products taxtype is set to ‘tt_1’. If it is set to ‘tt_1’, then if either the sites state and the carts shipping address state must match, or the taxOutState feature is enabled, tax is calculated against the cartProduct.


Rewritting the above:

By default there is no tax rate applied to any orders
To set a tax rate
1. Set the global tax rate - ie the base rate that will be applied to all sales
2. Set the tax rates for individual states. 

Once the tax setting is active, Omni will first check for a state tax record rate. If there is none then then it defaults to the global tax rate. If the global tax rate is not set, a tax of $0 will be charged. In this case it will still be considered an order with 'tax', although it is taxed at $0.00. This is because 


DOUBLE CEHCK THE ABOVE!!!