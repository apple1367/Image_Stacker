# Image_Stacker
tools for making imgs with stacked elements

Grammers
each elements get its own height.
it can set manualy but usually it considers automaticly.

command writen like this:

    import image_stacker
    
    imageset.autofigure()
    out = imageset()
    
    out.append(imageset_1)
    out = oneof(imgset_2, out)
    out = oneof(color_table, out)
    out = combination(imgset_3, out)
    out = pair(imgset_4, out)
    out = distribute(imgset_5, out)
    
    imageset.save()

all elements except colortables are considered as imageset (single image will considered as 1-image imageset.)

each methods(oneof, distribute, combination) decide how these images will combine.

methods will have two arguements.

    method(top, bottom)

image from top imageset will stacked on to image from bottom image.

if you stack with colortable, it just multiplies.



'one of' makes a random choice with duplication allowed.

for every imageset from bottom, choose one random image from top imageset and stack.


'pair' makes random choice trying to reduce duplication.

so for every image from bottom imageset,
choose one random, but not duplicated image from top imageset
and stack that on bottom image


'distribute' makes pair, but if top imageset is smaller, some of bottom imageset couldnt get stacked.


'combination' makes combination with every image.

so for every image from bottom imageset,
stack top imageset for every single combination.
if you combinate top imageset containing 4 img and bottom imgset containg 5 imgs,
result will be imageset with 20 imgs. (4 * 5 = 20)




