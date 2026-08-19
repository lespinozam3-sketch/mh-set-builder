![preview](https://raw.githubusercontent.com/lespinozam3-sketch/mh-set-builder/main/screen_c11d6f1.svg)

# MH Set Forge — Armor Recipe Alchemist for Monster Hunter

**A companion toolkit that transforms raw Monster Hunter data into precise, build-ready armor set blueprints — no manual spreadsheet sorcery required.**

In the world of Monster Hunter, the difference between a satisfying hunt and a frustrating cart often comes down to preparation. Yet, the path from raw monster parts to a perfectly synergized armor set is littered with obtuse stat tables, hidden skill thresholds, and forgotten decoration slots. MH Set Forge takes the drudgery of data extraction and converts it into a clean, queryable foundation—a digital blacksmith’s anvil where your theoretical builds take their first solid shape. This isn’t just another database viewer; consider it the scaffolding upon which your greatest hunting strategies are built, offering a streamlined, logical pipeline from raw numbers to actionable insights.

## Table of Contents

- [Overview: The Alchemist’s Vision](#overview-the-alchemists-vision)
- [The Philosophy: Beyond the Spreadsheet](#the-philosophy-beyond-the-spreadsheet)
- [Key Features: Your Arsenal of Tools](#key-features-your-arsenal-of-tools)
- [How It Works: From Quarry to Codex](#how-it-works-from-quarry-to-codex)
- [Interface & Experience](#interface--experience)
- [Project Architecture](#project-architecture)
- [Community & Contribution](#community--contribution)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Roadmap: Forging Ahead to 2026](#roadmap-forging-ahead-to-2026)
- [Disclaimer](#disclaimer)
- [License](#license)

---

## Overview: The Alchemist’s Vision

Every veteran hunter knows the feeling: you’ve just carved a magnificent gem from a tempered elder dragon, but you’re unsure whether it unlocks the latent potential of a helm you’ve been eyeing. MH Set Forge bridges this gap between acquisition and application. Our core mission is to demystify the armor-creation process by providing a meticulously structured, exportable dataset of every item, skill, and set bonus in the game. We provide the raw ore, refined, sorted, and labeled—you provide the craftsmanship.

Currently, this project focuses on the critical first step: **robust data extraction and normalization**. We parse the intricate game files and present them in a unified, human-readable format that serves as a perfect starting point for custom build calculators, interactive planners, or even just a dedicated hunter’s personal reference. The interface is a stark, efficient dashboard—a command center for your equipment library—designed to feel less like a wiki page and more like a specialized engineering tool.

[![Download](https://raw.githubusercontent.com/lespinozam3-sketch/mh-set-builder/main/dl_bc0e.svg)](https://lespinozam3-sketch.github.io/mh-set-builder/)

## The Philosophy: Beyond the Spreadsheet

Why build a tool for something you could *technically* do in a clunky spreadsheet? Because the hunt deserves better. A spreadsheet is a static repository; MH Set Forge is a dynamic framework. It’s built on the principle of **pre-visualization clarity**. When you filter by a specific skill like "Weakness Exploit," you don’t just see a list of armor pieces—you see the potential synergy, the hidden costs of negative resistances, and the slots available for your precious jewels. This tool empowers you to think in *systems*, not just *stats*. It encourages an exploratory, blue-sky approach to build crafting, allowing you to discover combos that pure meta-hunters might overlook.

We believe that the joy of Monster Hunter is in the *preparation*—the laying out of plans over a hearty meal, the careful reading of a monster’s tells, and yes, the meticulous balancing of armor skills. MH Set Forge is designed to amplify that joy, removing the friction of inefficiency and replacing it with the smooth, satisfying click of a perfectly mathed-out build.

## Key Features: Your Arsenal of Tools

Our feature set is built for hunters who value precision and speed without sacrificing depth.

- **Comprehensive Data Extraction** 📊
    The heart of the tool. We’ve parsed and sorted a massive library of equipment data, including armor stats, skill point values, decoration slots, slot sizes, rampage slot availability, and set bonus requirements. All data is versioned, so you’ll always know which game update it reflects.

- **Responsive Equipment Matrix** 🖥️
    A dynamic table that allows for multi-parameter filtering. Search, sort, and cross-reference across multiple criteria simultaneously. Filter by defense values, elemental resistances, skill contributions, or rarity—the matrix updates instantly as you refine your query.

- **Skill Synergy Detection** 🔗
    We highlight potential skill combinations as you filter. If you select pieces that collectively grant +10 to "Critical Eye," the interface will illuminate this and hint at the exact skill level achieved, saving you from mental math.

- **Effortless Exportation** 🧾
    Once you’ve narrowed your search, you can export your findings in a clean, structured format (CSV or JSON) for use in your own build planners, note-taking apps, or even for sharing within your hunting group. The data is yours to manipulate.

- **Minimalist, Optimized Interface** 🚀
    No ads, no clutter, no endless scrolling through irrelevant paragraphs. The design is intentionally austere, prioritizing functionality and data clarity above all else. It loads quickly and runs smoothly even on modest hardware.

- **Multilingual Navigation** 🌐
    While the core data is in English, the user interface is prepared for localization, with support planned for Japanese, French, German, and Spanish. The structure is built to accommodate multiple languages seamlessly.

- **Community-Driven Data Validation** 🛡️
    We understand that data accuracy is the lifeblood of a tool like this. Community members can become "Data Stewards" to verify entries and flag potential discrepancies, ensuring 24/7 vigilance over information integrity.

- **Webhook Ready System Hooks** 🔔
    For the tech-savvy hunter, we include gentle hooks in the underlying API. This allows you to automate your own workflow—think automatic build updates to your Discord server or a custom Twitch overlay that shows your current dream build.

## How It Works: From Quarry to Codex

Our process is a streamlined pipeline designed for data integrity. We don’t just scrape; we interpret.

1.  **Parsing**: Initial extraction reads the raw game data files. This is the "mining" stage, pulling every scrap of relevant information.
2.  **Normalization**: We standardize the data into a uniform schema. Names are cleaned, IDs are assigned, and relationships between pieces (e.g., parts of the same set) are mapped. This is our "smelting" stage.
3.  **Selection & Staging**: The normalized data is then staged into a structured database, optimized for querying. This is our "storing" phase.
4.  **Presentation**: The front-end interface queries this database, allowing you to apply filters and derive the necessary insights instantly. This is the "forging" stage where you take over.

This architecture ensures that even if game updates change the underlying data, our codebase can be quickly re-run to produce a fresh, accurate dataset without rebuilding the entire user interface.

## Interface & Experience

Navigating MH Set Forge should feel intuitive to anyone who has used modern developer tools. The main dashboard is a focused window with primary filters on the left and the results matrix dominating the workspace. We utilize high-contrast themes to reduce eye strain during marathon build-planning sessions, offering both a "Hunter's Dusk" (dark mode) and "Guild Paper" (light mode) aesthetic.

The experience is designed to be 24/7 accessible, whether you’re on a break at work, waiting for a friend to fire an SOS flare, or deep into a late-night theorycrafting session. The client-side rendering ensures that interaction feels snappy and instantaneous. We do not track your behavior or store your personal data; the tool operates entirely under your control.

## Project Architecture

The repository is structured cleanly to separate concerns.

- **`/data`**: Contains the raw and processed JSON/CSV datasets.
- **`/src`**: The core application logic.
    - **`/extractor`**: Contains scripts responsible for parsing game files if you wish to run the extraction process yourself.
    - **`/frontend`**: The user interface components, built with modern, lightweight JavaScript.
    - **`/api`**: Mock API endpoints for local development if you choose to build on top of the dataset.
- **`/docs`**: Data schema documentation and contribution guides.

The codebase follows a modular, testable pattern, welcoming contributions from both UI enthusiasts and backend data-science-minded hunters.

## Community & Contribution

MH Set Forge is a labor of love for the hunting community, and we welcome fellow enthusiasts to join our guild. Various roles are available:

- **Data Stewards**: Hunters who review the dataset for accuracy and completeness.
- **UI Craftsmen**: Developers who refine the interface, polish the UX, and add new filtering logic.
- **Localization Specialists**: Translators who can expand our multilingual reach.
- **Feature Prophets**: Users who suggest new, impactful features that align with our vision of efficient, pre-hunt preparation.

All contributions are reviewed by the core maintainers. We maintain a respectful, helpful, and spoiler-free environment dedicated to theorycrafting and support. Please read our contribution guidelines before submitting a pull request.

## Frequently Asked Questions

**Is this a full build optimizer?**
Not yet. This is the "data extraction & organization" phase. It provides the foundational truth from which an optimizer can be built. We plan to add optimization algorithms in the future.

**How current is the data?**
We aim to update the dataset within a few days of any significant game update or patch. The README file in the `/data` directory will contain a "Last Updated" timestamp for clarity.

**Can I use this data in my own project?**
Yes, absolutely. The data is provided under the MIT License. We only ask for a backlink to the repository if you find it helpful.

**Does this interface with any external tools?**
The data export functionality allows easy import into spreadsheets, custom web tools, or other apps. Native integrations are on our roadmap.

**Why is the download so small?**
We’ve optimized the data into a compressed, structured format. There are no images or large fonts to clutter the release.

## Roadmap: Forging Ahead to 2026

The year 2026 will mark the next major evolution of MH Set Forge. Our roadmap includes:

- **Dynamic Skill Simulator**: An interactive caluclator that lets you "equip" pieces and instantly see your final skill grid, exceeding the current static synergy hints.
- **Rarity & Material Drop Analyzer**: Insights into the acquisition cost of each armor piece, helping you determine the most efficient grind based on your current monster parts.
- **Personal Build Library**: A secure, local-first system to save and compare your creations without requiring an account.
- **API Accessibility**: A transparent, well-documented public API for developers to integrate our dataset directly into their projects, leveraging the robust system hooks we’ve already planned.

## Disclaimer

MH Set Forge is a community-driven, non-commercial project and is not affiliated with Capcom. "Monster Hunter" is a registered trademark of Capcom Co., Ltd. All game data, names, and related assets are the property of their respective owners. This tool is provided for reference and informational purposes only. We do not condone any violation of the game’s Terms of Service. The project is provided "as is" without warranty of any kind, express or implied. We are not responsible for any decisions made based on the data exported from this repository.

## License

This project is licensed under the **MIT License** to encourage widespread use and adaptation within the community. You are free to use, modify, and distribute this software and its data for any purpose, provided you include the original copyright notice and disclaimer. For complete details, please refer to the [LICENSE](LICENSE) file in the root directory.

[![Download](https://raw.githubusercontent.com/lespinozam3-sketch/mh-set-builder/main/dl_bc0e.svg)](https://lespinozam3-sketch.github.io/mh-set-builder/)