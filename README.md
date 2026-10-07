# C# Syntax Tester — GitHub Pages edition

A browser-only C# syntax checker intended for assessment use.

## What it does

- Uses the official Roslyn C# parser (`Microsoft.CodeAnalysis.CSharp`) in Blazor WebAssembly.
- Checks C# syntax locally in the student's browser.
- Returns only one of the following outcomes:
  - `Syntax OK.`
  - `Syntax error detected. Review your code and try again.`
- Does **not** show compiler codes, line numbers, locations, or suggested fixes.
- Does **not** execute student code.
- Does **not** send student code to a server.
- Does **not** provide IntelliSense, autocomplete, hover help, or AI assistance.

## Important limitation

This is a **syntax parser**, not a full compiler. Code can be syntactically valid but still fail compilation for semantic reasons.

For example, this is syntactically valid C# even though it has a type error:

```csharp
int x = "hello";
```

The syntax checker will report `Syntax OK.` because the C# grammar is valid.

## Deploy to GitHub Pages

1. Upload this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Push/commit to `main`.
5. Open **Actions** and wait for **Deploy GitHub Pages** to finish with a green check mark.
6. Open **Settings → Pages** to find the public site URL.

No API URL, Docker server, VPS, secrets, or paid hosting are required.

## Replacing the earlier Runner project

If you are replacing the previous `csharp-console-runner` repository, delete the old `backend`, `deploy`, `frontend`, `compose.yml`, and old project files, then upload the contents of this repository at the repository root. Keep only this version's `.github`, `Pages`, `wwwroot`, and root project files.
