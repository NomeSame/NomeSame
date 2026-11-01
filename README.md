# Hi 👋 I'm NomeSame

I build Android apps and Python research tools around things I want to use, from a local music library to document editing and chess analysis.

My projects are built with AI-assisted development. I shape the product, direct the implementation, and take responsibility for checking the result. Much of that work happens after the first working version, when a document loses its formatting, an engine fails to restart, or a promising backtest stops looking promising under a fair comparison.

## What I'm building

### [Music Monster](https://github.com/NomeSame/MusicMonster)

A local Android audio and video player built with Kotlin, Jetpack Compose, and Media3. It includes playlists, fuzzy title search, an equalizer, a sleep timer, and video picture-in-picture. The public app needs no account and declares no internet permission.

Playback checkpoints are tested against abrupt loss of a separate probe process. In a controlled 2,000-file test, the public player displayed its first list after 1.187 seconds while media-duration parsing was blocked. Release scroll performance still needs measurement.

[Download v1.4.0](https://github.com/NomeSame/MusicMonster-Release)

### [Read & Convert](https://github.com/NomeSame/MarkdownViewer-Releases)

An Android document app for viewing, editing, and converting text, Markdown, HTML, CSV, PDF, DOCX, and XLSX, with capabilities that vary by format. Its DOCX editor saves a separate copy, and PDF-to-DOCX conversion reconstructs editable headings, lists, and paragraphs where the source allows it, with a page-based fallback for harder layouts.

One real document exposed an image-cache problem because 38 image parts contained only four distinct images. Content-based deduplication and device regression tests now cover that case. Version 1.3.0 is published, while dictation remains experimental and complex conversions can lose formatting.

### [Chess Analysis](https://github.com/NomeSame/chess-analysis-android)

An Android chess app with Stockfish 18 through C++ and JNI, saved games, review and reanalysis, PGN/FEN import, and optional local coaching through llama.cpp with separately supplied models.

A native restart bug came down to duplicate shutdown commands and stale UCI queues. The fix is checked through repeated engine restarts in one process. Version 1.0.0 is published. Move classification remains experimental and hasn't been validated on an independent hold-out set.

### [LocalChat](https://github.com/NomeSame/LocalChat-Release)

An Android chat app running language models on the device through LiteRT-LM, with streaming, background generation, and a file agent offering eight tools. The agent works on copies, keeps up to five snapshots, and supports planning, confirmation, and automatic execution modes.

Security tests reproduced nine issues, including a file-access boundary failure and CSV formula injection, which were then corrected. The current signed, minified build still needs device acceptance, and the privacy wording needs to be reconciled with Android backup settings.

## Research that changed my mind

My Python trading work includes an Elliott-wave analyzer, a shared signal-validation harness, and a Hyperliquid execution system. I compare signals with matched random baselines, separate selection from out-of-sample checks, and account for fees and slippage.

The Elliott-wave project's headline hit rate lost its apparent advantage once zone width and distance were controlled. A separate strategy study found a gross edge below trading costs, so that candidate was rejected and the executor remained paused. The ensemble's aggregation layer is still unbuilt, and the Elliott-wave review records unresolved geometry and adapter failures. These are research projects with no demonstrated robust trading edge.

## A few dated checks

These are documented successful runs, with local and Android device checks kept separate.

| Project | Local checks | Android checks |
| --- | --- | --- |
| Music Monster | 743 executions on 27 Oct 2026 | 130 tests on API 33 on 24 Oct 2026 |
| Read & Convert | 632 JVM tests on 21 Oct 2026 | 260 tests on API 33, followed by 28 targeted checks after the final scan fix |
| Chess Analysis | 252 JVM/Robolectric tests on 7 Oct 2026 | 12 tests in an isolated debug app on Android 13 |
| LocalChat | 427 JVM tests on 7 Oct 2026 | Current signed release awaiting device acceptance |

The runs cover different builds and scopes, so they aren't a combined coverage figure or a claim that every current release passed the same suite.

I work mainly around Kotlin, Java, and Python, and keep learning through the problems these projects uncover.

You can reach me at [nomesame@proton.me](mailto:nomesame@proton.me). I'm based in Brazil and open to collaboration and small product work.

<sub>Project overview updated on 1 November 2026. Android reviews run through October and November, while the trading research reflects the documented August review.</sub>
