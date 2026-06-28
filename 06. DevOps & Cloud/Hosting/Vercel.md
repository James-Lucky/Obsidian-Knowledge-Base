How to Deploy a Project Using Vercel

Step 1: Install Vercel Globally
Open your terminal and run: npm install -g vercel

Step 2: Navigate to Your Project Directory
Open the project folder in VS Code or your terminal: cd your-project-folder

Step 3: Deploy the Project
For initial deployment (first-time setup), run: vercel
It will prompt you with configuration options (like project name, framework, etc.). Follow the prompts to complete setup and deploy.

Step 4: Deploy New Changes
If your project is already deployed and you want to deploy changes, use: vercel deploy
After deployment, Vercel will provide a preview link.

Step 5: Deploy to Production
If the preview looks good, deploy to production by running: vercel --prod
