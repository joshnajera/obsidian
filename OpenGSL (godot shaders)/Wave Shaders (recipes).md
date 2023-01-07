#recipe 
# Wave Shaders
Encorporate trigonometry functions

``` SIN wave along y axis
shader_type canvas_item;

void fragment(){
	vec2 newUV = UV; // Get a copy to manipulate
	newUV.x += sin(TIME * 0.2 + newUV.y * 8.0) * 0.2; // Note: we use newUV.y as an offset so the 
	COLOR = texture(TEXTURE, newUV);
}
```

