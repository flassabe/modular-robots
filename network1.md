# Blinky Blocks applications with communications

For both applications, you shall set software IDs on you Blinky Blocks, with the command `blinkyApploaderCLI -t -k 1 -s /dev/ttyUSB0 -q`

## Application 1: distance gradient

This application aims at computing the shortest distance towards a leader (arbitrarily set to ID=1). It will rely on a message flooding initiated by the leader, and propagated by BBs if the new value improves the actual one. Every 250 ms, a BB updates its color by using `setColor` and its current distance as color index.

## Application 2: leader election

In this application, you shall elect a leader whose software ID is the highest one. The leader shall light in blue, while the other BBs shall switch their LED off. You can use any leader election algorithm studied in the modular robots module.
