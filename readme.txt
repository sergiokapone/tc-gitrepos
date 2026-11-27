GitRepos 1.1 - git repositories in Total Commander (file system + Lister plugin, 32 and 64 bit)
==============================================================================================

GitRepos shows all your git repositories as one virtual folder in Network Neighborhood
("Git repositories"): their state at a glance, branches, tags, GitHub releases, commits
and uncommitted changes, an overview of each repository, plus a window to commit, pull
and push. The same DLL is also a Lister plugin that shows .patch / .diff files in colour.

INSTALLATION
  Open GitRepos-1.1.zip in Total Commander and confirm. Then: Network Neighborhood
  (\\\ in the command line) -> "Git repositories".
  Recommended: also open GitRepos-Lister-1.1.zip and confirm (the patch viewer). If another
  viewer takes .patch files first, move GitRepos up in Configuration > Options > Plugins >
  Lister plugins > Configure.
  Needs Git for Windows (git.exe in PATH, or Git= in the ini). Optional: the GitHub CLI
  logged in ("gh auth login") for private releases and more GitHub requests per hour.

THE ROOT
  - Every git repository under <drive of Total Commander>\Projects (5 levels deep) is a folder.
    Other places: Roots= (several folders) and Repos= (single repositories) in GitRepos.ini.
  - Icons: clean / uncommitted changes / commits not pushed.
  - Columns: Branch, Status ("clean", "2 modified 1 new", up/down arrows = to push/pull),
    Commit, Subject (last commit), Author, Remote (origin URL), Path.
  - States are read in the background, several repositories at once.

INSIDE A REPOSITORY
  Branches        local and remote branches; current one marked; ahead/behind; Enter = its files
  Tags            all tags; Enter = the files of that tag (nothing is checked out)
  Releases        GitHub releases: assets (F5 downloads), "Release notes.md", "Source code.zip"
  Commits         the last 300 commits; Enter/F3 = the patch, F5 = save as .patch
  Changes         uncommitted files; F3 = the diff, Enter = the commit window
  -> Working folder        Enter goes to the real folder
  Commit and Push...       Enter opens the commit window; F3 = git status
  (i) Overview             F3/Enter: state, history, activity per week, authors, file types,
                           most changed files, recent commits (the root has one for all
                           repositories: which need attention, all by last commit)

  Names show "/" as U+2215 and ":" as U+A789 (Windows does not allow them in file names).

COMMIT AND PUSH WINDOW (theme and language of Total Commander)
  - Changed files with check boxes: checked = in the next commit (git add / git restore --staged).
  - Coloured diff of the selected file.
  - Commit message, Commit (Ctrl+Enter), Commit + Push.
  - Fetch, Pull (fast-forward only, never creates a merge), Push (sets the upstream of a new branch).
  - Right click on a file: open, show in folder, copy path, check/uncheck all, add to .gitignore.
  - Esc closes, F5 refreshes. Nothing is ever deleted or reverted.

PATCH VIEWER (Lister plugin: .patch, .diff, .rej and the overviews)
  - A card per commit (subject, author, dates, hash, message) and a table of its files with
    +added -removed and a bar; click a row to jump to the file.
  - Every file with a banner (status, rename, mode); hunks with old/new line numbers; added
    and removed lines tinted, the changed words inside a line marked.
  - ] / [ next / previous file, L line numbers, W wrap, Ctrl+C, Ctrl+A, F7 search.

KEYS
  Alt+Enter   open the item on GitHub (repository, branch, file, commit, release);
              without GitHub: go to the working folder
  Ctrl+R      root: look for repositories again; a repository: re-read it; Releases: ask GitHub again
  F3 / F5     view / copy out files of branches, tags and releases

SETTINGS  (copy GitRepos.ini.example to GitRepos.ini next to the plugin; all keys optional)
  Roots, Depth, Repos, ImportGitview (repositories of the gitview plugin's gitview.json),
  Git, Token, UseGhToken, Commits, Releases, SourceZip, DefaultColumns, Threads, Overview, Theme,
  Language; [View] LineNumbers, Wrap, FontSize for the patch viewer (its ini is the one next to
  GitRepos.wlx64).
  Every key is explained in GitRepos.ini.example.

SAFETY AND PRIVACY
  - Browsing never writes to a repository (git status runs with --no-optional-locks).
  - Network: api.github.com (release lists), github.com / codeload.github.com (downloads you
    ask for), and whatever git fetch/pull/push contacts. No telemetry, no update checks.
  - The GitHub token (from Token= or "gh auth token") is kept in memory only and is sent
    only to api.github.com.

LIMITS
  Releases: GitHub only. A repository nested inside another one is not found by the scan
  (add it to Repos=). Commits shows the current branch. Git LFS files appear as pointers.

Full description with screenshots: https://github.com/sergiokapone/tc-gitrepos
Freeware, see LICENSE.txt.

SUPPORT
  GitRepos is free. If it saves you time, you can support the work:
  https://send.monobank.ua/jar/7EiyaxfeWZ  (or the Sponsor button on the GitHub page). Thank you!
