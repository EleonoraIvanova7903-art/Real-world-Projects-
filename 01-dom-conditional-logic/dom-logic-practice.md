# DOM Logic Practice – Real-World Mini Scenarios

This folder contains beginner-friendly but realistic DOM exercises focused on:

- `if / else` and `if / else if / else`
- logical operators `&&`, `||`, `!`
- chained conditional logic
- real user input via the DOM
- scalable structure for later refactoring with functions

The goal is to build strong logical thinking first, then gradually increase complexity without changing the core structure.

---

## Task 1: Event Registration Check

### Description
A simple registration scenario where access depends on age, ticket type, and accepting terms.  
This task focuses on **input validation first**, then **business rules**.

### UI Elements
- text input: age (`id="age"`)
- select: ticket type (`id="ticket"`)  
  Options: `standard`, `vip`
- checkbox: terms acceptance (`id="terms"`)
- button: submit (`id="btn"`)
- div: result message (`id="res"`)

### JavaScript Naming
- DOM elements:  
  `ageInput`, `ticketSelect`, `termsInput`, `button`, `result`
- Event handler:  
  `handleRegisterCheck`
- Working variables:  
  `ageValue`, `ticketValue`, `message`

### Rules (execute in this order)
1. If age is empty → `Enter your age.`
2. If age is not a number → `Age must be a number.`
3. If age < 16 → `You must be 16 or older.`
4. If terms are not accepted → `You must accept the terms.`
5. If ticket is `vip` AND age < 18 → `VIP is available from 18+.`
6. Otherwise → `Registration approved.`

### Test Data
- age: empty
- age: `abc`
- age: `15`
- age: `17` + ticket `vip`
- age: `20` + ticket `vip` + terms checked

### Future Upgrades
- add email field and validation
- add attempt counter and lock after multiple failures
- move validation and rules into separate functions

---

## Task 2: Delivery Fee Calculator

### Description
A delivery scenario based on city, order total, and express delivery option.  
This task trains **chained conditions with `&&` and `||`**.

### UI Elements
- text input: city (`id="city"`)
- text input: order total (`id="total"`)
- checkbox: express delivery (`id="express"`)
- button: calculate (`id="btn"`)
- div: result message (`id="res"`)

### JavaScript Naming
- DOM elements:  
  `cityInput`, `totalInput`, `expressInput`, `button`, `result`
- Event handler:  
  `handleDeliveryCheck`
- Working variables:  
  `cityValue`, `totalValue`, `isExpress`, `message`

### Rules (chained logic)
1. If city OR total is empty → `Enter city and order total.`
2. If total is not a number → `Order total must be a number.`
3. If total <= 0 → `Order total must be greater than 0.`
4. If express is checked AND total < 30 → `Express requires total of 30 or more.`
5. If city is `London` AND total >= 25 → `Free delivery.`
6. If city is `London` AND total < 25 → `Delivery fee: 3.99.`
7. If city is not `London` AND total >= 40 → `Free delivery.`
8. Otherwise → `Delivery fee: 5.99.`

### Test Data
- city: empty, total: empty
- city: `London`, total: `abc`
- city: `London`, total: `20`
- city: `London`, total: `25`
- city: `Manchester`, total: `39`
- city: `Manchester`, total: `40`
- express checked + total: `29`

### Future Upgrades
- add promo code logic
- show delivery type (Standard / Express)
- extract logic into calculation functions

---

## Task 3: Discount Code Validation

### Description
A realistic discount system using promo codes, order total, and membership.  
This task focuses on **complex conditional chains and logical grouping**.

### UI Elements
- text input: promo code (`id="code"`)
- text input: order total (`id="total"`)
- checkbox: membership (`id="member"`)
- button: apply (`id="btn"`)
- div: result message (`id="res"`)

### JavaScript Naming
- DOM elements:  
  `codeInput`, `totalInput`, `memberInput`, `button`, `result`
- Event handler:  
  `handleDiscountCheck`
- Working variables:  
  `codeValue`, `totalValue`, `isMember`, `message`

### Rules
1. If code OR total is empty → `Enter code and total.`
2. If total is not a number → `Total must be a number.`
3. If total <= 0 → `Total must be greater than 0.`
4. If code is not `SAVE10` AND not `VIP` → `Invalid code.`
5. If code is `SAVE10` AND total < 30 → `SAVE10 requires total of 30 or more.`
6. If code is `VIP` AND (total < 50 AND member is false) →  
   `VIP requires membership or total of 50 or more.`
7. Otherwise → `Discount applied.`

### Test Data
- code: empty, total: `10`
- code: `SAVE10`, total: `29`
- code: `SAVE10`, total: `30`
- code: `VIP`, total: `40`, member unchecked
- code: `VIP`, total: `40`, member checked
- code: `VIP`, total: `50`, member unchecked

### Future Upgrades
- calculate and display discount percentage
- add maximum discount limit
- track last applied codes
- refactor logic into reusable functions

---

## Learning Goal
These tasks are designed to:
- build confidence with DOM + conditional logic
- avoid premature abstraction
- allow smooth transition to function-based architecture later
