# Elevator-system-PLC-programming
elevator system controlled using the PLC, a 3-level elevator with 2 H-bridged DC motors for the vertical movement and horizontal movement of the door, making use of a counter to keep track of the floor

•	Rung 1: 
o	The master start starts the elevator by using a start latch to store the memory that the button has been pressed, while the master stop is off.
•	Rung 2:
o	When the elevator master start is on, the emergency light will turn off.
•	Rung 3-4:
o	Rung 3 has a ground button; when pressed, the button is set, and the target floor becomes 0 as the floor moves to the ground floor. The last target floor is updated to the current target.
o	Rung 4 has the ground limit switch (two parallel one activated when the elevator moves down(GroLS) and the other is activated when it moves up (GroLim))  when it is activated the ground button is reset and the light is also reset, while the current floor is updated to 0 indicating it is currently on the ground floor. It takes 4s for the light and button to switch off.
•	Rungss 5-6:
o	Rung 5 has a first-floor button; when pressed, the button is set, and the target floor becomes 1 as the floor moves to the first floor. The last target floor is updated to the current target floor.
o	Rung 6 has the first-floor limit switch (two parallel one activated when the elevator moves down(FirLS) and the other is activated when it moves up (FirLim)) the first-floor button is reset and the light is also reset, while the current floor is updated to 1 indicating it is currently on the first floor. It takes 4s for the light and button to switch off.
•	Rungs 7-8:
o	Rung 7 has a second-floor button; when pressed, the button is set, and the target floor becomes 2 as the floor moves to the second floor. The last target floor is updated to the current target floor.
o	Rung 8 has the second-floor limit switch (two parallel one activated when the elevator moves down(SecLS) and the other is activated when it moves up (SecLim)) the second-floor button is reset and the light is also reset, while the current floor is updated to 2 indicating it is currently on the second floor. It takes 4s for the light and button to switch off.
•	Rungs 9-10:
o	Rung 9 has a third-floor button; when pressed, the button is set, and the target floor becomes 3 as the floor moves to the third floor. The last target floor is updated to the current target floor.
o	Rung 10 has the third-floor limit switch (two parallel one activated when the elevator moves down(TrdLS) and the other is activated when it moves up (TrdLim)) the third-floor button is reset and the light is also reset, while the current floor is updated to 3 indicating it is currently on the third floor. It takes 4s for the light and button to switch off.
•	Rungs 11 and 12:
o	Rung 11 controls the downward motion of the elevator when the target floor is larger than the current floor the downward motor is activated.
o	Rung 12 controls the upward motion of the elevator when the target floor is smaller than the current floor the upward motor is activated.
•	Rung 13:
o	When the target floor is equal to the current floor the elevator doors are opened after 6s, when the up motor and down motor are both off.
o	It is in parallel with the emergency contact that when the emergency button is pressed the door will open
•	Rung 14:
o	Has the counter up-down counter, when the limit switches ( those ending with Lim) for the upward motion are on and their timers the counter is initiated until it reaches the preset value of 3 counting up from 0.
o	When the limit switches ( those ending with LS) for the downward motion are on and their timers the counter is initiated until it reaches the preset value of 0 counting down from 3.

•	Rung 15:
o	When the door is open, the vertical motors are open and one of the switches on, L is set.
•	Rung 16:
o	When the floor buttons are pressed the counter is reset, both the up count (UpReset) and down (DownReset) counter outputs. L is reset.
•	Rung 17 – 20:
o	When the current value of the counter is 0 and the elevator is moving up, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-up output on the switch stays on if the target floor is 0 (ground floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 1 and the elevator is moving up, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-up output on the switch stays on if the target floor is 1 (first floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 3 and the elevator is moving up, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-up output on the switch stays on if the target floor is 2 (second floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 3 and the elevator is moving up, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-up output on the switch stays on if the target floor is 3 (third floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
•	Rung 21 – 24:
o	When the current value of the counter is 3 and the elevator is moving down, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-down output on the switch stays on if the target floor is 3 (third floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 2 and the elevator is moving down, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-down output on the switch stays on if the target floor is 2 (second floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 1 and the elevator is moving down, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-down output on the switch stays on if the target floor is 1 (first floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
o	When the current value of the counter is 0 and the elevator is moving down, the limit switch is activated after 4 seconds. This is parallel to the open contact and the counter-down output on the switch stays on if the target floor is 0 (ground floor). Taking approximately 8 s to get to the next floor including the timer on the limit switch rung.
•	Rung 25-26:
o	When the emergency button is pressed, the emergency button is set and the light is also set, then the door is open and after the emergency light is turned on. The light is turned off when the elevator starts again. The elevator is also stopped simultaneously.

