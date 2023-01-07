We will implement noise via  uniforms

```
uniform sampler2D varname; // Brings up editor with selectable noises
```


```Godot
shader_type canvas_item;
uniform sampler2D noise_sample;
uniform float dissolve_state : hint_range(0.0,1.0) = 0.0;
void fragment(){
	float noise = texture(noise_sample, UV).g;
	COLOR = texture(TEXTURE,UV);
	if(noise < dissolve_state){
		COLOR.a = 0.0
	}
}
```