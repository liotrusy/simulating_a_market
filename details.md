## Assumptions

In this model, we assume that the buyers and sellers interact directly in a shared marketplace. There are no intermediaries involved in the transaction therefore there will not be any transaction fees/costs.

## Questions

### Fundamental

* What is the object of the model (eg. the buyer, the seller, the market (log of bids/asks))?
* Is ownership of capital or goods verified?


### Implementation

1. Can there be more than one good/service type? Perhaps in the first version of this model we allow for only one type of good/service. For example, we create a market for apples.
2. What details buyers use to search for opportunities?
3. What details buyers/sellers are required to post regarding the bid? Are there optional details? This is important because it may require us to model bids and asks differently to allow for these differences.
4. Are there restrictions on the type of goods? If so, probably there will need to be an object for allowed goods.
5. Are only existing offers (bid/ask) logged in the book? Or may we also see historical transactions?
6. Are participants allowed to be both buyers and sellers? Or do they need to register for each side?

## Objects

What objects do we need to model?

### market_participant

    * id: String
    * roles: List or Dictionary
    * selected_market:
        * market_id: ??
        * highest_price: float
        * lowest_price: float
        * target_price: float

### offer

    * type: String
    * unit_price: float
    * units: Inter
    * time_stamp: DateTime
    * type: String - may not be needed
    * lifetime: integer. -1 for good until filled, 0 immediate or cancel, *n* for number of [minutes, hours, days] available
    * total_price: unit_price * units
    * expiry_time: time_stamp + lifetime
    * expired: Bool

### market

    * bids_log: List
    * asks_log: List
    * lowest_ask: float
    * highest_bid: float
    * spread: lowest_ask - highest_bid

