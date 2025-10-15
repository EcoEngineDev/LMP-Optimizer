# Linear Metal Part Optimizer

A web-based calculator that optimizes metal purchasing decisions to minimize costs and waste. This tool determines the most cost-effective combination of metal lengths to purchase while providing detailed cutting plans.

## Mathematical Foundation

The LMP-Optimizer uses a combination of mathematical approaches:

### Cost Minimization Function
```
Minimize: Σ(Ci × Qi)
Subject to: Σ(Li × Qi) ≥ Σ(Pj × Qj)
Where:
- Ci = Cost per unit of option i
- Qi = Quantity of option i to purchase
- Li = Length of option i
- Pj = Length of required part j
- Qj = Quantity of required part j
```

### Backtracking Algorithm
The algorithm explores all possible combinations using:
- **State Space**: Each state represents a partial solution with remaining material needs
- **Pruning**: Eliminates branches where current cost exceeds the best known solution
- **Optimization**: Minimizes total cost while ensuring all parts can be produced

### Cutting Optimization
For each purchased piece, the algorithm:
1. **Sorts parts** by length in descending order: `P1 ≥ P2 ≥ ... ≥ Pn`
2. **Fits parts** using a greedy approach: `remaining_length ≥ part_length`
3. **Calculates waste**: `waste = piece_length - Σ(used_parts)`
4. **Minimizes total waste** across all pieces

### Efficiency Metrics
- **Cost per foot**: `CPF = price / length`
- **Waste percentage**: `WP = (total_waste / total_purchased) × 100`
- **Material utilization**: `MU = (total_used / total_purchased) × 100`

#Use

### 1. Add Required Parts
- Enter the length of each part needed (in feet)
- Specify the quantity required
- Click "Add Part" to add to your list
- You can add unlimited parts

### 2. Define Purchasing Options
- Enter available metal lengths and their prices
- The calculator shows cost per foot for easy comparison
- Add multiple purchasing options from different suppliers

### 3. Calculate Optimal Purchase
- Click "Calculate Optimal Purchase" to run the LMP-Optimizer
- View the optimal combination of metal to buy
- See detailed cutting instructions for each piece

### 4. Review Results
- Purchase Plan: Shows exactly what to buy and total cost
- Cutting Plan: Visual guide for cutting each piece
- Material Summary: Total needed vs purchased vs excess
- Chart: Visual breakdown of material usage

## Algorithm Details

### LMP-Optimizer (Linear Metal Part Optimizer)
The calculator uses the LMP-Optimizer algorithm that:

1. Sorts Options: Orders purchasing options by cost per foot
2. Explores Combinations: Tests different combinations of metal lengths
3. Minimizes Cost: Finds the combination with the lowest total cost
4. Allows Excess: Permits some excess material to find better deals

### Cutting Optimization
The cutting plan algorithm:

1. Sorts Parts: Orders parts by length (largest first) for efficiency
2. Fits Parts: Tries to fit as many parts as possible into each piece
3. Minimizes Waste: Reduces scrap material through smart placement
4. Visual Guide: Shows exactly how to cut each piece


## Example Use Case

### Scenario: Manufacturing Project
- Parts Needed: 
  - 10 pieces of 8 ft metal
  - 15 pieces of 6 ft metal
  - 20 pieces of 4 ft metal
- Purchasing Options:
  - 20 ft pieces at $50 each
  - 12 ft pieces at $35 each
  - 8 ft pieces at $25 each

### Result: 
The LMP-Optimizer will determine the optimal combination (e.g., 2×20ft + 3×12ft + 1×8ft) and show exactly how to cut each piece to minimize waste and cost.

## Features in Detail

### Cost Optimization
- Compares cost per foot across all options
- Finds the best combination even if it means buying more than needed
- Considers bulk discounts and supplier variations

### Waste Minimization
- Shows exact waste from each cut
- Calculates waste percentage
- Suggests uses for excess material

### Visual Cutting Guide
- Color-coded segments show different cuts
- Blue segments: Parts to be cut
- Red segments: Waste material
- Proportional sizing based on actual lengths

### Real-time Updates
- Add/remove parts and options dynamically
- Instant recalculation when inputs change
- Live preview of cost implications

## Customization

### Styling
The application uses CSS custom properties that can be easily modified:
- Color scheme can be changed by updating CSS variables
- Layout can be adjusted for different screen sizes
- Typography can be customized for brand consistency

### Functionality
- Algorithm parameters can be adjusted for different optimization strategies
- Chart types can be changed for different data visualization needs
- Additional input validation can be added as needed

## Contributing

This is a standalone application designed for metal purchasing optimization. The code is well-documented and modular, making it easy to extend with additional features.

## License

This project is open source and available for educational and commercial use.

---

**LBO Metal Purchasing Calculator** - Optimize your metal purchasing decisions with precision and efficiency using the LMP-Optimizer algorithm.
