# Blender Font Mesh Generator

![](https://user-images.githubusercontent.com/28234322/168922128-3a8c0d13-b683-498b-a225-646f8f5a8d1d.png)

```py
import bpy

asciiStartingFrom33 = '!"#$%&\'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~'

for character in asciiStartingFrom33:
    bpy.ops.object.text_add(enter_editmode=False, align='WORLD', location=(0, 0, 0), scale=(1, 1, 1))
    txt = bpy.data.objects['Text']
    txt.data.body = character
    txt.data.font = bpy.data.fonts.load('C:\\Users\\Constantine\\Downloads\\DroidSansMono.ttf')
    bpy.context.view_layer.objects.active = txt
    bpy.ops.object.convert(target="MESH")
    txt.name = character
```
