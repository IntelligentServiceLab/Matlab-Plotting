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

## Common Pitfalls
+ Forgetting that subplot numbers the plots rowwise rather than columnwise
+ Not realizing that the subplot function just creates a matrix within the Figure Window. Each part of this matrix must then be filled with a plot, using any type of plot function
+ Closing a Figure Window prematurely—the properties can only be set if the Figure Window is still open!
