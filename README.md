# Dev-work-Report---Web-Systems-Architecture-Diagnostic-Pipeline

# Dev. Work Report

## Project: Web Systems Architecture & Diagnostic Pipeline (P2)

### Goal
Document technical errors, debugging strategies, repository organization, deployment workflow, and lessons learned during the development, execution, and troubleshooting of local web applications.

---

## STEP 1 — Repository and Local Server Configuration

### Problem
When attempting to execute the web application through the local development server (Live Server Extension), the browser was strictly redirected to the root directory interface (`http://127.0.0.1:5500/`), displaying either a completely blank page or an empty directory listing grid.

### Cause
The local workspace suffered from severe routing breaks due to the injection of invisible characters (`non-breaking spaces`) within the source code during copy-paste operations from external rich-text formats. This broke the syntax highlighter compiler inside VS Code (rendering text entirely white) and caused the Live Server engine to fail when mapping paths and parsing the Document Object Model (DOM) tree.

### Solution
Physically deleted the corrupted index file inside VS Code to eliminate bad references. Created a clean, native `index.html` file within the local directory path, manually sanitizing the structure to guarantee the absolute absence of hidden string characters. Restarted the Live Server instance, successfully coupling the application runtime route to `/exercicio_1/index.html`.

### Learning
* Impact of non-breaking spaces and hidden byte-characters on compiler tokenization.
* Local server routing behavior over local port systems (`5500`).
* Live Server file-mapping constraints when reading complex directory hierarchies.

### Improvement
* Standardize on copying raw unformatted code or utilizing specialized sanitization tools before script injection.
* Frequently audit code syntax highlighting states to instantly detect breaking lexical tokens.

---

## STEP 2 — OS File-System Mapping and Authentication

### Problem
Attempting to inspect or directly trigger the `index.html` file through the macOS native Finder file manager interface resulted in the Operating System forcing the file to open inside the TextEdit plain-text editor instead of an active web browser. Furthermore, the file asset was flagged with a persistent question mark `?` overlay icon.

### Cause
A global file extension mapping corruption occurred in the macOS file-system layer. The system configuration mapped the `.html` extension directly to the generic plain text handler app (`TextEdit`), treating structural HTML documents as raw, unformatted text files. The `?` system icon explicitly confirmed that the macOS tree metadata flagged the asset as unknown, untrusted, or physically corrupted regarding its declared extension parameters.

### Solution
Triggered the native macOS file metadata interface by selecting the asset and executing the **"Get Info"** command (`Cmd + I`). Navigated to the **"Open with"** controller sub-menu, selected **Google Chrome** (or the target system browser), and executed the **"Change All..."** system override instruction. This successfully rebuilt the extension mapping database across the OS partition.

### Learning
* Mechanics of Operating System file extension mapping registries.
* Permission tree integrity flags and standard diagnostic indicators (`?` system overlays) on Unix-based kernels.
* Decoupling editor workspace configurations from global system file execution paths.

### Improvement
* Enforce global OS system file-type assignments prior to setting up development sandbox environments.
* Use strict command-line utilities to query file mime-types if metadata markers display corrupted states.

---

## STEP 3 — Library and Asset Integration (jQuery Ecosystem)

### Problem
The metric prefix converter application required a responsive user interface layout with custom animated expansion routines, but early runtime executions failed to expand container spaces dynamically or manipulate values across power-of-10 scales.

### Cause
The application infrastructure requires external asset synchronization. Specifically, the implementation demands an absolute initial hidden rendering state inside the CSS document structure to allow jQuery's height calculations to map layout boundaries during initialization events.

### Solution
Separated the modular codebase into distinct, single-responsibility files (`index.html`, `style.css`, `script.js`). Injected a dedicated stylesheet instruction `#resultadoContainer { display: none; }` to force a non-rendered node boundary, enabling the jQuery engine listener (`$('#btnCalcular').on('click')`) to smoothly calculate the transition heights via `.slideDown(400)` upon user action.

### Learning
* Lifecycle mechanics of the jQuery initialization routine and DOM manipulation APIs.
* Layout calculation prerequisites for height-altering layout animations like `.slideDown()`.
* Modular architecture design requiring absolute physical isolation between design layout and behavioral layers.

### Improvement
* Standardize on creating layout target skeletons with zeroed display properties inside the stylesheet layer whenever dynamic visual expansions are required.

---

## STEP 4 — Form Component State and Selection Tracking

### Problem
The application needed to dynamically capture state parameters from user selections (radio buttons and text input areas) without suffering from execution context errors or mapping the wrong inputs into the business logic processor.

### Cause
Improper form encapsulation or lack of strict variable isolation causes selection pools to overlap. For instance, if `<input type="radio">` tags do not share an isolated scope or precise selector bindings, the execution thread cannot determine the checked status during interaction.

###
