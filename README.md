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

## Common Pitfalls
+ Forgetting that subplot numbers the plots rowwise rather than columnwise
+ Not realizing that the subplot function just creates a matrix within the Figure Window. Each part of this matrix must then be filled with a plot, using any type of plot function
+ Closing a Figure Window prematurely—the properties can only be set if the Figure Window is still open!
