# How to use Golang generics with structs

## Learn how to create a generic struct to make the most of this feature

![](https://miro.medium.com/v2/resize:fit:700/1*CJ-Wx5mXF_fo3p1yKh_5bg.png)

Since Go 1.18, we finally have the power of generics. This week, while I was looking through the Golang source code, I found an example of how to create structs using generics.

In this post, I’ll show you how to do this.

Before we begin, let’s assume we are implementing a blog system with the two structs listed below.

```=golang
package blog

type Category struct {
    ID int32
    Name string
    Slug string
}

type Post struct {
    ID int32
    Categories []Category
    Title string
    Description string
    Slug string
}
```

Seeking some performance improvement, we’ll implement a cache system that guarantees that no one can modify any data directly inside the cache.

With these specs in mind, let’s create a new package with the name of cache.

This package needs a private struct to hold all the data that we want to cache. But, before we create this struct, let’s create an interface for the types that will be cacheable.

```=golang
package cache

type cacheable interface {

blog.Category | blog.Post

}
```

Good! Now we can create our private and generic struct to hold the data.

```=golang
type cache[T cacheable] struct {

data[string]T

}
```

To manipulate the data, we gonna implement two methods, Set and Get.

```=golang
func (c *cache[T]) Set(key string, value T) {

c.data[key] = value

}

func (c *cache[T]) Get(key string) (v T) {

if v, ok := c.data[key]; ok {

return v

}

return

}

```

Now, let’s add a generic function to create and return a pointer to a new cache.

```=golang
func New[T cacheable]() cache[T] {

c := cache[T]{}

c.data = make(map[string]T)

return &c

}
```

NICE!!!

To use our package, all we need to do is create a new cache for the type we wanna cache and use the methods of the struct like the example below.

```=golang
func main() {

// create a new category

category := blog.Category{

ID: 1,

Name: "Go Generics",

Slug: "go-generics",

}

// create cache for blog.Category struct

cc := cache.New[blog.Category]()

// add category to cache

cc.Set(category.Slug, category)

// create a new post

post := blog.Post{

ID: 1,

Categories: []blog.Category{

{ID: 1, Name: "Go Generics", Slug: "go-generics"},

},

Title: "Generics in Golang structs",

Text: "Here go's the text",

Slug: "generics-in-golang-structs",

}

// create cache for blog.Post struct

cp := cache.New[blog.Post]()

// add post to cache

cp.Set(post.Slug, post)

}
```

Leave your questions in the comments and I’ll answer ASAP.

Thank’s for reading!