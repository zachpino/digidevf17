### Simple Plots

Single Plot

```python
import matplotlib.pyplot as plt

x = [1,3,5,7]
y = [2.5,3,16,1.2]

plt.xlabel('time in seconds')
plt.ylabel('sensor value')

#plt.scatter(x,y)
#plt.bar(x,y)
plt.plot(x,y)

#plt.savefig('plot.png')
plt.show()
```

Multiple Plots

```python
import matplotlib.pyplot as plt

x = [0,1,2,3,4]

y1 = [1.5,2,1,3.5,2]
y2 = [.5,.25,2,4,5]

#subplot(rows,columns,which plot are we building now?)
plt.subplot(2, 1, 1)

plt.plot(x, y1)
plt.ylabel('Sensor 1')

#now we're building the second plot, this one filled!
plt.subplot(2, 1, 2)
plt.plot(x, y2)
plt.fill(x, y2
plt.ylabel('Sensor 2')
plt.xlabel('Time in Seconds')

plt.show()
```


