

# Client-side


# Server-side
## Static Rendering
- Caches 
- Example: If you were to print out `{new Date().toLocaleTimeString()}` it would be rendered when you run build or dev, and wouldn't change upon page load/reload
## Dynamic Rendering
- Renders at request-time




# Viewing which components are static
- When we run `npm run build` static components will be marked with a circle
- Static components are automatically rendered as static HTML