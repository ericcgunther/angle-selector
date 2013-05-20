angle-selector
==============

A Javascript/HTML5 user input control specifically for radian angle values

Note: angle-selector requires jQuery.

How it works
-

Include angle-selector.js as a script in your HTML. This script will allow you to use the <angle_selector> tag which has the following attributes:

- **id** (required, must be unique on the page)
- **width** (required)
- **height** (required)
- **angle1** - first angle (in radians)
- **angle2** - second angle (in radians)
- **radius** - radius of circle input
- **handle_radius** - radius of the angle selector handles
- **ccw** - direction of path between two angles
- **angle1_label** - label for the first angle selector
- **angle2_label** - label for the second angle selector

Adding an <angle_selector> element will create an HTML5 canvas element which the user can interact with to change the angle1, angle2 and ccw attributes. Clicking the circle will reverse the path from angle1 to angle2 (switches the value of ccw). Dragging the angle handles will adjust the angle attribute for each.

Example
------

    <!doctype html>

    <html>
    
    <script type="text/javascript">
        document.write("\<script src='http://code.jquery.com/jquery-latest.min.js' type='text/javascript'>\<\/script>");
    </script>
    
    <body>
    	<angle_selector id="two_angles_with_dir" width="200" height="200" angle1="0" angle2="3.14" radius="50" handle_radius="10" ccw="true" angle1_label="1" angle2_label="2"></angle_selector>
    	<angle_selector id="two_angles" width="200" height="200" angle1="0" angle2="3.14" radius="50" handle_radius="10" angle1_label="1" angle2_label="2"></angle_selector>
    	<angle_selector id="one_angle" width="200" height="200" angle1="0" radius="50" handle_radius="10" ></angle_selector>
    </body>
    
    <script src="angle-selector.js"></script>
    
    </html>

The example creates three angle selectors: one that allows the user to select two angles and a direction, one that allows the user to select two angles, and one that allows the user to select one angle. 

When the user interacts with the angle selector, the attributes of the angle selector will update in real time. Thus they can be used as inputs for some other process by using jQuery:

    var input_angle = $('#one_angle').attr('angle1')