LibCanvas
=========

LibCanvas is a free javascript library, based on MooTools and available under LGPL License. This library gives the developer a lot of tools for creating web applications & games by expanding canvas-2d context existing methods and providing new ones. There are tools for work with mouse events, such Behaviors as draggable and droppable, class for easy image preloading and so on.

![Logo](http://funkyimg.com/u2/608/884/libcanvas-logo.png)

How to use
----------

A little example of a moveable object, which could be linked and dropped to the other objects.
Also, this object receives mouse events and changes its color depending on current state - blue when clicked,
green when hovered and red in normal state.

	Interface.Shape = new Class({
	   Extends : LibCanvas.Behaviors.Drawable,
	   Implements : [
		  LibCanvas.Behaviors.MouseListener,
		  LibCanvas.Behaviors.Draggable,
		  LibCanvas.Behaviors.Clickable,
		  LibCanvas.Behaviors.Linkable,
		  LibCanvas.Behaviors.Moveable,
		  LibCanvas.Behaviors.Droppable
	   ],
	   getStyle : function () {
		  return (this.active && { fill : "#99f", stroke : "#006"})
			  || (this.hover  && { fill : "#9f9", stroke : "#060"})
			  ||                 { fill : "#f99", stroke : "#600"};
	   },
	   draw : function () {
		  var ctx = this.libcanvas.ctx.save();

		  this.lineWidth && ctx.set('lineWidth', this.lineWidth);

		  ctx.fill(this.shape, this.getStyle().fill)
		   .stroke(this.shape, this.getStyle().stroke)
		   .restore();
	   }
	});

Screenshots
-----------

!["Asteroids" game built with LibCanvas](http://funkyimg.com/u2/964/114/lc-screen-1.jpg)

![Solitaire built with LibCanvas](http://funkyimg.com/u2/964/114/lc-screen-2.jpg)

![Pseudo-vector editor built with LibCanvas](http://libcanvas.com/files/images/demos/path-builder.png)
