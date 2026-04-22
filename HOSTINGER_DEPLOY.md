# Deployment to Hostinger (Node.js Hosting)

To host this application on Hostinger, follow these steps:

## 1. Prepare for Export
In AI Studio, click **Settings > Export > Download as ZIP**.

## 2. Generate the Production Build
Locally (on your computer) or via a CI/CD pipeline:
1. Extract the ZIP.
2. Open a terminal in the folder.
3. Run `npm install`.
4. Run `npm run build`.
   - This creates a `dist` folder containing the compiled frontend and the `server.cjs` backend bundle.

## 3. Upload to Hostinger
1. Log in to your Hostinger hPanel.
2. Go to **Websites > Manage > Node.js**.
3. Create a new Node.js application.
4. Upload all project files to your domain's directory, **including the `dist` and `Material` folders**.
5. In the Hostinger Node.js configuration:
   - **App Directory**: Your project folder (e.g., `/`)
   - **App Environment**: `Production`
   - **App Entry Point**: `app.js` (this file acts as a bridge to your built server)
6. Run `npm install` within the Hostinger terminal (or use their UI button).
7. Start/Restart the application.

## 4. Configuration
Ensure you set your `GEMINI_API_KEY` (if used) in the Hostinger **Environment Variables** section.

## Note on Static Hosting
If you only want to host the frontend (without the customer database features), simply upload the contents of the `dist` folder to your `public_html` directory and ensure you have a `.htaccess` file for SPA routing.
