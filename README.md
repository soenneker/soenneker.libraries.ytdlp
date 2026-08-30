[![](https://img.shields.io/nuget/v/soenneker.libraries.ytdlp.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ytdlp/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ytdlp/build-and-test.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ytdlp/actions/workflows/build-and-test.yml)
[![](https://img.shields.io/nuget/dt/soenneker.libraries.ytdlp.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ytdlp/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ytdlp/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ytdlp/actions/workflows/codeql.yml)

# Soenneker.Libraries.ytdlp

The yt-dlp Windows executable packaged as a .NET content asset.

## Install

```bash
dotnet add package Soenneker.Libraries.ytdlp
```

The package copies the executable beneath the application output directory:

```csharp
string ytdlp = Path.Combine(AppContext.BaseDirectory, "Resources", "yt-dlp.exe");

var startInfo = new ProcessStartInfo(ytdlp)
{
    RedirectStandardOutput = true,
    RedirectStandardError = true,
    UseShellExecute = false
};

startInfo.ArgumentList.Add("--dump-single-json");
startInfo.ArgumentList.Add("--no-download");
startInfo.ArgumentList.Add(mediaUrl);
```

Drain both redirected streams, wait for completion, and reject a non-zero exit code. Pass URLs, output templates, cookie paths, and other variable values through `ArgumentList`; never include cookies or credentials in logs.

FFmpeg is required for many merge and post-processing operations and is not supplied by this package. Applications are responsible for setting time, output-size, and disk-space limits and for complying with the media provider's terms and applicable law.
