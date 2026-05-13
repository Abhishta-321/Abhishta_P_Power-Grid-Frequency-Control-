clc;
clear;
close all;

%% 1. Define System
s = tf('s');
G = 1/(4*s + 1);   % Given transfer function

%% 2. Time Vector
t = 0:0.01:20;     % 0 to 20 seconds

%% 3. Disturbance (Step at t = 8s)
d = zeros(size(t));
d(t >= 8) = 1;     % Step disturbance

%% 4. Without Controller (Open Loop)
y_open = lsim(G, d, t);

%% 5. PI Controller Design
Kp = 2;
Ki = 1;
C = Kp + Ki/s;

%% 6. Closed Loop System
T = feedback(C*G, 1);

%% 7. With Controller (Closed Loop Response)
y_closed = lsim(T, d, t);

%% 8. Plot Results
figure;

subplot(2,1,1)
plot(t, y_open, 'r', 'LineWidth', 2)
title('Without Controller')
xlabel('Time (s)')
ylabel('Frequency Deviation')
grid on

subplot(2,1,2)
plot(t, y_closed, 'b', 'LineWidth', 2)
title('With PI Controller')
xlabel('Time (s)')
ylabel('Frequency Deviation')
grid on

%% 9. Combined Plot (Comparison)
figure;
plot(t, y_open, 'r--', 'LineWidth', 2); hold on;
plot(t, y_closed, 'b', 'LineWidth', 2);
legend('Without Controller', 'With PI Controller')
title('Comparison of System Response')
xlabel('Time (s)')
ylabel('Frequency Deviation')
grid on
