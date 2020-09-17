clc;
clear all;
close all;
variance = 1;
mean = 0;
p_0 = input('Enter P(0) = ');
p_1 = input('Enter P(1) = ');
eta = p_0/p_1; % since P(1) = P(0) 
t=0:1:9;
% input_signal with p(0) = p(1) 
input_signal = [-1 1 1 -1 1 -1 1 -1 1 -1];
subplot(4,1,1);
stem(t,input_signal);
title('Input siganl');
% noise signal
r = normrnd(mean,variance,1,10);
subplot(4,1,2);
stem(t,r);
title('AGWN siganl');
% transmitted signal
transmitting_signal = input_signal + r;
% detector code
thre = ones(1,10);
threshold_voltage = (log(eta)*variance/2).*thre;
received_signal = [];
for i=1:10
    if(abs(transmitting_signal(i)) > threshold_voltage(i))
        received_signal(i) = transmitting_signal(i);
    else
        received_signal(i) = 0;
    end
end
subplot(4,1,3);
stem(t,received_signal);
title('Received signal');
%transmitted signal
transmitting_signal=input_signal+r;
estimated=[];
for i=1:10
    if(transmitting_signal(i)>0)
        estimated(i)=1;
    else
         estimated(i)=-1;
    end
end
subplot(4,1,4);
stem(t,estimated);
title('estimated siganl');
