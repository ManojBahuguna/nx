# Deploying Next.js applications to Vercel

Starting from Nx 11, your Next.js application should already be ready for deployment to Vercel.

## Configure your Vercel project's settings appropriately

### New Vercel project

1. If you are "importing" your Nx workspace's repository for the first time, make sure you do _not_ choose a root directory as part of the repo selection process (therefore leaving it to be the root of the full repo/workspace)
2. Ensure the Next.js "Framework Preset" is selected
3. Expand the "Build and Output Settings" and toggle the override switch for the build command. For example, for an application named `tuskdesk` the value will look like this:

```bash
npx nx build tuskdesk --prod
```

4. Toggle the override switch for the output directory. Point it to the `.next` directory inside the built app:

```bash
dist/apps/tuskdesk/.next
```

Therefore, our full configuration (based on a repo called "nx-workspace" and a project called "tuskdesk") will look like this:

![image](./next-deploy-vercel-1.png)

### Existing Vercel project

If you have an existing project on Vercel then the exact same guidance applies as for the section above, it's just that you will need to update the project's existing settings.

When everything is updated appropriately, for our `tuskdesk` example we would see the following in our "General" settings UI:

![image](./next-deploy-vercel-2.png)

Naturally, you can continue on and set any additional Environment Variables etc that may be appropriate for your projects, but we have now covered the key points needed to deploy Next.js projects from Nx workspaces on Vercel!
