# gcodeFont
Simple command-line tool for creating the gcode for drawing/engraving a text line.

[![video]()](https://www.youtube.com/watch?v=t--c6iU60Fs)


It is a java program (single class) that you can include it on your own project or you can use as a command-line tool.

*Usage: java Romans "text" [offsetX] [offsetY] [scale] [angle]*

It will print to the standard output the g-code for drawing/engraving the text between quotation marks. Please remember these marks are needed.

The output for the text "abc 123 ABC" is containted in the sample file (https://github.com/misan/gcodeFont/blob/master/abc123ABC.gcode)

And you can see the final result in 3D
![3dview](https://github.com/misan/gcodeFont/blob/master/3dview.png?raw=true)

Please note entering into the material at the begining of each symbol is done with a G1 command and leaving the material with a (probably faster) G0 command.

Font is based on the ROMANS.CHR font from [NCPlot program](http://ncplot.com/stickfont/stickfont.htm) but I have included support for Spanish symbols (Ñ, ñ, á, é, í, ó and ú).

Now with scale and rotation features, as shown in the next example:

$ for((i=0; i<8; i++)) ; do a=$(echo $i*0.785|bc); java Romans "abc 123 ABC" 0 0 0.5 $a; done
![rotate](https://github.com/misan/gcodeFont/blob/master/rotate.png?raw=true)
