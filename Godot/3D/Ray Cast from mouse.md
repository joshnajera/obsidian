
```gdscript
var ray_origin = Vector3()
var ray_target = Vector3()

func _physics_process(delta):
	var mouse_pos = get_viewport().get_mouse_position() // Gets the mouse position on the 2D "screen" of the camera
	ray_origin = $Camera.project_ray_origin(mouse_position) == Projects a ray through the camera's origin to the cursors position, returning intersections
	ray_target = ray_origin + $Camera.project_ray_normal(mouse_position) * 2000
	var space_state = get_world().direct_space_state // get current physics state
	var intersction = space_state.intersect_ray(ray_origin, ray_target)

if not intersection.empty():
	var pos = intersection.position // 

```