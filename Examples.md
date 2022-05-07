## MATLAB Plot Examples

### 【Examples 1】
```matlab
% version: R2021b
colororder({'0 0 1','1 0 0'})
x=1:5;
rmse=[0.1217,0.1164,0.0988,0.0979,0.0974];
mae=[0.05,0.0484,0.0452,0.0449,0.0442];
yyaxis left;

xlabel("Number of transformation matrices",FontSize=20,FontName='times new roman')
bar(rmse,0.5);
ylim([0.08,0.13])
ylabel('RMSE',FontSize=15,FontName='times new roman');
yyaxis right;

plot(x,mae,LineWidth=3,marker="+",MarkerSize=8);
ylim([0.04 0.052]);
ylabel('MAE',FontSize=15,FontName='times new roman');
grid on;
legend('RMSE','MAE')
```
![matrix of plots](examples/example1.jpg)


