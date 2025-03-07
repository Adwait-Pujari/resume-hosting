# Hosting a Resume on a Static Site Generator Using Forges

## Purpose
This README provides clear, concise instructions for formatting and hosting a resume on a forge that supports static site hosting on a Windows system. Following modern technical writing principles, it ensures readability, ease of maintenance, and accessibility. This guide is intended for individuals with basic Markdown knowledge but no prior experience with Git, static site generators, or forges.

## Prerequisites
Before proceeding, ensure you have the following:
- A resume formatted in **Markdown** (lightweight markup improves maintainability and readability).
- A **Git** client installed ([Git Installation Guide](https://git-scm.com/downloads)).
- A chosen **static site generator** – This guide uses **[Pelican](https://getpelican.com/)** (other options include **Jekyll, Hugo**).
- **Python** installed ([Python Installation Guide](https://www.python.org/downloads/)) as required for Pelican.
- An account on a **forge** – This guide uses **GitHub** (other options include **GitLab, Codeberg**).

## Instructions

### Step 1: Set Up Your Repository
1. **Create a new repository** on GitHub.
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
3. Stage and commit the file:
   ```bash
   git add resume.md
   git commit -m "Added resume"
   ```

### Step 3: Set Up Pelican on Windows
Following the process-oriented guidance from Pfeiffer & Adkins, present your instructions in clear, ordered steps:

### A. Install Python for Windows
   
   1. **Download the Installer:**
      
      Visit [Python](https://www.python.org/downloads/windows/) and download the latest Python installer for Windows.
      
      **Important** : After visiting the above website and selecting the **'Stable Python Version'** scroll down to the bottom of the page where it says **'Files'** and downloaded the recommended windows installer.
   
   <br>

   2. **Configure the Installer:**

      **Important**: During installation, check the box **"Add Python to PATH"** to ensure that Python and pip are accessible from the command line.
   
   <br>

   3. **Verify Installation:**
      
      Open Command Prompt and run:
      ```bash
      python --version
      ```
      This should display your installed Python version.
   
### B. Install Pelican and Dependencies

   1. **Update pip (if necessary):**
   
      In Command Prompt or PowerShell (run as administrator if required), update pip:
      ```bash
      python -m pip install --upgrade pip
      ```
      <br>

   2. **Navigate to the repository:** 
   
      Open the Github folder insitalized in Step 1.

      <br>

   3. **Install Pelican and Markdown:**
      
      Run:
      ```bash
      python -m pip install "pelican[markdown]"
      ```

   4. **Create a project:**

      Create a folder for your site and create a skeleton project inside of it.
      
      Run the following command:
      ```bash
      mkdir ./projects
      ```

### C. Initialize and Configure Your Pelican Project

   1. **Run Pelican Quickstart:**
      
      In your repository directory, initialize a new Pelican project:
      ```bash
      pelican-quickstart
      ```

   2. **Answer the given questions promtps after running pelican:**

      ```bash
         > Where do you want to create your new web site? [.]
         > What will be the title of this web site? <Resume Title>
         > Who will be the author of this web site? <Your Name>
         > What will be the default language of this web site? [en]
         > Do you want to specify a URL prefix? e.g., https://example.com (Y/n) n
         > Do you want to enable article pagination? (Y/n) n
         > How many articles per page do you want? [10]
         > What is your time zone? [Country/City]
         > Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n)
         > Do you want to upload your website using FTP? (y/N) n
         > Do you want to upload your website using SSH? (y/N) n
         > Do you want to upload your website using Dropbox? (y/N) n
         > Do you want to upload your website using S3? (y/N) n
         > Do you want to upload your website using Rackspace Cloud Files? (y/N) n
         > Do you want to upload your website using GitHub Pages? (y/N) y
      ```

   3. **Update your Resume:**

      Update your `resume.md` with the first three lines, as it is required by the pelican to host your website.
      ```bash
         Title: <Your Title>
         Date: <YYYY-MM-DD HH:MM>
         Category: <RESUME>
      ```

   4. **Include Your Resume:**

      Place your `resume.md` file in the Pelican content Directory (usually named content)

   5. **Review Configuration:**

      Open the `pelicanconf.py` file to ensure it includes your content directory and any additional settings required for your site.

   6. **Build the site:**

      Generate the static site by running:
      ```
      pelican content
      ```
      **Important** : Note you must be outside the content folder to run the pelican command.

   7. **Test the site by running locally**

      Use the following command to run locally:
      ```bash
      pelican --listen
      ```
      This will generate a link and if followed to that link it will locally host the website on your computer.

### Step 4: Deploy the Site
1. Push the changes to the remote repository:
   ```bash
   git push origin main
   ```
2. Enable static site hosting on the forge (e.g., GitHub Pages, GitLab Pages).
3. Obtain the URL of your hosted site and verify accessibility.

## Technical Writing Best Practices
1. **Use Lightweight Markup** – Markdown is easier to write and maintain than raw HTML.
2. **Leverage Version Control** – Git tracks changes efficiently, ensuring content accuracy.
3. **Avoid Redundancy** – Maintain a single source of truth for documentation.
4. **Make It Scannable** – Use headings, lists, and concise steps for clarity.

## Further Resources
- [Markdown Guide](https://www.markdownguide.org/)
- [Git Basics](https://git-scm.com/doc)
- [Pelican Documentation](https://docs.getpelican.com/en/latest/)
- [GitHub Pages Documentation](https://pages.github.com/)

## FAQ

**Q: Why use Markdown instead of raw HTML?**  
*A: Markdown is simpler, more readable, and widely supported by static site generators.*

**Q: My resume updates aren’t showing. What should I check?**  
*A: Ensure you have committed and pushed changes, and that Pelican has rebuilt the site.*

**Q: Why is my GitHub Pages site showing a 404 error?**  
*A: GitHub Pages can take a few minutes to process changes. If the issue persists, verify that you have set the branch correctly in the Pages settings and that your content is in the correct directory.*

**Q: How do I change the theme of my Pelican site?**  
*A: You can download and apply themes from the [Pelican Themes Repository](https://github.com/getpelican/pelican-themes) by updating the `pelicanconf.py` file.*

**Q: What should I do if Python is not recognized as a command?**  
*A: Ensure Python is installed and added to the system PATH. You can check by running `python --version` in the command prompt. If not recognized, reinstall Python and check the "Add to PATH" option during installation.*

**Q: How can I check if my site is being indexed by search engines?**  
*A: GitHub Pages automatically includes a `robots.txt` file. To confirm indexing, use Google Search Console or inspect the `robots.txt` file in your browser by visiting `your-site-url/robots.txt`.*

## Credits
- **Contributors**: Adwait Pujari
- **Peer Review Contributors**: Om Sevek, Meshvi Patel
- **Third-Party Tools and Resources**:  
  - Static site templates provided by [Pelican Themes](https://github.com/getpelican/pelican-themes)  
  - Guidance from GitHub Pages documentation and Markdown tutorials  
- **Instructional References**:  
  - Andrew Etter’s principles on using lightweight markup and version control for effective documentation

