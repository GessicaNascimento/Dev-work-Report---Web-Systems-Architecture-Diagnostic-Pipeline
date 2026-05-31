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

### Solution
Grouped selection components strictly inside explicit `<fieldset>` containers sharing unified `name="conversao"` attributes to force single-choice exclusivity at the browser engine level. Used precise runtime queries (`document.querySelector('input[name="conversao"]:checked').value`) coupled with native string cleanups (`.trim().toUpperCase()`) to capture form inputs perfectly before submitting them to logic evaluations.

### Learning
* Form grouping mechanisms inside the HTML5 DOM scope.
* Real-time target selection parsing via query selector filtering attributes (`:checked`).
* Input string hygiene processing methods to prevent human error during input collection.

### Improvement
* Implement string normalizers and hard name constraints on form structures to keep code resilient against varied human data entries.

---

## STEP 5 — Algorithmic Processing and Data Serialization Failures

### Problem
Complex logic branches (such as progressive salary updates or cross-unit thermodynamic conversions) faced value precision loss or failed to render outputs with the strict font, size, and styling metrics requested by project stakeholders.

### Cause
Data formatting pipelines frequently suffer from data-type mismatches, such as passing raw floating-point numbers into text blocks or failing to bind specific typographic classes to output blocks (`<span>`, `<div>`) after string processing loops.

### Solution
Configured precise type formatting rules by running target rounding operations (`.toFixed(2)`) and localized currency serializers (`.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })`). Bound these values to dedicated, pre-styled interface classes (such as `.texto-formatado`), instantly injecting results into target nodes while enforcing type safety and styling boundaries.

### Learning
* Floating-point precision management via native formatting APIs.
* Localized formatting pipelines for enterprise-ready internationalization presentation.
* Proper DOM node insertion techniques to preserve design definitions.

### Improvement
* Ensure output components are decoupled from calculations by establishing rigid presentation stylesheets before writing calculation scripts.

---

## Workflow Structure

The web applications engineering pipeline strictly follows this structural sequence:

[Data Ingestion / Input] ➡️ [Sanitization & Normalization] ➡️ [Algorithmic Processing] ➡️ [Dynamic DOM Injection & Style Rendering]


* **Data Ingestion / Input:** Captures raw input values, radio component states, and text strings from dedicated form fields.
* **Sanitization & Normalization:** Employs `.trim().toUpperCase()` logic routines to eliminate input whitespace anomalies and bypass case-sensitivity constraints.
* **Algorithmic Processing:** Runs computations through conditional matrices (`switch`, `if/else`) and power-of-10 conversions to establish base units.
* **Dynamic DOM Injection & Style Rendering:** Outputs the processed data directly into designated target blocks (`<span>`, `<div>`), activating real-time visual transitions.

---

## Technical Reflection

The debugging, refactoring, and local server deployment process reinforced:
* **Workflow Organization:** Separating logic, layout styles, and semantic files guarantees high maintenance scalability.
* **Troubleshooting Methodology:** Performing root cause analysis on operating system file maps and hidden byte strings accelerates structural problem resolution.
* **Repository Management:** Maintaining clean local work directories prevents cross-contamination of metadata.
* **Persistence During Technical Failures:** Debugging silent execution breaks builds critical resiliency when interacting with development server runtimes.
* **Adaptive Problem-Solving Strategies:** Developing fallback plans for unexpected system behaviors isolates software bugs from global hardware errors.

The project also improved understanding of:
* **Git Workflows & Version Control:** Version tracking helps isolate safe source branches from breaking environment modifications.
* **Authentication Systems:** Transitioning securely from open tokens to private SSH key configurations isolates workspace access vectors.
* **Data Processing Pipelines:** Implementing clean input validation routines prevents bad data states from breaking mathematical logic.
* **Debugging Logic:** Analyzing execution logs from browser devtools enables quick identification of silent failures.
* **Deployment Organization:** Packaging production-ready scripts separately from staging playgrounds optimizes asset load times across server hosts.

---

**Author:** Géssica Nascimento  
**Title:** Systems Analysis & Development Student  
**Date:** 28/05/2026











## Workflow Structure

The web applications engineering pipeline strictly follows this structural sequence:
