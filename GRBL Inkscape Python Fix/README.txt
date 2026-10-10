MI GRBL Z-Axis Servo Controller - Python 3 subpath fix

Reason: traced SVGs can contain multiple subpaths. The previous script
compared a candidate distance tuple against None at parse_curve line 2462.
Python 3 rejects that comparison and the program stops after creating an
empty output file.

Changes vs the previous MI_GRBL_Inkscape_1x_fix.zip:
- Fix the tuple-vs-None comparison in parse_curve.
- Preserve previous Python 3 / macOS compatibility changes.

Install:
1. Quit Inkscape.
2. Back up your existing servo.py and servo.inx files.
3. Replace them with the two files alongside this README.
4. Reopen Inkscape, select the traced panda path, and run the extension.
5. Check that the new G-code file is nonempty and contains X/Y moves.

IMPORTANT: This revision passed Python syntax checks and a focused
18-subpath sorting test, but has NOT been run inside your Inkscape or
validated with your physical plotter. Preview and inspect the G-code
before connecting motor power. Your custom servo-up/down commands must
match your firmware. Do not drive the machine using unverified commands.
