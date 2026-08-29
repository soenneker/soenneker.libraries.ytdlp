[![](https://img.shields.io/nuget/v/soenneker.libraries.ytdlp.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ytdlp/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ytdlp/build-and-test.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ytdlp/actions/workflows/build-and-test.yml)
[![](https://img.shields.io/nuget/dt/soenneker.libraries.ytdlp.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ytdlp/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ytdlp/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ytdlp/actions/workflows/codeql.yml)

# Soenneker.Libraries.ytdlp

Simply adds the yt-dlp nightly Windows executable, updated daily (if available).

## Install

```bash
dotnet add package Soenneker.Libraries.ytdlp
```

## What it provides

- Simply adds the yt-dlp nightly Windows executable, updated daily (if available).
- The file is copied to the output directory, and located at the relative path: `Resources\yt-dlp.exe`.

## How to use it

After installation, resolve the packaged file from the output-relative path above. The package deploys the asset but does not invoke it for you.
