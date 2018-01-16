# Best Time to Buy and Sell Stock II

Say you have an array for which the ith element is the price of a given stock on day i.

Design an algorithm to find the maximum profit. You may complete as many transactions as you like (ie, buy one and sell one share of the stock multiple times). However, you may not engage in multiple transactions at the same time (ie, you must sell the stock before you buy again).

----

```javascript
const maxProfit = prices => {
  if(prices.length < 2) return 0;

  const len = prices.length;
  const trend = prices.map((current, index) => {
    if(index < len - 1) {
        return prices[index + 1] - current
    }
  });
  return trend.slice(0, -1).filter(x => x >= 0).reduce((prev, next) => prev + next, 0);
};
```
