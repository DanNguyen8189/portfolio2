# portfolio2

2nd version of my software developer portfolio, deployed at https://dannguyencodes.netlify.app/

## Build Setup

```bash
# install vue-cli

# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

## Notes

### Adding a project

To add or remove a project, go to ./contents/projects/projects.json  
The formatting looks like this:
```json   
{  
    "title": "title",  
    "img": "imageFileName",  
    "description": "description",  
    "github": "githubLink",  
    "link": "liveDemoLink",  
    "technologies": ["technology1", "technology2", "..."]  
}  
```

Fields can be left out. If the "img" field is left out, the project is displayed with the BasicProject component. Otherwise it's displayed with the FeaturedProject component.

### Project images

Project images can be added in ./static  
The code will find the images there


