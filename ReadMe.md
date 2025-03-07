# Hosting a Resume on a Static Site Generator Using Forges

## Purpose
This README provides instructions for formatting and hosting a resume on a forge that supports static site hosting. It is intended for individuals with basic knowledge of Markdown but no prior experience with Git, static site generators, or forges.

## Prerequisites
Before proceeding, ensure you have the following:
- A resume formatted in **Markdown**
- A **Git** client installed ([Git Installation Guide](https://git-scm.com/downloads))
- A chosen **static site generator** – For this documentation, we will be using **Pelican** (other options include **Jekyll, Hugo**)
- **Python** installed ([Python Installation Guide](https://www.python.org/downloads/)) as it is required for Pelican
- An account on a **forge** – For this demo, we will be using **GitHub** (other options include **GitLab, Codeberg**)

## Instructions

### Step 1: Set Up Your Repository
1. **Create a new repository** on your chosen forge.
2. Clone the repository locally:
   ```bash
   git clone <repository-url>
   ```
3. Navigate to the cloned directory:
   ```bash
   cd <repository-name>
   ```

### Step 2: Add Your Resume
1. Create a new file named `resume.md` in the repository.
2. Copy and paste your Markdown-formatted resume into `resume.md`.
3. Add the file to Git:
   ```bash
   git add resume.md
   ```
4. Commit the changes:
   ```bash
   git commit -m "Added resume"
   ```

### Step 3: Set Up a Static Site Generator
1. Install your chosen static site generator.
2. Configure it to recognize `resume.md` as content.
3. Build the site locally to verify formatting:
   ```bash
   <generator-command> build
   ```

### Step 4: Deploy the Site
1. Push the changes to the remote repository:
   ```bash
   git push origin main
   ```
2. Enable static site hosting on the forge (e.g., GitHub Pages, GitLab Pages).
3. Obtain the URL of your hosted site and verify that your resume is accessible.

## Technical Writing Principles (Etter’s *Modern Technical Writing*)
1. **Use a Lightweight Markup Language** – Markdown is chosen for its simplicity and readability.
2. **Version Control Best Practices** – Git ensures changes are tracked and reversible.
3. **Automation & Static Site Generators** – Automating site generation reduces manual effort.
4. **Hosting on a Forge** – Publicly accessible repositories improve collaboration and maintainability.

## Further Resources
- [Markdown Guide](https://www.markdownguide.org/)
- [Git Basics](https://git-scm.com/doc)
- [Choosing a Static Site Generator](https://www.staticgen.com/)
- [GitHub Pages Documentation](https://pages.github.com/)

## FAQ
**Q: Why is Markdown better than writing raw HTML?**  
*A: Markdown is simpler, more readable, and widely supported by static site generators.*

**Q: I updated my resume, but changes aren’t showing. Why?**  
*A: Ensure you have committed and pushed the changes, and your static site generator has rebuilt the site.*

## Credits
- Contributors: [Your Name]
- Static site themes, images, and third-party resources are credited as per their licenses.

