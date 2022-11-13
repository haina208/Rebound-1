# Rebound-1
First assignment of Rebound

import rebound
import numpy
import matplotlib.pyplot as plt
from IPython.display import display, clear_output

sim = rebound.Simulation()
rebound.data.add_solar_system(sim)
print(sim.status())

sim.move_to_com()
for i in range(100):
    sim.integrate(sim.t+0.31)
    fig, ax = rebound.OrbitPlot(sim,color=True,unitlabel="[AU]",xlim=[-30,30.],ylim=[-30,30.])
    display(fig)
    plt.close(fig)
    clear_output(wait=True)
