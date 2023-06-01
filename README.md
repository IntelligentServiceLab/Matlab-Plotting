## MATLAB Functions and Commands
<table style="width:100%">
  <tr>
    <td>subplot</td>
    <td>plot3</td>
    <td>sphere</td>
    <td>barh</td>
    <td>bar3</td>
    <td>cylinder</td>
    <td>area</td>
    <td>bar3h</td>
    <td>colorbar</td>
  </tr>
  <tr>
    <td>stem</td>
    <td>pie3</td>
    <td>line</td>
    <td>hist</td>
    <td>comet3</td>
    <td>rectangle</td>
    <td>pie</td>
    <td>stem3</td>
    <td>text</td>
  </tr>
  <tr>
    <td>comet</td>
    <td>spiral</td>
    <td>get set</td>
    <td>movie</td>
    <td>mesh</td>
    <td>patch</td>
    <td>getframe</td>
    <td>surf</td>
    <td>image</td>
  </tr>
</table>

**[Matlab Plot Examples for Reference](Examples.md)**

[Stormy Attaway. **Matlab: A Practical Introduction to Programming and Problem Solving** [M]. Butterworth-Heinemann, 2013.](https://pan.baidu.com/s/1XqzsOz60NUSiN92BgYm9CQ?pwd=kang )

**Note**: Save \*.emf file for WORD template and save \*.eps file for LATEX template.

## Matlab Software Download
- [R2009a](https://pan.baidu.com/s/1LfePFjCCpGZw6r0Pw4HR3g)
- [R2016a](https://pan.baidu.com/s/1bbcMHcFj_uMkEgJ8hclT9g ) 
- [R2021b](https://pan.baidu.com/s/1cJ8jcHgEF9U_OKbxUaNGig?pwd=kang )

fetch code: kang

## Programming Style Guidelines
+ Always label plots
+ Take care to choose the type of plot to highlight the most relevant information

## Advanced Plotting TEchniques
### Plot Fucntions
```matlab
% version: R2016a
% Demonstrates subplot using a for loop
for i = 1:2
x = linspace(0,2*pi,10 *i);
y = sin(x);
subplot(1,2,i)
plot(x,y,'ko')
xlabel('x')
ylabel('sin(x)')
title(sprintf('%d Points',10 *i))
end
```
![matrix of plots](figures/figure1.jpg)

#### Method One
```matlab
% version: R2016a
% Subplot to show plot types
year = 2007:2011;
pop = [0.9 1.4 1.7 1.3 1.8];
subplot(2,2,1)
bar(year,pop)
title('bar')
xlabel('Year')
ylabel('Population')
subplot(2,2,2)
barh(year,pop)
title('barh')
xlabel('Year')
ylabel('Population')
subplot(2,2,3)
area(year,pop)
title('area')
xlabel('Year')
ylabel('Population')
subplot(2,2,4)
stem(year,pop)
title('stem')
xlabel('Year')
ylabel('Population')
```
#### Method Two
```matlab
% version: R2016a
% Demonstrates evaluating plot type names in order to use the plot functions and put the names in titles
year = 2007:2011;
pop = [0.9 1.4 1.7 1.3 1.8];
titles = {'bar', 'barh', 'area', 'stem'};
for i = 1:4
subplot(2,2,i)
eval([titles{i} '(year,pop)'])
title(titles{i})
xlabel('Year')
ylabel('Population')
end
```
![Subplot to display bar, barh, area, and stem plots](figures/figure2.jpg)

```matlab
% version: R2016a
% Data from a matrix in a bar chart
groupages = [8 19 43 25; 35 44 30 45];
bar(groupages);
xlabel('Group');
ylabel('Ages');
```
![Data from a matrix in a bar chart](figures/figure3.jpg)

```matlab
% version: R2016a
% Data from a matrix in a bar chart
groupages = [8 19 43 25; 35 44 30 45];
bar(groupages,'stack');
xlabel('Group');
ylabel('Ages');
```
![Data from a matrix in a bar chart](figures/figure4.jpg)

```matlab
% version: R2016a
% Histogram of data
quizzes = [10 8 5 10 10 6 9 7 8 10 1 8];
hist(quizzes);
xlabel('Grade');
ylabel('#');
title('Quiz Grades');
% >> c = hist(quizzes)
% c = 1 0 0 0 1 1 1 3 1 4
```
![Histogram of data](figures/figure5.jpg)

```matlab
% version: R2016a
% pie(vec): Pie chart showing percentages
pie([11 14 8 3 1]);
```
![Pie chart showing percentages](figures/figure6.jpg)

```matlab
% version: R2016a
% pie(vec): Pie chart with labels from a cell array
pie([11 14 8 3 1], {'A','B','C','D','F'});
```
![Pie chart with labels from a cell array](figures/figure7.jpg)

### Animation
```matlab
% version: R2016a
% animating a plot of sin(x) 
x = -2*pi : 1/100 : 2*pi;
y = sin(x);
comet(x,y);
% The end result looks similar to the result of plot(x,y)
```
![animating a plot of sin(x)](figures/figure8.jpg)


```matlab
% version: R2016a
% Shows a movie of the sin function
% The frames are captured in a loop using the built-in function getframe, and are stored in a matrix.
clear
x = -2*pi : 1/5: 2*pi;
y = sin(x);
n = length(x);
for i = 1:n
    plot(x(i),y(i),'r*')
    axis([min(x)-1 max(x)+1  min(y)-1 max(y)+1])
    M(i) = getframe;
end
movie(M)
```
![Shows a movie of the sin function](figures/figure9.jpg)

### Three-Dimensional Plots
```matlab
% version: R2016a
% 3D plot with a grid
x = 1:5;
y = [0 -2 4 11 3];
z = 2:2:10;
plot3(x,y,z,'k*');
grid;
xlabel('x');
ylabel('y');
zlabel('z');
title('3D Plot');
```
![3D plot with a grid](figures/figure10.jpg)

```matlab
% version: R2016a
% 3D bar chart
y = 1:6;
z = [33 11 5 9 22 30];
bar3(y,z);
xlabel('x');
ylabel('y');
zlabel('z');
title('3D Bar');
```
![3D bar chart](figures/figure11.jpg)


```matlab
% version: R2016a
% 3D plot of a spiral matrix
mat = spiral(5);
bar3(mat);
title('3D Spiral');
xlabel('x');
ylabel('y');
zlabel('z');
```
![3D plot of a spiral matrix](figures/figure12.jpg)

```matlab
% version: R2016a
% 3D pie chart
 pie3([3 10 5 2]);
```
![3D pie chart](figures/figure13.jpg)

```matlab
% version: R2016a
% an animated plot
t = 0:0.001:12*pi;
comet3(cos(t), sin(t), t);
```
![an animated plot](figures/figure14.jpg)

```matlab
% version: R2016a
% Mesh plot of sphere
[x,y,z] = sphere(15);
size(x); % ans = 16 16
mesh(x,y,z);
title('Mesh of sphere');
```
![Mesh plot of sphere](figures/figure15.jpg)


```matlab
% version: R2016a
% Surf plot of sphere
[x,y,z] = sphere(15);
surf(x,y,z);
title('Surf of sphere');
colorbar;
```
![Surf plot of sphere](figures/figure16.jpg)

```matlab
% version: R2016a
% Subplot to show varying bar widths
year = 2007:2011;
pop = [0.9 1.4 1.7 1.3 1.8];
for i = 1:4
	subplot(1,4,i)
	% width will be 0.6, 0.8, 1, 1.2
	barh(year,pop,0.4 + i*.2)
	title(sprintf('Width = %.1f',0.4 + i*.2))
	xlabel('Population')
	ylabel('Year')
end
```
![Subplot to show varying bar widths](figures/figure17.jpg)

```matlab
% version: R2016a
% Largest Fraction of Grades
gradenums = [11 14 8 3 1];
which = gradenums == max(gradenums);
% which = 0 1 0 0 0
pie(gradenums,which,{'A','B','C','D','F'});
title('Largest Fraction of Grades');
```
![Largest Fraction of Grades](figures/figure18.jpg)


```matlab
% version: R2016a
% plotywithcell.m
% Format: plotxywithcell(x,fn handle, cell array)
function plotxywithcell(x, fnhan, rca)
lenrca = length(rca);
y = fnhan(x);
for i = 1:lenrca
	subplot(1,lenrca,i)
	funh = str2func(rca {i});
	funh(x,y)
	title(upper(rca {i}))
	xlabel('x')
	ylabel(func2str(fnhan))
end
end
```

```matlab
% version: R2016a
% call plotywithcell.m
anfn = @ (x) x .^ 3;
x = 1:2:9;
rca = {'bar', 'area', 'plot'};
plotxywithcell(x, anfn, rca)
plotxywithcell(x, anfn, rca)
```
![Subplot showing different file types with their names as titles](figures/figure19.jpg)

## Common Pitfalls
+ Forgetting that subplot numbers the plots rowwise rather than columnwise
+ Not realizing that the subplot function just creates a matrix within the Figure Window. Each part of this matrix must then be filled with a plot, using any type of plot function
+ Closing a Figure Window prematurely—the properties can only be set if the Figure Window is still open!
