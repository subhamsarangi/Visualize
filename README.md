# Visualize
___
- ### Matplotlib
     Matplotlib is a Python 2D plotting library. [Official Website](https://matplotlib.org/), [Gallery](https://matplotlib.org/gallery.html)
     
     ___IPython Notebooks___
     - [Basics of the Matplotlib Framework](https://github.com/subhamsarangi/Visualize/blob/master/plt/1.%20matplotlib_basics.ipynb), 
     - [Advanced Matlpotlib](https://github.com/subhamsarangi/Visualize/blob/master/plt/2.%20matplotlib_advanced.ipynb) ([nbviewer](http://nbviewer.jupyter.org/github/subhamsarangi/Visualize/blob/master/plt/2.%20matplotlib_advanced.ipynb))

- Seaborn is a library for making attractive and informative statistical graphics in Python [Official Website](https://seaborn.pydata.org/), [Gallery](http://seaborn.pydata.org/examples/)
     
     ___IPython Notebooks___
    - [Basics of the Seaborn Framework](https://github.com/subhamsarangi/Visualize/blob/master/plt/3.%20seaborn_basics.ipynb)
    - [Categorical Plots with Seaborn](https://github.com/subhamsarangi/Visualize/blob/master/plt/4.%20seaborn_categorical_plots.ipynb)
    - [Creating Matrix Plots](https://github.com/subhamsarangi/Visualize/blob/master/plt/5.%20seaborn_matrix_plots.ipynb)
    - [Regression Plots with Seaborn](https://github.com/subhamsarangi/Visualize/blob/master/plt/6_seaborn_regression.ipynb)

# Here are some plots:
### 2D Plots (Scatter-plot, Step-plot, Bar-plot, Fill Between-Plot)
```python
fig, axes = plt.subplots( 1, 4, figsize=(12,3))
axes[0].scatter( x, x + 0.25*np.random.randn( len(x)))
axes[0].set_title("scatter")

axes[1].step( n, n**2, lw=2 )
axes[1].set_title("step")

axes[2].bar( n, n**2, align="center", width=0.5, alpha=0.5)
axes[2].set_title("bar")

axes[3].fill_between( x, x**2, x**3, color="green", alpha=0.5 )
axes[3].set_title("fill_between")
```
![2D Plots](https://raw.githubusercontent.com/subhamsarangi/Visualize/master/plt/images/08%20other2D.png)



### A 3D Plot (Contour plots with projection) 
```python
fig = plt.figure( figsize=( 12,10 ) )
ax = fig.add_subplot( 1,1,1, projection='3d' )
ax.plot_surface( X, Y, Z, rstride=4, cstride=4, alpha=0.25,cmap='plasma' )
cset = ax.contour( X, Y, Z, zdir='z', offset=-np.pi, cmap='gist_earth' )
cset = ax.contour( X, Y, Z, zdir='x', offset=-np.pi, cmap='gist_earth' )
cset = ax.contour( X, Y, Z, zdir='y', offset=3*np.pi, cmap='gist_earth' )
ax.set_xlim3d( -np.pi, 2*np.pi)
ax.set_ylim3d( 0, 3*np.pi )
ax.set_zlim3d( -np.pi, 2*np.pi )
```
![3D plot](https://raw.githubusercontent.com/subhamsarangi/Visualize/master/plt/images/16%20contour_proj.png)



### Heatmap
```python
flights = sns.load_dataset( 'flights' )
fpt=flights.pivot_table( index='month',columns='year',values='passengers' )
sns.heatmap( fpt, cmap='coolwarm' )
```
![Heatmaps](https://raw.githubusercontent.com/subhamsarangi/Visualize/master/plt/images/sns_13heatmap.png)



### Linear Model Plot
```python
tips = sns.load_dataset('tips')
sns.lmplot(x='total_bill',y='tip',data=tips,hue='sex',markers=['o','v'],scatter_kws={'s':100})
```
![LM Plot](https://raw.githubusercontent.com/subhamsarangi/Visualize/master/plt/images/sns_16lmplot_2.png)



### Joint Plot
```python
tips = sns.load_dataset('tips')
sns.jointplot(x='total_bill',y='tip',data=tips,kind='hex')
```
![Joint Plot](https://raw.githubusercontent.com/subhamsarangi/Visualize/master/plt/images/sns_2joints_hex.png)
