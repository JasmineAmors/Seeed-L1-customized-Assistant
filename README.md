# Seeed L1-customized Assistant

[English](README.md) · [简体中文](README.zh-CN.md)

A Windows tool for finding Seeed products, checking specifications and box contents, saving favorites, and organizing customization requests. AI chat is optional. **Basic lookup needs no AI subscription or programming knowledge.**

## Start here: first-time user guide

### Understand the basics

- A **repository** stores application files and instructions. Download from its **Code** page.
- A **GitHub Project** is a task board, not an installer. Customization projects saved inside this application are separate local records and do not automatically sync with GitHub Projects.
- **Deployment in this guide** means downloading and running the application on your PC. No server or domain purchase is needed. Uploading to GitHub does not start the app online.
- This repository is **Public**: colleagues can view and download it without a GitHub account or invitation. The GitHub Project board has separate permissions, which do not affect application downloads.

### Step 1: prepare your computer

Use a Windows 10/11 **x64 PC**, with Edge or Chrome. The double-click workflow is for Windows; this guide does not promise support for macOS, Linux, phones, or Windows ARM.

Internet is required for the initial download. The application and images occupy a little over 100 MB; allow extra extraction and update space. Full functionality requires **64-bit Python 3.12 or 3.13**, the runtime that runs the application. Ordinary users do not need Git, GitHub Desktop, Node.js, or Codex.

### Step 2: download the complete application

