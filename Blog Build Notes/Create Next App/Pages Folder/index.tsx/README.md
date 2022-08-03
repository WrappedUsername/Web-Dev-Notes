## Working on index.tsx inside the pages folder
The pages folder has one of the most important files in the app, the index.tsx file. I started working on this file removing
most of the boilerplate code. I created my own favicon in the link, and changed the title to Journey Blog, I left the outer div and Head.

The outer div className was changed to "container mx-auto px-10 mb-8 gradient-bg-container", and I changed const Home = () =>
to export default function Home ().
```JavaScript
import Head from 'next/head'
///@notice Changed const Home = () =>
export default function Home () {
  return (
    <div className="container mx-auto px-10 mb-8 gradient-bg-container">
      <Head>
        <title>Journey Blog</title>
        <link rel="icon" href="/favicon.ico" />
      </Head>
    </div>
  )
}
```

The next div will be for looping through the blog posts.
              
```JavaScript
export default function Home () {
  return (
    <div className="container mx-auto px-10 mb-8 gradient-bg-container">
      <Head>
        <title>Journey Blog</title>
        <link rel="icon" href="/favicon.ico" />
      </Head>
    </div>
      <div className="grid grid-cols-1 lg:grid-cols-12 gap-12"> 
  
      </div>
  )
}               
```
## Demo post
I created a demonstration post above the Home function, before fetching the data from graphql. 

```JavaScript
const posts = [
  { title: 'Web-Dev-Notes', excerpt: 'Collection of notes from my self taught developer journey.' },
]; 
```
