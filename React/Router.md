
```jsx
<Router>
	<Routes>
		<Route path='/' element={<Home />} />
		<Route path='posts' element={<Posts />} >
			<Route path='new' element={<NewPost />} >
			<Route path=':postId' element={< Post />} >
		</Route>
	</Routes>
</Router>

```