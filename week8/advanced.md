### Advanced Plotting

Many Plots...

```python
# An extra set of sample plots for the thumbnail image.
import matplotlib.pyplot as plt
import numpy as np

# returns an array of 2 dimensions, with 100 entries
#ie [(.5,.1),(.2,.8),(.7,.3),...]
data = np.random.randn(2, 100)

#setup 2x2 array of plots
fig, axs = plt.subplots(2, 2)

#histogram
axs[0, 0].hist(data[0])

#scatter plot
axs[1, 0].scatter(data[0], data[1])

#line plot
axs[0, 1].plot(data[0], data[1])

#2d histogram
axs[1, 1].hist2d(data[0], data[1])

plt.show()
```
