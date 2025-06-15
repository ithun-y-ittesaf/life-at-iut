
## 📁 How to Use This Repository

### ✅ For Personal Use (Users)

If you want to use this repository for your own notes or setup:

1. **Clone the repository** to your local machine:

   ```bash
   git clone <repo-url>
   ```

2. **Add the cloned folder** to your Obsidian vault. That's it—you're good to go!

---

### 🤝 For Collaborators

If you're contributing to this repository, please follow these important guidelines:

1. **Pull the latest changes** before making any edits:

   ```bash
   git pull
   ```

2. **Placeholder `.txt` files** have been added to each directory to ensure folder structure is preserved on GitHub and in local clones.
   **Do not delete these placeholders** unless you are adding new files to that folder.

3. **Handling PDFs:**

   * The repository is configured to **ignore all `.pdf` files** via `.gitignore` to avoid performance issues with large files.
   * If you need to include PDFs, **keep them locally** and instead:

     * Create a `.zip` file containing the PDF(s).
     * Place the `.zip` in the same directory.
     * Commit the `.zip` file—**this ensures efficient version control and keeps the repo lightweight**.

  * When adding slides, project outline documents, etc. (basically very small PDFs), use the command:
      ```bash
      git add -f path/to/file.pdf
      ```


