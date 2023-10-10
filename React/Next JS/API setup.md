
- There are 2 different ways to define API routes
	1. Create a route within an API directory
	2. Create a route within the app directory
- Cannot exist in the same folder as a page.jsx / tsx file?
- Supports
	- GET
	- POST
	- PUT
	- PATCH
	- DELETE
	- HEAD
	- OPTIONS


route.jsx / tsx
```jsx
export async function GET(request) {
	return new Response('Hello, Next.js!');
}
export async function POST(request) {}
export async function PUT(request) {}
export async function PATH(request) {}
export async function DELETE(request) {}
export async function HEAD(request) {}
export async function OPTIONS(request) {}
```