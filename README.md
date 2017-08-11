# Matlab_GUI_example

This is an example of how to program a simple GUI for a graph window in Matlab.

## Usage

Run the *Main.m* file in Matlab.

## Commands

This example shows how to create clickable buttons in the main GUI and how to assign a method to this button.

The code for creating a button is 
```matlab
h = uicontrol('position',[10,5,80,30]);
set(h, 'String', 'Button text');
set(h, 'Callback','Main method');
```
and you implement it as

```matlab
if nargin<1, action='start'; end

switch(action)
	case 'start'    
		h = uicontrol('position',[10,5,80,30]);
		set(h, 'String', 'Button text');
		set(h, 'Callback','Main method');
	case 'method'
		fprintf('Button Pressed\n');
	otherwise
		error('Unknown action string!');
end
```
and if you want to add a new button, just do it in the *start* section as
```matlab
if nargin<1, action='start'; end

switch(action)
	case 'start'    
		h = uicontrol('position',[10,5,80,30]);
		set(h, 'String', 'Button text');
		set(h, 'Callback','Main method');
		
		h2 = uicontrol('position',[190,5,80,30]);
		set(h2, 'String', 'Rotate');
		set(h2, 'Callback','Main rotate');

	case 'method'
		fprintf('Button Pressed\n');
	case 'rotate'
		%your code here.
	otherwise
		error('Unknown action string!');
end
```
