# Swizling

Allows for partial accessing of vectors using their named vector components.
They do not need to be in order, but the order they are listed is the order in which they are accessed. The following are all valid examples of this.
```Example
COLOR.rgb
COLOR.bgra
COLOR.ggg
COLOR.r
```
Also allows for reassigning different combinations.

## COLOR
Has RGBA (Red, Green, Blue, Alpha) values that can be accessed.

```Example
COLOR.rgba = COLOR.bgra
```

## UV
Has X and Y values that can be accessed