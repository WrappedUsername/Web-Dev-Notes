# Create Next App with Typescript, and Tailwindcss
<p align="left"> <img src="https://komarev.com/ghpvc/?username=CreateNextApp&label=Repository%20views&color=0e75b6&style=flat" alt="wrappedusername" /> </p>

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

