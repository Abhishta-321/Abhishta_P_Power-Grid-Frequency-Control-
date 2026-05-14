 Power Grid Frequency Control 
 System modelled as: G(s)=1/4s+1
 
 Objectives: 
• Frequency deviation returns to zero quickly  
• Minimal oscillations  
• Stable response 

Tasks 
• Model system response  
• Design PI/PID controller  
• Analyze response to disturbance  
• Evaluate system stability 

Expected outcomes:
• Transfer function model  
• Controller parameters  
• Response plots  
• Performance evaluation 

Flow of the program : User i/p(when the delay of disturbance)-> user inputs disturbanc to the system(ex: step,impulse etc) -> user input gets converted from string to matlab function(str2func)->system defined acc to problem statement(ie 1/4s+1),0-15s after disturbance, intervals of 0.01 sec->using gradient descent algorithm we find most optimum values of Kp,Ki for the PI controller-> plot system response to disturbance with and without optimised PI controller and display system metrics (peak,settling time)


<img width="1088" height="787" alt="Screenshot 2026-05-14 124744" src="https://github.com/user-attachments/assets/edec1118-55ea-46b7-a53f-9a99cf2ae458" />
<img width="1088" height="837" alt="Screenshot 2026-05-14 104908" src="https://github.com/user-attachments/assets/73bf919c-3d51-4b52-a7b2-12d6d62ebc4d" />
