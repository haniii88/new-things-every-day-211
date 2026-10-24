```javascript
function dailyLog211() {
  const products = [
    { name: "Laptop", sold: 12, price: 900, cost: 650 },
    { name: "Keyboard", sold: 45, price: 50, cost: 25 },
    { name: "Mouse", sold: 60, price: 30, cost: 12 },
    { name: "Monitor", sold: 18, price: 250, cost: 170 },
    { name: "Headphones", sold: 32, price: 80, cost: 40 },
  ];

  const totalRevenue = products.reduce(
    (sum, product) => sum + product.sold * product.price,
    0
  );

  const totalProfit = products.reduce(
    (sum, product) =>
      sum + product.sold * (product.price - product.cost),
    0
  );

  const bestSeller = products.reduce((best, product) =>
    product.sold > best.sold ? product : best
  );

  console.log("=== Sales Performance Report ===");
  console.log(`Products: ${products.length}`);
  console.log(`Total Revenue: $${totalRevenue.toLocaleString()}`);
  console.log(`Total Profit: $${totalProfit.toLocaleString()}`);
  console.log(`Best Seller: ${bestSeller.name}`);
  console.log(`Units Sold: ${
    products.reduce((sum, product) => sum + product.sold, 0)
  }`);

  console.log("\n=== Product Breakdown ===");

  products.forEach(product => {
    const revenue = product.sold * product.price;
    const profit = product.sold * (product.price - product.cost);

    console.log(
      `${product.name}: Revenue $${revenue}, Profit $${profit}`
    );
  });
}

dailyLog211();
```
