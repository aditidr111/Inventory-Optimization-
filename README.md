
# Inventory-Optimization using Linear Programming

This repository contains Inventory Optimization project for a Fashion and Beauty startup. The dataset is based on the supply chain of Makeup products and is taken from Kaggle. The key features in the dataset includes:  
Product Type, SKU, Price, Availability, Number of products sold, Revenue generated, Customer demographics, Stock levels, Lead times, Order quantities, Shipping times, Shipping carriers, Shipping costs, Supplier name, Location, Lead time, Production volumes, Manufacturing lead time, Manufacturing costs, Inspection results, Defect rates, Transportation modes, Routes, Costs.

## Goal
To optimize inventory levels across different locations (e.g., warehouses) such that:  
    1. Holding costs are minimized  
    2. Stockouts are avoided  
    3. Inventory turnover improves  
    4. Production and transportation constraints are taken into     consideration
   
## Libraries Used
1. PANDAS
2. PULP
3. MATPLOTLIB
4. SEABORN

## Project Flow
1.Problem Formulation:  
To determine the optimal number of units to maintain in stock for each SKU at each warehouse (location) given:  
Forecasted demand (based on Order quantities)
1.Current inventory (Stock levels)  
2.Holding cost (you can assume it as % of Manufacturing cost, say 10%)  
3.Replenishment cost (Manufacturing cost + Transportation cost)  
4.Lead time constraints

2.Decision Variable:  
Let x[i]= Number of units to order/keep in stock for SKU i

3.Objective Funcution:  
We minimize the total cost suct that  
Minimize:  
i∑[Holding Costi ⋅ x[i]+Ordering Costi ⋅ (x[i]−Current Inventoryi)+]  
where:  
Holding cost = 10% of Manufacturing cost  
Ordering cost = Manufacturing cost + Transportation cost  
(x[i] - current_inventory[i])^+ ensures only positive orders are considered

4.Constraints:  
a. Demand Constraints:  
x[i]≥ Order quantities 
 (to avoid stockouts)

b. Production Constraints:  
∑x[i]≤ Production volume at each location



