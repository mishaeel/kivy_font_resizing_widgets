This code takes a Kivy Label and resizes the font automatically
if the window is resized/maximized/restored or if the window is dragged
to another display. I have only tested on Windows and desktop, 
float and grid layouts. Feel free to let me know if you experience issues.

To use the code, you have to declare the inital font size in python. 
For whatever reason, declaring the initial size in the kv language has not 
worked for me. You also have to use 'sp' units in your font size.

To use, either:

1. Add the code in the FontResizingLabel class to your own Label, or

2. Save the code as a module in your app's root directory
and include as follows in your application's python code.
---------------------------------------------------------
	from FontResizingLabel import FontResizingLabel
	
	class YourLabel(FontResizingLabel):
	
		original_font_size = '22sp'
		
		# declare your initial font size in python
		# as a string with sp units
	
		def __init__(self, **kwargs):
			super(YourLabel, self).__init__(**kwargs)
