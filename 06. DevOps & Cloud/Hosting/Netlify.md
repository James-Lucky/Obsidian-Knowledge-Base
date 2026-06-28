
How to Deploy a Project Using Netlify (with CI/CD)

1: Push Your Project to GitHub

2: Commit and push all your changes:

3: Connect Your Repository
Click “Add New Site” → “Import an existing project”.

4: Configure Build Settings
Build Command: Usually
npm run build (React, Vue, Svelte, etc.)

5: Deploy
Click Deploy Site.
Netlify will pull code from your Git repo, run the build command, and host it.

6: Set Up CI/CD
It’s automatic — every time you push changes to your main branch, Netlify will rebuild and redeploy.

7: (Optional): Custom Domain
Go to Domain Settings in your site dashboard.

npm install -g netlify-cli
netlify login
netlify init   
netlify deploy 
netlify deploy --prod
