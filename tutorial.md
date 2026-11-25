# Build an Interactive Calculator

### Step 1: Open the Calculator
Let's draw the calculator on the screen when the game starts.
Drag ``||calculator:show calculator||`` into ``||loops:on start||``.

```blocks
calculator.showCalculator()
```

### Step 2: Add a Movable Cursor
Now let's create a pointer sprite so the player can move around the buttons with the arrow keys.
Snap ``||calculator:enable calculator cursor at speed 100||`` inside ``||loops:on start||``.

```blocks
calculator.showCalculator()
calculator.enableCursor(100)
```

### Step 3: Click Buttons with A
To let the player press the button under the cursor, grab ``||controller:on A button pressed||`` and put ``||calculator:click button under cursor||`` inside it.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    calculator.clickUnderCursor()
})
```

### Step 4: Add Sound Effects
Let's make the calculator beep whenever any button is pressed!
Drag ``||calculator:on calculator button pressed||`` onto the workspace and place ``||music:play tone Middle C for 1/2 beat||`` inside it.

```blocks
calculator.onButtonPressed(function (button) {
    music.play(music.tonePlayable(262, music.beat(BeatFraction.Half)), music.PlaybackMode.UntilDone)
})
```

### Step 5: Test Your Calculator! @unplugged
Use the **Arrow Keys** (or WASD) in the simulator to move the cursor over numbers and operators, and press **Spacebar / Z** to calculate equations!
