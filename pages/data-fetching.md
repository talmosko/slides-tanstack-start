---
---
# Data Fetching

<div class="flex flex-col justify-between h-[82%]">   

````md magic-move {lines: true}
```tsx
// Fetching critical data on server-side
export const route = createRoute({
  loader: async () => {
    await queryClient.ensureQueryData(postsQuery)
  },
  component: () => {
    const query = useQuery(postsQuery)
    // Data is already available from loader
    return <PostsList posts={query.data} />
  }
});

```

```tsx
// We can use `fetch` directly in the loader instead of `TanStack Query`
export const route = createRoute({
  loader: async () => ({
    posts: await fetchPosts()
  }),
  component: () => {
    const { posts } = useLoaderData()
    return <PostsList posts={posts} />
  }
});
```
````

<DataFetchingStepper :currentStep="0" class="mt-auto" />

</div>


---
---
# Data Fetching


<div class="flex flex-col justify-between h-[82%]">   

````md magic-move {lines: true}
```tsx
// Prefetch data with deferred loading using `SuspenseQuery`
export const route = createRoute({
  loader: async () => {
    queryClient.prefetchQuery(postsQuery)
  },
  component: () => {
    const { data } = useSuspenseQuery(postsQuery)
    return <PostsList posts={data} />
  }
});
```

```tsx
// Deferred loading with `Await` component
export const route = createRoute({
  loader: async () => ({
    postsPromise: fetchPosts()
  }),
  component: () => {
    const { postsPromise } = useLoaderData()
    return (
      <Await 
        promise={postsPromise}
        children={posts => {
          return <PostsList posts={posts} />
        }}
      />
    )
  }
});
```
````
<DataFetchingStepper :currentStep="1" class="mt-auto" />

</div>


---
---
# Data Fetching

<div class="flex flex-col justify-between h-[82%]">   

```tsx
// Dynamic streaming

const { data } = useSuspenseQuery(postsQuery)
    
```

<DataFetchingStepper :currentStep="2" class="mt-auto" />

</div>

---
---
# Data Fetching

<div class="flex flex-col justify-between h-[82%]">   
    

```tsx
// Client-only data fetching

const { data } = useQuery(postsQuery)
    
```

<DataFetchingStepper :currentStep="3" class="mt-auto" />

</div>
