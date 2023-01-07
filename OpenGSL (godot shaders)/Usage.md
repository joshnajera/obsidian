#2D
``` 2D_pixel_shader/fragment_shader
shader_type canvas_item;

uniform varType varName [ : hints ][ = default_value];

void fragment(){
	COLOR = texture(TEXTURE, UV);
}
```

Where shader_type is from [[Shader Types]]
