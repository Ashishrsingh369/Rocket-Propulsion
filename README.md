# Rocket-Propulsion
Different use cases for python,C++for propulsion,docking
import numpy as np
from scipy.optimize import minimize

def trajectory_cost(params):
    # Simulate fuel cost based on angle and thrust
    angle, thrust = params
    fuel = 1000 * np.sin(angle) + 0.5 * thrust**2
    return fuel

result = minimize(trajectory_cost, [0.5, 1000], method='SLSQP')
print(f"Optimal angle: {result.x[0]}, thrust: {result.x[1]}")
