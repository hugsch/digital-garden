---
id: 2kulwe7c9axclfc27vbg59a
title: Working with masks in the VSE
desc: ''
updated: 1671296946168
created: 1671293283322
---
# Creating a circular mask with a border

Imagine that you need a red circle with a blue border on a green background. Or an enlarged circular cut-out of a family photo.

![](/assets/images/vse.mask.svg)
Figure 1: Creating a blue bordered mask.

- Create the mask in the image editor. Call it for example msk-circle. The Image Editor is opened in the top-left window of figure 1. Don't forget to switch to the Mask Editing Context (see top-left). By default, it is set to View.
- Switch to the Sequencer of the VSE (lower panel). You need three strips:
   - the background strip; e.g. the family photo or the green color strip in figure 1.
   - the masked strip; e.g. the image of the face or the red color strip.
   - the border strip; e.g. probably always a color strip. We choose a blue color for the border. Note that the border strip is beneath the masked strip but above the background.
- Apply the mask (msk-circle) to both the border and masked strip. For now, you will only see a completely red circle without a border. This is because the same mask is applied to both and the red strip is on top of the blue one. You need to scale up the blue strip a bit, BUT ...
- Scaling the blue strip will have no effect because you don't scale the mask with it. You need to convert the strip into a meta strip (right click and choose Group). Because you probably will scale or move both strips, it is good practice to also group the masked strip.
- Scale the blue border strip a little so that it appears from under the masked strip. Depending on the width of the border you have to scale more or less.
- Eventually, select both group strips and scale, rotate or move them to the appropriate values. 


# Creating a growing arrow with masks

- Render the frame where the arrow will finish
- Draw the arrow as a mask in the image editor. Place the render result of the previous step as background image. Ctrl+Shft click to add points. Make sure to Toggle Cyclic to close the shape.
- Swith to the VSE. Insert a color strip with the desired length. Apply the mask. The arrow will appear. Eventually convert the strip to a Group (Ctrl+G) and scale, rotate and move the arrow to the desired spot. 
- Place the current frame at the frame where the arrow should be fully visible.
- Insert a keyframe for the X/Y location and/or the crop left/right or top/bottom. This depends on the direction of the growing arrow (from left to right or top to bottom).
- Place the current frame at the frame where the growing of the arrow should begin.
- Change the crop value until the arrow is completely disappeared. Move the box of the arrow to the starting postion .
- Put a keyframe on the crop value and x/y location.

- eventually, leave the arrow at the end position. Crop it to zero. Reduce  the x/Y position with the crop value
