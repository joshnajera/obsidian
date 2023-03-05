# Inputs

## Default inputs
You can use a combination of all of these in a single shader.

### UV
The UV position of the current position.

### TEXTURE
The texture supplied in the material.

~~### SCREEN_TEXTURE
The texture of the whole screen
** Note: You should probably sample this with SCREEN_UV, not UV, as you will get a small flipped version of the screen~~
### New way to get SCREEN_TEXTURE  [Godot 4]
uniform sampler2D SCREEN_TEXTURE : hint_screen_texture , filter_linear_mipmap;

### SCREEN_UV
The UV position of the current pixel relative to the screen

### TIME
Time since GODOT started, constantly updates

### DELTA
Time in between frame
