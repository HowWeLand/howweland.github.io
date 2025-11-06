# howweland.github.io
This is where my business card lives

# GitHub Pages Digital Business Card Template

These files provide a template for a personal digital business card, designed to be hosted for free on GitHub Pages.

## How to Use This Template

### Step 1: Customize Your Files

Before you upload anything, you need to edit the files to include your personal information.

1.  **Edit `index.html`:**
    * Open `index.html` in any text editor.
    * **Info:** Find the text "James Myint Jr." and "Independent Security Researcher" and replace them with your name and title.
    * **About Me:** Change the quote in the "About Me" section to your own.
    * **Contact/Links:** Replace all `href="..."` links (like `mailto:`, `tel:`, `https://github.com/...`, `https://www.linkedin.com/...`) with your own.
    * **vCard:** Scroll down to the `<script>` tag at the bottom. Carefully edit the `vCardData` fields (`N:`, `FN:`, `TITLE:`, `TEL:`, `EMAIL:`, `URL;TYPE=GitHub:`, etc.) with your own information.
    * **QR Code:** Change the `data=` part of the `api.qrserver.com` URL to point to your new site's URL (e.g., `https://your-username.github.io`).
    * **Resume Links:** Note the names of the resume files this page links to (`resume.html` and `James_Myint_Jr_Resume.pdf`). If you change these, you must update the links here.

2.  **Edit `resume.html`:**
    * Open `resume.html` and replace all the placeholder content (Summary, Skills, Experience, Education) with your own.

### Step 2: Create Your Resume PDF

The business card links to both a web page resume (`resume.html`) and a downloadable PDF version. You need to provide this PDF.

1.  Create your resume in any program (Word, Google Docs, or LaTeX).
2.  Save or export it as a PDF.
3.  **Crucially:** Rename the downloaded file to match the name in the `index.html` link (e.g., `Your_Name_Resume.pdf`). You will also need to update the link in `index.html` to point to this new filename.

### Step 3: Set Up Your GitHub Pages Repository

1.  Log in to your GitHub account.
2.  Create a **new, public repository** and name it **exactly**: `your-username.github.io`
    * (Replace `your-username` with your actual GitHub username).
    * This specific naming convention is what tells GitHub to turn this repository into a website.
3.  In your new repository, click the "Add file" button and choose "Upload files".

### Step 4: Upload Your Files

Upload your three customized files into your new repository:

1.  `index.html` (your edited main card page)
2.  `resume.html` (your edited web-based resume)
3.  `Your_Name_Resume.pdf` (your personal PDF resume)

After you've uploaded and committed (saved) these files, you're done!

### Step 5: Visit Your Live Site

GitHub will automatically build and deploy your site. It can take 1-2 minutes. Once it's ready, you will be able to visit it at:

**[https://your-username.github.io](https://your-username.github.io)**

That's it! Your electronic business card is now live.
