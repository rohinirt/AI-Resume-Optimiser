# Resume Optimiser : https://rohinirt.github.io/AI-Resume-Optimiser/

Upload your resume (.docx), Uber experience file, projects file and a job description. The app scores the match, rewrites your summary, experience bullets, projects and skills from your own facts, explains each change, and exports Word or PDF.

It is a single static page (`index.html`). There is no server and no build step.

## Publish it free on GitHub Pages

1. Sign in at github.com and select **New repository**. Name it `resume-optimiser`, set it to **Public**, and create it.
2. Select **Add file > Upload files**, drag in `index.html` and this `README.md`, then select **Commit changes**.
3. Open **Settings > Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then select **Save**.
4. After about a minute your site is live at `https://YOUR-USERNAME.github.io/resume-optimiser/`.

## Using the app

1. Get a free key at https://aistudio.google.com/apikey (Google sign-in, no card).
2. Open your site, expand **AI settings**, paste the key, and pick a model.
3. Upload your four inputs, select **Analyse match**, then **Rewrite my resume**.

The key is saved only in your own browser. It is never in the code, so the public repo is safe. Anyone who visits your site pastes their own key.

## Limits

- GitHub Pages hosting is free. The page has no usage cap of its own.
- The AI is Google's free Gemini API, which has per-key rate and daily limits. No free AI service is truly unlimited. If you hit a limit, wait a minute or switch to **Flash-Lite**, which has higher free limits.
- Free-tier Gemini inputs may be used by Google to improve its products (check Google's current terms). If that matters for your resume, use a paid key.

## Notes

- Resume input must be .docx. Convert PDFs to Word first.
- The Word download keeps your original formatting. The PDF is rebuilt from the text.
