# Vigi Hub

**The official community registry for Vigi tools and personas.**

Welcome to the central hub for the Vigi ecosystem! This repository acts as a curated index of community-created tools (procedures) and personas that you can easily install and use with the Vigi CLI.

> **Note:** This repository does not contain the source code for the tools themselves. Instead, it holds a `registry.json` file that points to scripts and configurations hosted in the creators' own public repositories.

### For Vigi Users: Discovering and Installing Tools

The Vigi Hub is integrated directly into the `vg` command line, making it simple to find and add new capabilities.

#### List Available Resources

To see all the tools and personas available in the community hub, run:

```bash
vg .hub .list
```

This will fetch the latest registry and display a formatted list of all available items, including their names and descriptions.

#### Install a Tool or Persona

Once you find a tool you like, you can install it using its unique namespaced identifier (`<author>/<tool_name>`).

**To install a tool:**

```bash
# Example: Installs the 'wiki_scraper' tool made by user 'raff'
vg .hub .install "raff/wiki_scraper"
```

Vigi will automatically download the script to your local `~/Desktop/VIGI/functions/` directory and prompt you to install any required dependencies.

**To install a persona:**

```bash
# Example: Installs the 'SarcasticHelper' persona made by user 'jdoe'
vg .hub .install --persona jdoe/SarcasticHelper
```

This will download the persona's JSON configuration to your local `~/Desktop/VIGI/roles/` directory, making it available for use with `vg .prs` or `vg .talk --role SarcasticHelper`.

### For Creators: How to Contribute

Have you created a cool tool or a useful persona? Share it with the community! The process is designed to be as simple as a standard GitHub pull request.

**Step 1: Host Your File**
-   Create a **public GitHub repository** to host your Vigi resources.
-   Add your tool (`.py` file) or persona (`.json` file) to that repository.
-   Get the URL to the **raw** version of your file. You can get this by navigating to your file on GitHub and clicking the "Raw" button. The URL will look something like `https://raw.githubusercontent.com/<username>/<repo>/main/<filename>`.

**Step 2: Fork and Edit the Registry**
-   Fork this `vigi-hub` repository.
-   Clone your fork to your local machine.
-   Open the `registry.json` file and add an entry for your resource. **Use the namespaced format `<your-github-username>/<your-tool-name>` as the key to prevent naming conflicts.**

**Step 3: Submit a Pull Request**
-   Commit your changes to `registry.json`.
-   Push the changes to your fork.
-   Open a Pull Request back to this main `vigi-hub` repository.
-   In your PR description, briefly explain what your tool or persona does.

#### Registry Format

**Example for a Tool:**

```json
{
  "tools": {
    "raff/wiki_scraper": {
      "author": "raff",
      "description": "A simple tool to scrape and summarize a Wikipedia article.",
      "url": "https://raw.githubusercontent.com/raff/vigi-extras/main/wiki_scraper.py",
      "dependencies": ["beautifulsoup4", "requests"]
    }
  },
  "personas": {
    ...
  }
}
```
-   **`author`**: Your GitHub username.
-   **`description`**: A concise, one-sentence explanation of what your tool does.
-   **`url`**: The direct link to the **raw** Python file.
-   **`dependencies`** (Optional): A list of Python packages required for your tool to run. Vigi will prompt the user to install these.

**Example for a Persona:**

```json
{
  "tools": {
    ...
  },
  "personas": {
    "jdoe/SarcasticHelper": {
      "author": "jdoe",
      "description": "A persona that provides correct answers but with a witty, sarcastic tone.",
      "url": "https://raw.githubusercontent.com/jdoe/vigi-personas/main/SarcasticHelper.json"
    }
  }
}
```

#### Review Process

We will review your pull request to ensure the link is valid, the description is clear, and the tool is not malicious. Once merged, your contribution will be available to all Vigi users!

---

Happy creating and automating with [Vigi](https://github.com/Muhammad-Subhan-Rauf/vigi)
