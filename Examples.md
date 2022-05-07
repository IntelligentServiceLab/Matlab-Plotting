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


### 【Examples 2】
```matlab
% version: R2021b
% note: Numbers are added by inserting TEXT manually
subplot(2,2,1)
a=[55,24,40,61,20]
b=bar(a)
set(gca,'TickLabelInterpreter','latex');
set(gca,'xticklabels',{"$duration_1$","$duration_2$","$duration_3$","$duration_4$",'$delay$'},fontsize=10)
xlabel({'\fontname{Times New Roman}Durations','\fontname{Times New Roman}(a) Task-role performance evaluation of \itcommunity review'},fontsize=15)
ylabel("Number of task instances",fontsize=15,FontName='times new roman')
ylim([0,90])
grid on

subplot(2,2,2)
a=[61,25,31,60,23]
b=bar(a,'FaceColor','g')
set(gca,'TickLabelInterpreter','latex');
set(gca,'xticklabels',{"$duration_1$","$duration_2$","$duration_3$","$duration_4$",'$delay$'},fontsize=10)
xlabel({'\fontname{Times New Roman}Durations','\fontname{Times New Roman}(b) Task-role performance evaluation of task-role of \itstreet review'},fontsize=15)
ylabel("Number of task instances",fontsize=15,FontName='times new roman')
ylim([0,90])
grid on

subplot(2,2,3)
a=[79,27,20,64,10]
b=bar(a,'FaceColor','r')
set(gca,'TickLabelInterpreter','latex');
set(gca,'xticklabels',{"$duration_1$","$duration_2$","$duration_3$","$duration_4$",'$delay$'},fontsize=10)
xlabel({'\fontname{Times New Roman}Durations','\fontname{Times New Roman}(c) Task-role performance evaluation of \itfirst county review'},fontsize=15)
ylabel("Number of task instances",fontsize=15,FontName='times new roman')
ylim([0,90])
grid on

subplot(2,2,4)
a=[66,47,22,58,7]
b=bar(a,'FaceColor',[0.7 0 0.8])
set(gca,'TickLabelInterpreter','latex');
set(gca,'xticklabels',{"$duration_1$","$duration_2$","$duration_3$","$duration_4$",'$delay$'},fontsize=10)
xlabel({'\fontname{Times New Roman}Durations','\fontname{Times New Roman}(d) Task-role performance evaluation of \itsecondary county review'},fontsize=15)
ylabel("Number of task instances",fontsize=15,FontName='times new roman')
ylim([0,90])
grid on
```
![matrix of plots](examples/example2.jpg)


### 【Examples 1】
```matlab
% version: R2021b
subplot(1,3,1)
a=[0,0.5,1,1.5,2]
b=[2.2115861,2.15729257154,2.10998199,2.04998199,2.00998199]

bar(b)
set(gca,"xticklabel",{'0','0.5','1','1.5','2'})
ylim([2,2.25])
txt=xlabel('(a) DCG Value vs. $H_{0}$')
set(txt,'interpreter','latex');
xlabel("(a) DCG Value vs. $H_{0}$",FontName='times new roman',FontSize=20)
ylabel("DCG Value",FontName='Times',FontSize=20)
grid on

subplot(1,3,2)
a=[0,0.5,1,1.5,2]

b=[0.531518,0.54817539,0.567141,0.577141,0.5998745]
bar(b,'red')
ylim([0.5,0.6])
txt=xlabel('(b) Diversity Value vs. $H_{0}$')
set(txt,'interpreter','latex');
set(gca,"xticklabel",{'0','0.5','1','1.5','2'})
xlabel("(b) Diversity Value vs. $H_{0}$",FontName='times new roman',FontSize=20)
ylabel("Diversity Value",FontName='Times',FontSize=20)
grid on

subplot(1,3,3)
a=[0,0.5,1,1.5,2]
y=[0.14279999999999995, 0.139457389999999926, 0.118422999999999976, 0.128422999999999967, 0.131156499999999903]
bar(y,'black')
ylim([0.1,0.15])
txt=xlabel('(c) RMSDE Value vs. $H_{0}$')
set(txt,'interpreter','latex');
set(gca,"xticklabel",{'0','0.5','1','1.5','2'})
xlabel("(c) RMSDE Value vs. $H_{0}$",FontName='Times New Roman',FontSize=20)
ylabel("RMSDE Value",FontName='Times',FontSize=20)
grid on
```
![matrix of plots](examples/example3.jpg)
