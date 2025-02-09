﻿## dotnet-format
<img width="480" alt="dotnet-format" src="https://user-images.githubusercontent.com/9797472/61659851-6bbdc880-ac7d-11e9-95f7-d30c7de1a18a.png">

[![Nuget](https://img.shields.io/nuget/v/dotnet-format.svg)](https://www.nuget.org/packages/dotnet-format)

|Branch| Windows (Debug)| Windows (Release)| Linux (Debug) | Linux (Release) | Localization (Debug) | Localization (Release) |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
[main](https://github.com/dotnet/format/tree/main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Windows&_configuration=debug&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Windows&_configuration=release&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Linux&_configuration=debug&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Linux&_configuration=release&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Linux_Spanish&_configuration=debug&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|[![Build Status](https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/format/dotnet.format?branchName=main&jobName=Linux_Spanish&_configuration=release&label=build)](https://dev.azure.com/dnceng/public/_build/latest?definitionId=347&branchName=main)|


`dotnet-format` is a code formatter for `dotnet` that applies style preferences to a project or solution. Preferences will be read from an `.editorconfig` file, if present, otherwise a default set of preferences will be used. At this time `dotnet-format` is able to format C# and Visual Basic projects with a subset of [supported .editorconfig options](./docs/Supported-.editorconfig-options.md).

### New in v5.0.211103

### New Features
- Can now apply codestyle codefixes automatically with `dotnet format --fix-style`
- Can now apply analyzer codefixes automatically with `dotnet format --fix-analyzers`

### Breaking Changes

Removed Deprecated options from 4.0:
- Removed `--dry-run` should use `--check` instead
- Removed `--files` should use `--include` instead
- Removed `--workspace` this option is now implied

#### Changes:
- [Isolate each Analyzer assembly into its own LoadContext. (959)](https://www.github.com/dotnet/format/pull/959)
- [Implement GetDocumentDiagnosticsAsync in CodeFix DiagnosticProvider (958)](https://www.github.com/dotnet/format/pull/958)
- [Fix missing ` in README.md (914)](https://www.github.com/dotnet/format/pull/914)
- [Add unit test for 3rd party fixer formatting (896)](https://www.github.com/dotnet/format/pull/896)
- [Add unit test for code style fixer formatting (893)](https://www.github.com/dotnet/format/pull/893)
- [Improve FixAll support by using equivalence key when available (884)](https://www.github.com/dotnet/format/pull/884)
- [Only run analyzers against specified project when workspace is a project (865)](https://www.github.com/dotnet/format/pull/865)
- [When matching all files don't rely on FileMatcher (864)](https://www.github.com/dotnet/format/pull/864)
- [Fix markdown formatting in example table (858)](https://www.github.com/dotnet/format/pull/858)
- [Add ability to read --{in,ex}clude value from stdin (790)](https://www.github.com/dotnet/format/pull/790)
- [Add test to ensure code containing <auto-generated> comment is treated as generated. (857)](https://www.github.com/dotnet/format/pull/857)
- [Fixes #834 : error reportfile without directory specified (842)](https://www.github.com/dotnet/format/pull/842)
- [Log there were warnings loading the workspace if diagnostics are reported (841)](https://www.github.com/dotnet/format/pull/841)
- [Fix CommandLine_AllArguments_Bind test (818)](https://www.github.com/dotnet/format/pull/818)
- [Fix Run argument names (817)](https://www.github.com/dotnet/format/pull/817)
- [Add option for whitespace formatting (774)](https://www.github.com/dotnet/format/pull/774)
- [Load analyzer assemlbies in their own AssemblyLoadContext (746)](https://www.github.com/dotnet/format/pull/746)
- [Check that file exists before considering it for formatting (775)](https://www.github.com/dotnet/format/pull/775)
- [Report formatted files and counts based based on reported issues. (776)](https://www.github.com/dotnet/format/pull/776)
- [Support generated_code editorconfig setting (780)](https://www.github.com/dotnet/format/pull/780)
- [Create integrations.md (777)](https://www.github.com/dotnet/format/pull/777)
- [Fix warnings and apply suggestions. (767)](https://www.github.com/dotnet/format/pull/767)
- [Improve folder workspace performance (763)](https://www.github.com/dotnet/format/pull/763)
- [Improve folder performance (760)](https://www.github.com/dotnet/format/pull/760)
- [Update --include and --exclude documentation (761)](https://www.github.com/dotnet/format/pull/761)
- [Remove aliases for the fix style and fix analyzers options (753)](https://www.github.com/dotnet/format/pull/753)
- [Run analyzers during integration tests (728)](https://www.github.com/dotnet/format/pull/728)
- [Remove unnecessary imports (749)](https://www.github.com/dotnet/format/pull/749)
- [Only include compiler diagnostics if a fixer supports them (750)](https://www.github.com/dotnet/format/pull/750)
- [Added CodeFormatter tests for `--fix-style` (751)](https://www.github.com/dotnet/format/pull/751)
- [Format one solution per repo during integration tests (739)](https://www.github.com/dotnet/format/pull/739)
- [Filter analyzers by project language before running (725)](https://www.github.com/dotnet/format/pull/725)
- [Run all analyzers even when a fixer isn't present (723)](https://www.github.com/dotnet/format/pull/723)
- [Update documentation for analyzers (722)](https://www.github.com/dotnet/format/pull/722)
- [Add devcontainer to better support Codespaces (721)](https://www.github.com/dotnet/format/pull/721)
- [Add validation when specifying --folder and analyzers (715)](https://www.github.com/dotnet/format/pull/715)
- [Merge in Feature/analyzers (713)](https://www.github.com/dotnet/format/pull/713)
- [Remove deprecated options and aliases (710)](https://www.github.com/dotnet/format/pull/710)
- [Added reflection based discovery of analyzers and fixes (698)](https://www.github.com/dotnet/format/pull/698)
- [Only run Imports formatter when is has configuration in the .editorconfig (701)](https://www.github.com/dotnet/format/pull/701)

### How To Install

The `dotnet-format` nuget package is [published to nuget.org](https://www.nuget.org/packages/dotnet-format/).

You can install the tool using the following command.

```console
dotnet tool install -g dotnet-format
```

#### Installing Development Builds

Development builds of `dotnet-format` are being hosted on Azure Packages. You can visit the [dotnet-format Azure Packages page](https://dev.azure.com/dnceng/public/_packaging?_a=package&feed=dotnet-tools&view=versions&package=dotnet-format&protocolType=NuGet).

You can install the latest  build of the tool using the following command.

```console
dotnet tool install -g dotnet-format --version 5.1.* --add-source https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json
```

### How To Use

By default `dotnet-format` will look in the current directory for a project or solution file and use that as the workspace to format. If more than one project or solution file is present in the current directory, you will need to specify the workspace to format. You can control how verbose the output will be by using the `-v` option.

```console
Usage:
  dotnet-format [options] [<workspace>]

Arguments:
  <workspace>    A path to a solution file, a project file, or a folder containing a solution or project file. If a path is not specified then the current directory is used.

Options:
  --no-restore                        Doesn't execute an implicit restore before formatting.
  --folder, -f                        Whether to treat the `<workspace>` argument as a simple folder of files.
  --fix-whitespace, -w                Run whitespace formatting. Run by default when not applying fixes.
  --fix-style, -s <severity>          Run code style analyzers and apply fixes.
  --fix-analyzers, -a <severity>      Run 3rd party analyzers and apply fixes.
  --diagnostics <diagnostic ids>      A space separated list of diagnostic ids to use as a filter when fixing code style or 3rd party analyzers.
  --include <include>                 A list of relative file or folder paths to include in formatting. All files are formatted if empty.
  --exclude <exclude>                 A list of relative file or folder paths to exclude from formatting.
  --check                             Formats files without saving changes to disk. Terminates with a non-zero exit code if any files were formatted.
  --report <report>                   Accepts a file path, which if provided, will produce a json report in the given directory.
  --binarylog <binary-log-path>       Log all project or solution load information to a binary log file.
  --verbosity, -v <verbosity>         Set the verbosity level. Allowed values are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic]
  --version                           Show version information
```

Add `format` after `dotnet` and before the command arguments that you want to run:

| Examples                                                         | Description                                                                                        |
| ---------------------------------------------------------------- |--------------------------------------------------------------------------------------------------- |
| `dotnet format`                                                  | Formats the project or solution in the current directory.                                          |
| `dotnet format <workspace>`                                      | Formats a specific project or solution.                                                            |
| `dotnet format <workspace> -f`                                   | Formats a particular folder and subfolders.                                                        |
| `dotnet format <workspace> --fix-style warn`                     | Fixes only codestyle analyzer warnings.                                                            |
| `dotnet format <workspace> --fix-style --no-restore`             | Fixes only codestyle analyzer errors without performing an implicit restore.                       |
| `dotnet format <workspace> --fix-style --diagnostics IDE0005`    | Fixes only codestyle analyzer errors for the IDE0005 diagnostic.                                   |
| `dotnet format <workspace> --fix-whitespace --fix-style`         | Formats and fixes codestyle analyzer errors.                                                       |
| `dotnet format <workspace> --fix-analyzers`                      | Fixes only 3rd party analyzer errors.                                                              |
| `dotnet format <workspace> -wsa`                                 | Formats, fixes codestyle errors, and fixes 3rd party analyzer errors.                              |
| `dotnet format -v diag`                                          | Formats with very verbose logging.                                                                 |
| `dotnet format --include Programs.cs Utility\Logging.cs`         | Formats the files Program.cs and Utility\Logging.cs                                                |
| `dotnet format --check`                                          | Formats but does not save. Returns a non-zero exit code if any files would have been changed.      |
| `dotnet format --report <report-path>`                           | Formats and saves a json report file to the given directory.                                       |
| `dotnet format --include test/Utilities/*.cs --folder`           | Formats the files expanded from native shell globbing (e.g. bash). Space-separated list of files are fed to formatter in this case. Also applies to `--exclude` option. |
| `dotnet format --include 'test/Utilities/*.cs' --folder`         | With single quotes, formats the files expanded from built-in glob expansion. A single file pattern is fed to formatter, which gets expanded internally. Also applies to `--exclude` option. |
| `ls tests/Utilities/*.cs \| dotnet format --include - --folder`  | Formats the list of files redirected from pipeline via standard input. Formatter will iterate over `Console.In` to read the list of files. Also applies to `--exclude` option. |

### How To Uninstall

You can uninstall the tool using the following command.

```console
dotnet tool uninstall -g dotnet-format
```

### How To Build From Source

You can build and package the tool using the following commands. The instructions assume that you are in the root of the repository.

```console
build -pack
# The final line from the build will read something like
# Successfully created package '..\artifacts\packages\Debug\Shipping\dotnet-format.5.1.0-dev.nupkg'.
# Use the value that is in the form `5.1.0-dev` as the version in the next command.
dotnet tool install --add-source .\artifacts\packages\Debug\Shipping -g dotnet-format --version <version>
dotnet format
```

> Note: On macOS and Linux, `.\artifacts` will need be switched to `./artifacts` to accommodate for the different slash directions.
