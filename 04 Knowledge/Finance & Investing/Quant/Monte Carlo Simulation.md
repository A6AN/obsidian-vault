---
tags: [finance, quant]
---

2025-09-14 01:44

Status: #Adult 

Tags: [[Brownian Motion]] [[Geometric Brownian Motion (GBM)]] [[Quant]] [[Calculus]] [[Python]] [[Ito's Lemma]] 

# Monte Carlo Simulation

`import numpy as np`
`import matplotlib.pyplot as plt`
`import time`

`def run_monte_carlo_simulation():`
    `"""`
    `Performs a Monte Carlo simulation for the Nifty 50 index`
    `using the Geometric Brownian Motion (GBM) model.`
    `"""`
    
    # --- 1. Define Simulation Parameters ---
    # These are our assumptions about the market.
    
    S0 = 23567.05      # Initial price of Nifty 50 (as of a recent date)
    mu = 0.11          # Expected annual return (drift) - a reasonable assumption for a large-cap index
    sigma = 0.18       # Annual volatility (standard deviation) - a typical value for Nifty 50
    
    T = 1.0 / 12.0     # Time horizon: 1 month (expressed in years)
    dt = 1.0 / 252.0   # Time step: 1 trading day (since there are ~252 trading days in a year)
    
    N = int(T / dt)    # Total number of time steps (trading days in the next month)
    I = 10000          # Number of simulations (paths) to generate
    
    print("--- Simulation Parameters ---")
    print(f"Initial Nifty 50 Price: {S0}")
    print(f"Time Horizon: {N} trading days ({T*12:.1f} month)")
    print(f"Expected Annual Return (μ): {mu*100:.2f}%")
    print(f"Annual Volatility (σ): {sigma*100:.2f}%")
    print(f"Number of Simulations: {I}")
    print("-----------------------------\n")

    # --- 2. Execute the Simulation ---
    # This is the core of the model, automating the manual calculation we did.
    
    start_time = time.time()
    
    # Create a 2D NumPy array to hold all price paths. Rows=time steps, Cols=simulations
    # We do this for efficiency instead of looping one by one.
    Z = np.random.standard_normal((N, I)) # Generates all random numbers at once
    
    # The GBM formula in its discrete, vectorized form
    price_paths = S0 * np.exp(np.cumsum((mu - 0.5 * sigma**2) * dt + sigma * np.sqrt(dt) * Z, axis=0))
    
    # Add the starting price to the top of the array for plotting
    price_paths = np.vstack([np.full(I, S0), price_paths])

    # The final prices are the last row of our simulated paths
    final_prices = price_paths[-1]
    
    end_time = time.time()
    print(f"Simulation completed in {end_time - start_time:.2f} seconds.\n")

    # --- 3. Analyze and Visualize the Results ---
    
    # Calculate key statistics from our 10,000 final prices
    mean_price = np.mean(final_prices)
    std_dev = np.std(final_prices)
    median_price = np.median(final_prices)
    
    # Calculate confidence intervals (e.g., the range where 90% of outcomes fall)
    percentile_5 = np.percentile(final_prices, 5)
    percentile_95 = np.percentile(final_prices, 95)
    
    print("--- Simulation Results ---")
    print(f"Average Predicted Nifty 50 Price: {mean_price:,.2f}")
    print(f"Median Predicted Price: {median_price:,.2f}")
    print(f"Standard Deviation of Predictions: {std_dev:,.2f}")
    print(f"90% Confidence Interval: [{percentile_5:,.2f} - {percentile_95:,.2f}]")
    print("--------------------------\n")

    # Plot the results
    plt.style.use('seaborn-v0_8-darkgrid')
    fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(16, 7))
    
    # Plot 1: A sample of the simulated price paths
    ax1.plot(price_paths[:, :100]) # Plot the first 100 paths
    ax1.set_title(f'Sample of {I} Simulated Nifty 50 Paths')
    ax1.set_xlabel(f'Trading Days from Today')
    ax1.set_ylabel('Nifty 50 Price')
    
    # Plot 2: Histogram of the final prices
    ax2.hist(final_prices, bins=75, edgecolor='black', alpha=0.7)
    ax2.set_title('Distribution of Nifty 50 Price in 1 Month')
    ax2.set_xlabel('Final Nifty 50 Price')
    ax2.set_ylabel('Frequency (out of 10,000 simulations)')
    
    # Add vertical lines for the key statistics
    ax2.axvline(mean_price, color='red', linestyle='--', linewidth=2, label=f'Mean: {mean_price:,.2f}')
    ax2.axvline(percentile_5, color='orange', linestyle=':', linewidth=2, label=f'5th Percentile: {percentile_5:,.2f}')
    ax2.axvline(percentile_95, color='orange', linestyle=':', linewidth=2, label=f'95th Percentile: {percentile_95:,.2f}')
    ax2.legend()
    
    plt.tight_layout()
    plt.show()

`if __name__ == '__main__':`
    `run_monte_carlo_simulation()`


# References

