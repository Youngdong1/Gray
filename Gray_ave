close all
clear;
clc;
%% load Gray data
Depth=xlsread('灰度2934.95-3122.15.xlsx','A2:A104565');
Gray=xlsread('灰度2934.95-3122.15.xlsx','C2:C104565');
%Diff=xlsread('全井段灰度数据系列.xlsx','D2:D18514');
%% load Gray data and find sample
%D=[3095.43;3095.9;3096.4];
Diff=abs(diff(Gray));
Diff=[0;Diff];
D=xlsread('条数.xlsx','A2:A49');
%%
w=1/100;%平均值步长1cm
l=length(D);%ind=zeros(l,1);
ave1=zeros(l,1);t=zeros(l,1);T=ones(l,1);ave2=zeros(l,1);
tu=ones(l,1);tl=ones(l,1);
for i=1:l
    tt=find(min(abs(D(i)-Depth))==abs(D(i)-Depth));
    t(i)=tt(1);
    %TT=min(abs(D(i)-Depth(t(i))));
    %T(i)=TT(1);
    wu=Depth(t(i))-w/2;
    wl=Depth(t(i))+w/2;
    tu(i)=find(min(abs(wu-Depth))==abs(wu-Depth));
    tl(i)=find(min(abs(wl-Depth))==abs(wl-Depth));
    ave1(i)=mean(Diff(tu(i):tl(i)));
    ave2(i)=mean(Gray(tu(i):tl(i)));
end
