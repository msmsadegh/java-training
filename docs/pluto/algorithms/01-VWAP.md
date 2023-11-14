# VWAP Algorithm

## Inputs:

- Volume
- Side
- Fraction Volume
- Interval Time
- Number Of Fractoions

## Algorithm Steps:
1. Compute the VWAP Price:
    ``` { .python }
    candlesDataFrame['ohl/3'] = (candlesDataFrame['open'] + candlesDataFrame['high'] + self.candlesDataFrame['low']) / 3
    candlesDataFrame['totalPrice'] = (candlesDataFrame['ohl/3'] * candlesDataFrame['volume']).cumsum()
    candlesDataFrame['totalVolume'] = candlesDataFrame['volume'].cumsum()
    candlesDataFrame['vwapPrice'] = candlesDataFrame['totalPrice'] / candlesDataFrame['totalVolume']
    vwapPrice = candlesDataFrame.iloc[-1]['vwapPrice']
   ```

2. While number Of Placed Orders not equal to number of fractions:
    
   1. If Side is Sell:
        1. Ask Price = Vwap Price 
        2. Ask Volume = min(fractionVolume, Asset)
   2. If Side is Buy:
        1. Bid Price = Vwap Price 
        2. Bid Volume = fractionVolume
       
   3. Send orders with manageOrders function.

## Remarks

