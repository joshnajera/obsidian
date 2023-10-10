# SSG, SSR, ISG
Fairly straightforward/simple
- In comparison to client-side fetching, server-side has the added benefit of being able to cache.
- Caching happens by default
```jsx
import react from 'react';

const UserPage = async () => {
	// Caching by default -- Static site generation by default
	const res = await fetch('https://jsonplaceholder.typicode.com/users');
	// Disable caching! -- Server-side render
	const res = await fetch('https://jsonplaceholder.typicode.com/users', { cache: 'no-store'});
	// OR, cache with auto-refresh every (10)sec -- Incremental Static Generation
	const res = await fetch('https://jsonplaceholder.typicode.com/users', { next: {revalidate: 10} });
	
	const users = await res.json();

	return (
	<>
		<h1>Users</h1>
		<ul className='users'>
		{users.map(user => <li key={user.id}>{user.name}</li>)}
		</ul>
	</>
	)
}
```


