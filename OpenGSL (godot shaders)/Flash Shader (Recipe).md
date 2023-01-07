#recipe
# Flash Shader

``` Godot OpenGSL
shader_type canvas_item; // boilperplate

uniform vec4 flashColor : hint_color;
uniform float flashState : hint_range(0.0,1.0) = 0.0;

void fragment(){
COLOR = texture(TEXTURE,UV);
COLOR.rgb = mix(COLOR, flashColor, flashState);
}
```