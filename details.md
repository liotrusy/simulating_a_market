## Assumptions

In this model, we assume that the buyers and sellers interact directly in a shared marketplace. There are no intermediaries involved in the transaction therefore there will not be any transaction fees/costs.

## Objects

What objects do we need to model?

* market_participant
    * buyer: Bool
    * highest_price: float
    * lowest_price: float
    * target_price: float

* offer
    * price: float
    * type: String - may not be needed
    * lifetime: integer. -1 for good until filled, 0 immediate or cancel, *n* for number of minutes available
