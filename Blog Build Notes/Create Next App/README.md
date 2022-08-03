## Create Next app with Typescript, and Tailwindcss
I first created a folder with my blog project name, journey-blog, I dragged and dropped that folder into VS Code. 
I like to use yarn, so inside a terminal window in VS Code I entered this command to initialize the project.

[Next.js documentation](https://nextjs.org/docs/getting-started) was also helpful with this initialization, because I wanted to use 
TypeScript.

```Shell
yarn create next-app --typescript -e with-tailwindcss ./
```
## Add dependencies
After the app has been created I added the necessary dependencies for the app.

```Shell
yarn add graphql graphql-request html-react-parser moment react-multi-carousel sass react-icons
```
I also added some more information to the package.json file.

```json
  "name": "journey-blog",
  "description": "collection of notes from my self taught developer journey.",
  "author": "wrappedusername",
  "version": "0.1.0",
```
## yarn dev
To run the app I use the yarn dev command. The new website is visible on localhost:3000. 
```Shell
yarn dev
```
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
I created a demonstration post, before fetching the data from graphql. 

```JavaScript
const posts = [
   { title: 'Wed-Dev-Notes', excerpt: 'Collection of notes from self taught developer journey." }
];

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
