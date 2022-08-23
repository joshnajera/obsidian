## Array rendering
React renders arrays naturally, this can be used with JSX elements


Example
```js
export default function App() {
    const data = [{coverImg:"...",...other fields...}, ...{}] // Where data is an array of objects
    const cards = data.map(item => {
        return (
            <Card // Card is some component elsewhere defined
	            key={item.id}
                img={item.coverImg}
                rating={item.stats.rating}
                reviewCount={item.stats.reviewCount}
                location={item.location}
                title={item.title}
                price={item.price}
            />
        )
    })        
    
    return (
        <div>
            <Navbar />
            {cards}
        </div>
    )
}
```

Note: unique key value may be required when using map, may possibly throw error.