# Arrhythmia-detection-using-heart-sound-wave-in-matlab
% Set the target heart rate (desired heart rate value).
targetHeartRate = 50; % You can adjust this to your desired value.
% Initialize a graphical figure for feedback.
h = figure;
set(h, 'Position', [100, 100, 800, 400]);
% Biofeedback loop
while ishandle(h)
% Simulate heart rate measurement (you would replace this with real data)
currentHeartRate = randi([30, 150]); % Simulated heart rate in bpm
% Display the current heart rate on the figure
subplot(1, 2, 1);
plot(currentHeartRate, 0, 'ro', 'MarkerSize', 10, 'MarkerFaceColor', 'r');
hold on;
axis([0, 160, -1, 1]);
title('Current Heart Rate');
% Check if the current heart rate is within a predefined range of the target
lowerThreshold = targetHeartRate - 5;
upperThreshold = targetHeartRate + 5;
% Provide biofeedback based on the heart rate
if currentHeartRate < lowerThreshold
feedbackMessage = 'Bradycardia detected.';
elseif currentHeartRate > upperThreshold
feedbackMessage = 'Tachycardia detected.';
end
subplot(1, 2, 2);
text(0.2, 0.5, feedbackMessage, 'FontSize', 10);
axis off;
drawnow; % Update the figure
pause(5); % Simulate real-time monitoring (adjust the interval as needed)
end

![image](https://github.com/Naveenaaraj/Arrhythmia-detection-using-heart-sound-wave-in-matlab/assets/128782565/4e5cb92d-7561-4db1-84e5-f8aa1c968cdd)
