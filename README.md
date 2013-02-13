Leap-Finger-Tracking
====================

A javascript program to track individual fingers using the LEAP sensor.

The program activates when all ten fingers are visible, and uses buffers to track the position of individual fingers (left pinky, left thumb, etc.) as they are recognized by the LEAP.
The program calculates the following for each finger in each of the X, Y, and Z directions: 
position
velocity
offsets (relationship to other fingers on that hand) 
avg (average position from buffer window)
median (median position for buffer window) 
longavg (average position from larger buffer window)

If a finger is visible to the LEAP, it is tracked by the ID that's assigned to it by the device.

If a finger is not visible to the LEAP, its position is extrapolated based on its previous relationship to other fingers that have remained visible.

If a finger has disappeared and becomes visible again, the program guesses which finger (left ring, etc.) it is based on the extrapolated positions of all the fingers that have disappeared.

A green light means that the program is identifying visible fingers on that hand with a high degree of certainty: either all fingers are visisble or any fingers that have disappeared have not reappeared.

A yellow light means that the program has had to make at least one guess in assigning a finger identification.

A red light means that no fingers on that hand are visible to the LEAP.

