### Styling

Simple styling can be accomplished by appending [keyword arguments](http://matplotlib.org/2.1.0/api/_as_gen/matplotlib.lines.Line2D.html#matplotlib.lines.Line2D.set_color) to your plotting functions.

```python
import matplotlib.pyplot as plt

x = [1,3,5,7]
y = [2.5,3,16,1.2]

plt.xlabel('time in seconds')
plt.ylabel('sensor value')
plt.title('my sensor')

# Note that color is expressed in a list of three parameterized values for Red, Green, and Blue. 0 is none, 1 is all, .5 is half. 
plt.plot(x,y,linewidth='3',linestyle='dashed',color=[.5,.1,.75])

plt.show()
```

Different plot types have different keywords available. Visit the [documentation](http://www.matplotlib.org) to see the hundreds of settings that are editable! 
