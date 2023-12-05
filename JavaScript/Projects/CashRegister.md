# Cash Register

> Design a cash register drawer function `checkCashRegister()` that accepts `purchase price` as the first argument (price), `payment` as the second argument (cash), and `cash-in-drawer` (cid) as the third argument. `cid` is a 2D array listing available currency.
> The `checkCashRegister()` function should always return an object with a `status` key and a `change` key.

Return `{status: "INSUFFICIENT_FUNDS", change: []}` if cash-in-drawer is less than the change due, or if you cannot return the exact change.

Return `{status: "CLOSED", change: [...]}` with cash-in-drawer as the value for the key change if it is equal to the change due.

Otherwise, return `{status: "OPEN", change: [...]}`, with the change due in coins and bills, sorted in highest to lowest order, as the value of the `change` key.

| Currency Unit       | Amount             |
| ------------------- | ------------------ |
| Penny               | $0.01 (PENNY)      |
| Nickel              | $0.05 (NICKEL)     |
| Dime                | $0.1 (DIME)        |
| Quarter             | $0.25 (QUARTER)    |
| Dollar              | $1 (ONE)           |
| Five Dollars        | $5 (FIVE)          |
| Ten Dollars         | $10 (TEN)          |
| Twenty Dollars      | $20 (TWENTY)       |
| One-hundred Dollars | $100 (ONE HUNDRED) |

See below for an example of a cash-in-drawer array:

```
[
  ["PENNY", 1.01],
  ["NICKEL", 2.05],
  ["DIME", 3.1],
  ["QUARTER", 4.25],
  ["ONE", 90],
  ["FIVE", 55],
  ["TEN", 20],
  ["TWENTY", 60],
  ["ONE HUNDRED", 100]
]
```

> Answer

```javascript
function checkCashRegister(price, cash, cid) {
  const currencyUnits = [
    ["PENNY", 0.01],
    ["NICKEL", 0.05],
    ["DIME", 0.1],
    ["QUARTER", 0.25],
    ["ONE", 1],
    ["FIVE", 5],
    ["TEN", 10],
    ["TWENTY", 20],
    ["ONE HUNDRED", 100],
  ];

  let changeDue = cash - price;
  let changeArray = [];

  // Calculate the total cash in the drawer
  let totalCID = cid.reduce((acc, curr) => acc + curr[1], 0);
  totalCID = totalCID.toFixed(2); // Fix floating-point precision issues

  // Helper function to get the index of a currency unit in the drawer
  function getIndex(unit) {
    return currencyUnits.findIndex((curr) => curr[0] === unit);
  }

  // Check if there is insufficient funds
  if (Number(totalCID) < changeDue) {
    return { status: "INSUFFICIENT_FUNDS", change: [] };
  }

  // Check if cash-in-drawer equals the change due
  if (Number(totalCID) === changeDue) {
    return { status: "CLOSED", change: cid };
  }

  // Iterate through currency units and provide change
  for (let i = currencyUnits.length - 1; i >= 0; i--) {
    const unit = currencyUnits[i][0];
    const unitValue = currencyUnits[i][1];
    const unitIndex = getIndex(unit);
    const availableCash = cid[unitIndex][1];

    // Calculate how much of this currency unit to give as change
    const unitsToGive = Math.min(
      Math.floor(changeDue / unitValue),
      availableCash / unitValue
    );
    const changeAmount = unitsToGive * unitValue;

    // Update change due and cash-in-drawer
    changeDue = (changeDue - changeAmount).toFixed(2);

    if (changeAmount > 0) {
      changeArray.push([unit, Number(changeAmount)]);
    }

    // Update cash-in-drawer array
    cid[unitIndex][1] = (availableCash - changeAmount).toFixed(2);

    // Check if change is complete
    if (changeDue == 0) {
      return { status: "OPEN", change: changeArray };
    }
  }

  // If change cannot be provided, return insufficient funds
  return { status: "INSUFFICIENT_FUNDS", change: [] };
}

// Example usage:
const result = checkCashRegister(19.5, 20, [
  ["PENNY", 0.01],
  ["NICKEL", 0],
  ["DIME", 0],
  ["QUARTER", 0],
  ["ONE", 1],
  ["FIVE", 0],
  ["TEN", 0],
  ["TWENTY", 0],
  ["ONE HUNDRED", 0],
]);

console.log(result);
```
