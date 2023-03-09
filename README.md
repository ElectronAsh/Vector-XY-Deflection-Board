# Vector-XY-Deflection-Board
XY Deflection Driver board for Vector arcade games

This is in Eagle format. I'm using Autodesk Eagle 9.0.1 atm.

Please note, this design is UNTESTED.
Please do NOT use the included Gerbers zip file yet. That was just for previewing the design.

There is also no output connector from the Spot Killer circuit added yet.


Originally based on this desgin...
http://www.e-basteln.de/arcade/asteroids/monitor/#improved-xy-deflection


I re-did the whole PCB layout, based on a 2-layer design.
(the original design was meant for single-layer, with a few wire links on the top side.)

I added a bridge rectifier to the board, and larger caps, so a centre-tapped transformer can be used directly.

The old fuses were removed, because fuse holders could (should?) be added externally to the transformer primary and secondaries.
(also might be easier to access external fuse holders instead of being directly on the board.)

(the deflection board uses sense resistors for the yoke current, and uses that as feedback to the opamp.
 It should be possible to add some current-limiting to the design later.
 I think a couple of external fuses on the transformer secondaries will offer half-decent protection in mean time.)

Plus I added the Gain pots, linearity pots, Spot Killer circuit, and larger main transistors + driver transistors, all based on this video series...
https://youtu.be/xNVZ1HK8R1w?t=1326


The larger transistors and driver transistors are now meant to be bolted to a heatsink, with the whole PCB mounted just above that.
Hence the holes in the PCB to allow access to the mounting screws for the transistors.

(The transistors can't easily be mounted to a heatsink at 90-degrees to the board any more, as the transistors would need to be flipped around.)

I think mounting them on a heatsink below the PCB will be a lot neater and more stable.
I guess a heatsink at 90-degrees to the board could still be used, but the transistors would need to point downwards from the underside of the PCB.


The "Unblank" RCA jack output was removed, which was originally intended for driving the Blanking input on the Vectrex power board.
The Unblank signal was pretty much just a resistor from the X yoke anyway, which was probably fine for the Vectrex, but didn't take into account the Y signal.

The new Spot Killer circuit does take into account both the X and Y signal inputs.
Once the output connector for that circuit is added, it will be able to blank the external Cathode (or RGB) driver if the Spot Killer circuit sees 
no deflection on either the X or Y input for a specific amount of time.

(that time-constant can be set by resistor/cap values in the Spot Killer circuit. A pot could be added later, to make that variable.)

I will try to get some PCBs ordered for this soon, to test it.


The LT1227 opamps have a maximum supply rail voltage of +/- 18V.
A typical centre-tapped transformer with an output voltage of "12VRMS" (AC) will give a DC voltage of around 15-17V after the bridge rectifier.

So I would NOT recommending using a higher transformer voltage than that atm.
Maybe some shunt regulators could be added to the opamps?

