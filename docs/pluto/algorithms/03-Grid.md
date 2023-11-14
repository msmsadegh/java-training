# Grid

## Inputs

- Fee Coefficient
- Maximum Inventory
- Time Interval

    
## Steps

   1. Grid Levels Computation: 
   ```python
   eachLevel = previousLevel * (1 + coefficient) / tickSize) * tickSize + tickSize
   ```
   2. Decision based on conditions:
        1. If it doesn't exist any previous orders:
        ```python
        comparatorPrice = lastTradePrice 
        ```
        else if it exists any previous filled order :
        ```
        comparatorPrice = lastFilledPriceOrder
        ```            
        else:
        do nothing until the next step

        2. Based on Cond 'a' decide to go to upper grid level or lower grid level and named it as targetValue
 
   3. Find the closest grid level to the buyer Price and placing order:
      1. Based on last filled order flag (Bid/Ask/Neutral):
         if flag is bid:
         ```python
         bidPrice = grid[targetValueIndex]
         askPrice = grid[targetValueIndex + 1]
         ```
         elif flag is asking:
        ```python
         bidPrice = grid[targetValueIndex - 1]
         askPrice = grid[targetValueIndex]
        ```
         elif flag is neutral:
        ```python
         bidPrice = grid[targetValueIndex]
         askPrice = grid[targetValueIndex + 1]
        ```
   4. Send orders with manageOrders function.

## Remarks

1. It shouldn't place the same three orders in a row
2. It shouldn't be placed the orders if a collision with the upper threshold has been held
3. It shouldn't place same order if the previous one is not filled
4. It shouldn't place order more than inventory volume