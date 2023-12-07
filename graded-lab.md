# Global objective

This exercise shall be finished and sent for grading at the end of December 14th, 2023 session. It will be graded on 100 points, then scaled down to 20.

The objective of this exercise is to build a set of consistent coordinates over all blinky blocks. One blinky block (ID=1) will initiate the coordinates, then start transmitting coordinates to their neighbors. Blinky blocks orientation is visible on top of the robot: a small hollow is moulded, that defines the left side of a Blinky block. Constants are defined in the API, defining the indices of UART interfaces, in relation to their orientation:
- MY_TOP is the top connector
- MY_BOTTOM is the bottom connector
- MY_LEFT is the one on the side of the hollow
- MY_RIGHT is the one opposite to MY_LEFT
- When facing the blinky block, MY_LEFT connector oriented to your own left, MY_FRONT is the connector whose side is facing you, while
- MY_BACK is the opposite connector, mask by the blinky block.

Coordinates are stored in three `int16_t` values.

The algorithm can be thought with several iterations:

- ideal layout, in which all blinky blocks face the same side (all hollows are in the same global direction)
- random (orientations are not homogeneous) layout with only one z-axis level (only connections between FRONT, BACK, RIGHT and LEFT; no TOP/BOTTOM connections)
- random layout on same z-level, but same orientation between TOP/BOTTOM connections
- complete random orientations

These iterations and their grade coefficient are defined below.

# Ideal layout (35 points)

To test this exercise, Blinky Block **shall be connected all with the hollow in the same direction**.

This part is simple: the leader starts with coordinates (0,0,0), then sends their coordinates to its neighbors:
- MY_RIGHT is the +X direction
- MY_LEFT is the -X direction
- MY_FRONT is the -Y direction
- MY_BACK is the +Y direction
- MY_TOP is the +Z direction
- MY_BOTTOM is the -Z direction

These initial directions will also apply for the subsequent parts.

Upon receiving a set of (x,y,z) coordinate, a blinky block will set its own x,y,z coordinate, then propagate updated coordinates to its neighbors. All BB shall end up with a consistent set of coordinates.

See last section for code enabling you to test your algorithm (available soon)

# Random, same z-level (35 points)

In this part, BB may be connected on one level, with any direction. The leader's direction will be the global direction. Each BB has to also maintain a value for its angle related to the leader's. Angles can be reconstructed by transmitting output connector and local angle along with updated coordinates. Then, by using the input connector on the receiving side, the angle compared to the sender can be computed, then added to the sender's local angle to get the global angle.

# Random, except for z-axis connections (10)

In this part, any BB connected on top of, or bellow another one, **shall be connected in the same direction**

Then, the rest of the algorithm is similar to the previous part's one.

# Total random (20)

In the last part, BBs can be plugged anyhow, even on TOP/BOTTOM connections. When going up/down, a set of coordinates and angles will be sent, that can be later reduced when receiving new coordinate updates from other paths.