1. Sign into a GitHub account with access and open [this repository](https://github.com/JasmineAmors/Seeed-L1-customized-Assistant).
2. If you see a planning board, follow the repository link to its **Code** page, where the files are listed.
3. Click **Code → Download ZIP** and wait. Do not download just one HTML file or use your browser's “Save page as” command.
4. Find the ZIP in Downloads, right-click, and choose **Extract All**.
5. Choose a writable local folder, such as SeeedTools in your Windows user folder. Avoid running inside the ZIP, read-only locations, and shared or synchronized directories.
6. Open the extracted subfolder until **Start Assistant.cmd, Stop Assistant.cmd, index.html, backend, data, and tools** appear together. A folder name ending in main is normal.
7. Keep the entire folder together. Moving just the launcher or index.html breaks the installation.

See also [GitHub's illustrated download guide](https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives).

### Step 3: install Python once

If supported Python is already installed, try the next step. Otherwise:

1. Visit the [official Python Windows download page](https://www.python.org/downloads/windows/). Choose a **3.13.x or 3.12.x Windows installer (64-bit)**, not another version, 32-bit, ARM64, or the embeddable package.
2. Run it. In the traditional installer, select **Add python.exe to PATH**, then **Install Now**.
3. Wait for completion. If company policy blocks installation, give these requirements to IT; do not disable security software.
4. Optional check: search the Start menu for cmd, open Command Prompt, enter either command below, and press Enter. Expect Python 3.12.x or 3.13.x. Opening Microsoft Store alone does not mean installation succeeded.

~~~text
python --version
py -3 --version
~~~

See [Python's illustrated Windows instructions](https://docs.python.org/3.13/using/windows.html). Close older command windows before retrying startup.

### Step 4: start and check the application

1. Double-click **Start Assistant.cmd**. The Chinese **启动助手.cmd** does the same thing.
2. Wait for checks. The browser normally opens automatically. Otherwise, manually open the URL shown by the launcher/diagnostics.
3. The default address is http://127.0.0.1:8765/. If the port is busy, use the actual address reported.
4. Look for **Favorites**, **Customization**, and the AI button at the bottom right.
5. Search **100025879**, inspect reComputer R1014-10, open **In the box**, and follow a source link.
6. Favorite a product and refresh. If it remains saved, you can begin daily work.

**127.0.0.1 means this computer.** Sending this URL to colleagues does not give them access to your copy: they must download and start their own installation. An address beginning with file:/// is only the read-only preview.

For daily use, return to the same folder and double-click the launcher. Closing a browser tab does not necessarily stop the service. To fully stop it, use **Stop Assistant.cmd** from that installation. Let active updates finish first.

### Step 5: try a customer request

For a customer asking about R1100 with EU868:

1. Search R1100 in **Product finder**. Confirm the exact SKU, model, and regional variant. A **SKU** is a product identifier.
2. Open **Specifications** and **In the box** separately to distinguish attributes from included items.
3. Search EU868 in **Accessories & customization**. Check interfaces, compatibility, and evidence; a recommended accessory is not necessarily bundled.
4. Star candidate products.
5. In **Customization**, create a request with a title, description, labels, and eligible products. Obtain evidence or explicit local confirmation for unconfirmed customization eligibility.
6. Before quoting, verify current price, currency, stock, and customization charges through the official product page/sales channel. Historical records and AI answers do not replace quotation checks.

### Step 6: configure AI only when needed

1. Confirm basic lookup first. AI is optional.
2. Open **Developer → Language & AI**, then choose DeepSeek or Doubao.
3. Enable **API access** on the chosen provider's official platform, obtain your own API key, and confirm credit and model access. An ordinary chat subscription may not include API usage.
4. Enter the key and a model name/model ID available to your account. Save, open the chat button, and test with a question containing no customer information.
5. The provider determines model availability; a prefilled model is only a default. Check provider, model ID, balance, network, and key if requests fail.

An API key is a credential: keep it out of GitHub, README files, and screenshots. Sending messages sends your question and relevant context to the selected provider and may incur charges. Check company policy before sending customer information, and verify answers against cited evidence.

### Step 7: update, back up, and share

| Task | Action |
| --- | --- |
| Update product data or replace images | Finish work, stop the assistant, run **Prepare Data Tools.cmd**, and wait for dependency installation/startup. Then use **Developer → Catalog updates**. Preparing dependencies requires access to a Python package source. |
| Update application code | Download a new ZIP, extract to a new folder, and follow the migration reference below. A download does not automatically replace an old installation. |
| Back up favorites, requests, and chats | Stop the app, then copy **.local-workbench** to an approved private backup location. Enable File Explorer **View → Show → Hidden items** if needed. |
| Help a colleague install | Share this repository link. While private, the owner must invite them through **Settings → Collaborators**; they must accept before downloading. Do not distribute your personal data folder. |
| Move to another PC | Preserve backups and original internal reference files; follow migration instructions below. Enter your AI key again on a new PC or Windows account. |

This repository contains application files and bundled product data. Personal .local-workbench files, virtual environments, keys, and logs are excluded by .gitignore. **GitHub is not an automatic backup of personal workbench records.**

### Common installation problems

| Symptom | First action |
| --- | --- |
| Repository/ZIP link returns 404 | Use this guide's repository URL and check that the full address was copied. Public downloads do not require sign-in or an invitation. |
| Window closes or only says “Press any key” | Run **Start Diagnostics.cmd** and inspect startup-diagnostic.txt. Give the maintainer an error report without credentials. |
| Python is missing | Install supported 64-bit 3.12/3.13 and retry in a fresh window; newer is not automatically compatible. |
| Only a heading appears, loading fails, or images are missing | Download/extract the complete ZIP, preserve data/backend/tools, and use the launcher. |
| Favorites or customization are missing | Close the directly opened index.html and use the launcher's URL. |
| Lookup works but AI fails | Basic setup may already be successful; troubleshoot provider access and AI settings separately. |
| You want one public URL for multiple users | This is a local workbench. Multiuser server deployment requires separate access control, data isolation, and hosting design; this guide does not provide that workflow. |

## Detailed feature and maintenance reference

The following sections preserve detailed features, historical catalogue audits, internal material handling, backups, and maintainer instructions. New users can finish the seven steps above first.

**Catalogue version note (2026-11-19):** this catalogue contains **4,534 product records**. The 4,521 SKUs and image counts in the 2026-11-09 review below describe a historical snapshot, not a complete audit of the current catalogue. The existing tools/verify.cjs checker fails where historical image counts are compared with the current total. This upload preserves the supplied catalogue; a new full audit has not been performed.

---

[简体中文](README.zh-CN.md)

A local Windows workbench for Seeed project managers. Start with a customer’s SKU, model or application requirement. Compare products from the **international Seeed Studio store**, check what ships in the box, find regional accessory SKUs and collect customization requests. The included catalogue works without an AI key.

**Sharing the catalogue with a colleague?** Send the full ZIP download link. On their Windows PC, they can download the ZIP, right-click **Extract All**, and open **`index.html`** beside the extracted `data` folder. No Python is needed to see J4012 on the first screen or search `100025879` for R1014-10. A GitHub address containing `/blob/` shows source code. `127.0.0.1` points to the recipient’s own PC and works after they start their local workbench. [Download the full ZIP](https://github.com/JasmineAmors/Seeed-L1-customized-Assistant/archive/refs/heads/main.zip)

**Looking for Favorites?** If the browser address starts with `file:///` and ends in `index.html`, you opened the read-only catalogue. To use the full workbench, extract the whole ZIP, return to the folder containing `index.html`, and double-click **`Start Assistant.cmd`** (or `启动助手.cmd`). Follow the setup steps below on a new PC. Use the browser address opened by that launcher. The full workbench shows **Favorites** and **Customization** on the left, **Developer** at the bottom left and the **AI chat** button at the bottom right. If the service is already running on the default port, you can go straight to your favorites. [Open Favorites on this PC](http://127.0.0.1:8765/#favorites)

## First-time setup on Windows

1. **Check your PC and Python.** Use Windows 10 or 11 on an x64 PC and a browser. Open the Start menu, type `cmd`, select **Command Prompt**, then run `py -3 --version` or `python --version`. If you already have **64-bit CPython 3.12 or 3.13**, skip installation and go to step 2. Otherwise ask IT to install it. On a self-managed PC, download a 3.13.x **Windows installer (64-bit)** from Python.org. On the traditional installer’s first screen, select **Add python.exe to PATH**, then **Install Now**. Open a fresh Command Prompt and repeat the version check. If the only result is the Microsoft Store, contact IT. [Python for Windows](https://www.python.org/downloads/windows/) · [Python installation guide](https://docs.python.org/3.13/using/windows.html)
2. **Download the project ZIP (about 100 MB).** Use the direct download below, or open the repository and select **Code → Download ZIP** above the file list. Wait for the download to finish. If your company network blocks GitHub, ask IT for the ZIP through an approved channel. The ZIP workflow requires no Git, Node.js or Codex installation. [Download the latest ZIP](https://github.com/JasmineAmors/Seeed-L1-customized-Assistant/archive/refs/heads/main.zip) · [Project repository](https://github.com/JasmineAmors/Seeed-L1-customized-Assistant) · [GitHub download instructions](https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives)
3. **Extract the whole ZIP.** In File Explorer, right-click the ZIP and select **Extract All…**. Choose a writable folder owned by your Windows account, outside cloud sync and shared drives. For example, type `%USERPROFILE%` into the File Explorer address bar, create a `SeeedTools` folder there, then browse to it in the extraction dialog. Open the extracted subfolder containing `Start Assistant.cmd`, `index.html` and `data`. Keep that folder together. [Microsoft’s extraction guide](https://support.microsoft.com/en-us/windows/experience/storage-filemanagement/zip-and-unzip-files)
4. **Double-click `Start Assistant.cmd`.** The Chinese launcher `启动助手.cmd` opens the same workbench. With Python installed, catalogue lookup, favorites, projects and AI settings start without downloading additional packages. Bookmark the address the launcher opens. The default is `http://127.0.0.1:8765/`. If the default port is busy, the launcher can select a free local port. This address serves only your own PC. [Open the default local address](http://127.0.0.1:8765/)

**Before your first store update or image replacement**, finish current work, run `Stop Assistant.cmd`, then double-click `Prepare Data Tools.cmd` (`准备更新工具.cmd`). It installs the pinned Pillow 12.3.0 and lxml 6.1.3 in this project's private `.venv` and starts the workbench. Only this preparation needs access to an approved Python package source. Rerun it if interrupted. A complete environment can be reused offline. Existing pip settings for company mirrors, proxies and certificates are respected.

**If the window only says “Press any key” or the browser does not open**, run `Start Diagnostics.cmd` (`启动诊断.cmd`) and read the last numbered message. Share `startup-diagnostic.txt` from the same folder with support. It contains startup stages, the Python version and safe error codes. When the service is ready, you can also open the printed URL manually.

**Check your installation.** Search for `100025879`. The first card should be **reComputer R1014-10**, with **2 GB RAM and 16 GB eMMC**. Open **In the box** and follow the source beside the five 120 Ω termination resistors. You can inspect the catalogue offline after setup. Opening an official source, checking the store for updates or sending an AI message requires a connection. [Open the sample on the default port](http://127.0.0.1:8765/#product=100025879&tab=parts)

To finish for the day, close the browser tab. To stop the local service, double-click `Stop Assistant.cmd` in the installation you started. It checks that the service belongs to this copy and leaves active work running. If it reports a busy operation, let it finish and run Stop again. Opening `index.html` directly provides a read-only catalogue. Use the launcher for saved work, updates and conversations.

## Use it for a customer request

| Your task | In the workbench |
| --- | --- |
| Identify a product or suggest an alternative | In **Product finder**, enter a SKU, model or need such as `J4012, need Super mode`. A specified product stays on the first card. A family name can show a representative configuration. Check the SKU and the stated reason for each alternative. The search rules are available beneath the search box. |
| Prepare a quotation | Open the full store URL at the top of the card. Read the listing currency, price or range and snapshot date. Confirm the current price, stock, quantity pricing and any customization charges with the relevant sales channel before quoting. A blank price means the workbench has no usable figure. |
| Check package contents and expansion | Open **In the box** for bundled items. **Accessories & customization** lets you filter extensions, exclusions and services together by name, interface, band or SKU. Both `wifi` and `Wi-Fi` match, as do `power adapter` and `电源适配器`. Try `R1100 with EU868` and compare SPI module `114993268` with USB module `114992628`. Expand **Also Add offers from the store** to check the original suggestions. |
| Revisit a page | The **Back** and **Forward** controls at the top recall up to five steps in either direction, including searches, filters and product tabs. |
| Track items and a custom request | Use the star on a product card. The sidebar favorites list starts collapsed. Select the arrow to open it. In **Customization**, create a project with a title, requirements, labels and one or more eligible SKUs. Eligibility comes from applicable manufacturer evidence or an explicit local confirmation. |
| Edit a local record or change language | Open **Developer → Product editor** to add a SKU, correct details or replace the main image. Local edits keep priority after a store refresh. For English or Simplified Chinese, use **Developer → Language & AI**. Product names, quoted source text and your own entries keep their original language. |

## Import your company reference material

In the full workbench, open **Developer → Internal reference**, enter a local folder and select **Import**. Supported sources are Markdown knowledge files, DOCX change notices, XLSX product lists and Markdown manuals inside ZIP archives. Imported records stay in this installation’s `.local-workbench/internal-knowledge.json`. Keep the original source folder. Refreshing the page or updating the public catalogue reapplies the SKU matches. Changed source files are reread, while failed sources retain their last successfully imported records and show an error.

Records include the source filename, line or spreadsheet location, file version and import time. Search by SKU, product name or rule. Spreadsheet imports retain identifiers, names, categories and explicit EOL markers. Cost, profit and price columns are omitted. Conflicting names keep their respective source versions. Struck-through names and SKUs indicate an internal EOL notice. Details and existing projects remain available, and project managers can assess new requests against remaining stock.

Product specifications and accessories show internal notes for the exact SKU. Typing an SSD upgrade request in a project displays locally matched drive dimensions, replacement actions and unresolved configuration questions. Unknown models or replacement SKUs remain unconfirmed. Imports, matching and SSD checks run locally. Sending an AI message explicitly sends a small set of relevant internal excerpts to the configured provider, with the resulting references labelled **Internal reference**.

Share the repository ZIP with authorized users to distribute the application. Transfer internal source material and personal workbench records through your company’s approved process. When moving PCs, back up `internal-knowledge.json` and the source folder, then select the new source path. The HTML-only preview uses the public catalogue distributed with the application.

## Optional AI conversations

In **Developer → Language & AI**, choose DeepSeek or Doubao, supply a model your provider account can access, and enter your own API key. Open the floating chat button at the bottom right. You can start a conversation, switch among saved conversations and follow sources in an answer.

**Sending a message contacts the selected external provider** and may incur charges on that account. Before sending, check the context shown above the chat. A request can include your question, selected product evidence, local product edits, relevant page or filter information, and up to six earlier turns. On a selected customization project it can also include relevant project details and up to 1,000 characters of the current unsaved draft description. Use customer information approved for that provider. Opening the panel, browsing history or switching products reads local data.

Answers identify official sources, local records and project or page context where available. Check those references before making a customer commitment. Completed turns and citations are stored on this PC.

## Update the store catalogue

1. Go to **Developer → Catalog updates → Check for changes**. Review new and changed records and their old and new values.
2. Apply selected differences or refresh specific SKUs or a category. **Run full refresh** requests the whole catalogue and can take considerably longer. Earlier records that disappear from a search are retained for review.
3. Watch the progress and the two dates. **Last store check** records a successful check. **Last successful catalog write** records when product data was applied. If the store rate-limits requests, wait until **Resume after**, then use **Resume job**. The previous catalogue remains available while work is staged.

Updates depend on the public store’s page layouts, search interface and available documents. A changed page may leave fields pending. Recheck manufacturer links and PDF pages when a manual changes.


## Back up

| What to keep | Location inside the extracted folder |
| --- | --- |
| Official catalogue and deduplicated main images | `data/catalog.js` and `data/jpg/` |
| Local settings, favorites, projects and product edits | `.local-workbench/workbench.json` |
| Locally supplied product images | `.local-workbench/user-images/` |
| Completed conversations and citations | `.local-workbench/chats.sqlite3` |

**For a private backup**, finish running tasks, run `Stop Assistant.cmd`, and copy `.local-workbench` to an approved private backup location. To preserve your exact catalogue as well, copy `data` with it. The backup can contain customer requirements, chats and encrypted credential material. Give colleagues the repository ZIP for installation and keep your personal backup out of shared archives and GitHub.


## If something goes wrong

| Symptom | What to do |
| --- | --- |
| The console displays `Install 64-bit Python 3.12 or 3.13`, then closes on a keypress | The launcher could not find a supported Python. Follow step 1 or ask IT to check the version and architecture. Close the old window, then double-click `Start Assistant.cmd` again. For a custom installation path, ask IT to add it to PATH. You can open `index.html` to browse products in the meantime. |
| Opening the HTML shows only a heading or never gets past “Loading” | A standalone HTML file is missing the catalogue and scripts. Right-click the full ZIP → **Extract All**, then use Edge or Chrome to open `index.html` alongside `data` and `search.js` in the extracted folder. If the browser says JavaScript is disabled, contact IT. |
| Package downloads fail, the directory is unwritable or a company policy blocks startup | Extract the full package into a writable local folder. Give IT the exact launcher message and ask them to verify package access or device policy. Omit customer data and keys from screenshots. |
| The browser does not open, the port is occupied, or the wrong copy appears | If the launcher says it is ready, open the local address it reports. For a previous installation, run **its own** `Stop Assistant.cmd`, then start the intended copy. If a port error persists, contact IT. |


The catalogue uses public material from the Seeed international store and Seeed Studio Wiki.