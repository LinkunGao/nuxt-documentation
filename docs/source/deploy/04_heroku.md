# Host app on Heroku

1. Create a nuxt project and make sure your project root conatins `package-lock.json` or `yarn.lock`. But they cannot exist togerther. You only can include one of them.

2. Create a emptry app on Heroku. Then in your project:

   ```bash
   heroku login
   git init
   heroku git:remote -a this-is-your-app-name
   heroku config:set NPM_CONFIG_PRODUCTION=false
   heroku config:set HOST=0.0.0.0
   heroku config:set NODE_ENV=production
   ```

3. Create a Procfile file, only name it `Procfile`, no extension name, like `Procfile.txt` is not work. Then inside the file, write these codes:

   ```bash
   web: npm run start
   ```

4. Check you npm and node version number:

   ```bash
   npm -v
   node -v
   ```

5. In your pakeage.json file, wirte down the npm and node version in `engines`:

   ```json
   {
     "scripts": {
       "dev": "nuxt",
       "build": "nuxt build",
       "start": "nuxt start",
       "generate": "nuxt generate",
       "heroku-postbuild": "npm run build" // if this is not work try: "heroku-postbuild": "npm run generate"
     },
     "engines": {
       "node": "14.16.0",
       "npm": "8.5.2"
     }
   }
   ```

6. After you editing the code:

   ```bash
   git add .
   git commit -am "Hello Heroku"
   git push heroku master
   ```
