Implemented via an exported constant

1. Static MetaData
```jsx
export const metadata = {
	title: "Home",
}
```
2. Dynamic MetaData
```jsx
export async function generateMetadata({params, searchParams}) {
	// Params: An object containing the dynamic urlParameters
	// searchParams: An object containing the url search parameters
	// Get product info
	const product = await getProduct(params.id);

	return {
	title: product.title
	}
}

export default function Page(){
	 return (
	 <h1>my page with meta</h1>
	 )
}
```
