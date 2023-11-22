# First Blinky Blocks applications

## Application 1 : setting color based on ID

For this exercise, you will first need to set software IDs to your blinky blocks (command option `-k`). Then, you shall write a program that sets the color of the Blinky Blocks according to its ID. You may use setColor with the ID as a parameter.

This function requires using two functions: `setColor` and `get_id()`.

## Application 2 : music

For this application, you need to implement the following music on your Blinky Blocks:

```c
uint16_t notes[] = {
		MI*2, SI, DO*2, RE*2, DO*2, SI,
		LA, LA, DO*2, MI*2, RE*2, DO*2,
		SI, DO*2, RE*2, MI*2,
		DO*2, LA, LA,
		SILENCE, RE*2, FA*2, LA*2, SOL*2, FA*2,
		MI*2, SILENCE, DO*2, MI*2, RE*2, DO*2,
		SI, DO*2, RE*2, MI*2,
		DO*2, LA, LA,
		LAST_NOTE
};
```

Durations are the following:

```c
uint16_t durations[] = {
		NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH, NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH,
		NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH, NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH,
		3*NOTE_BLACK/2, NOTE_EIGHTH, NOTE_BLACK, NOTE_BLACK,
		NOTE_BLACK, NOTE_BLACK, NOTE_WHITE,
		NOTE_EIGHTH, NOTE_BLACK, NOTE_EIGHTH, NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH,
		NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH, NOTE_BLACK, NOTE_EIGHTH, NOTE_EIGHTH,
		3*NOTE_BLACK/2, NOTE_EIGHTH, NOTE_BLACK, NOTE_BLACK,
		NOTE_BLACK, NOTE_BLACK, NOTE_WHITE
};
```

Music shall be played once, then stop.
