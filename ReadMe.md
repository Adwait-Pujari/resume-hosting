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
3. Stage and commit the file:
   ```bash
   git add resume.md
   git commit -m "Added resume"
   ```

### Step 3: Set Up Pelican on Windows
Following the process-oriented guidance from Pfeiffer & Adkins, present your instructions in clear, ordered steps:

#### A. Install Python for Windows
   
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
   
<!-- 1. Install Pelican:
   ```bash
   pip install pelican
   ```
2. Initialize a Pelican project:
   ```bash
   pelican-quickstart
   ```
3. Configure `pelicanconf.py` to include `resume.md` in content.
4. Generate the site:
   ```bash
   pelican content
   ``` -->

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
*A: Ensure you’ve committed and pushed changes, and that Pelican has rebuilt the site.*

## Credits
- **Contributors**: Adwait Pujari
- **Peer Review Contributors**: Om Sevek, Meshvi Patel
- **Third-Party Tools and Resources**:  
  - Static site templates provided by [Pelican Themes](https://github.com/getpelican/pelican-themes)  
  - Guidance from GitHub Pages documentation and Markdown tutorials  
- **Instructional References**:  
  - Andrew Etter’s principles on using lightweight markup and version control for effective documentation

