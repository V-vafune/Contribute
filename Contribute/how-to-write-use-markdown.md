---
title: How to use Markdown for writing Docs
description: This article provides the basics and reference information for the Markdown language used for writing docs.microsoft.com articles.
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 03/26/2019
---
# How to use Markdown for writing Docs

[Docs.microsoft.com](https://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn. Because of this, it has quickly become an industry standard. The docs site uses the [Markdig flavor](#markdown-flavor) of Markdown.


## Markdown basics

### Headings

To create a heading, you use a hash mark (#), as follows:

```md
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6. Examples of first- through fourth-level headers are used above.

There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.

If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly. For example, `# Async Programming in F# #`.

Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.

### Bold and italic text

To format text as **bold**, you enclose it in two asterisks:

```md
This text is **bold**.
```

To format text as *italic*, you enclose it in a single asterisk:

```md
This text is *italic*.
```

To format text as both ***bold and italic***, you enclose it in three asterisks:

```md
This is text is both ***bold and italic***.
```

### Blockquotes

Blockquotes are created using the `>` character:

```md
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

The preceding example renders as follows:

> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.

### Lists

#### Unordered list

To format an unordered/bulleted list, you can use either asterisks or dashes. For example, the following Markdown:

```md
- List item 1
- List item 2
- List item 3
```

will be rendered as:

- List item 1
- List item 2
- List item 3

To nest a list within another list, indent the child list items. For example, the following Markdown:

```md
- List item 1
  - List item A
  - List item B
- List item 2
```

will be rendered as:

- List item 1
  - List item A
  - List item B
- List item 2

#### Ordered list

To format an ordered/stepwise list, you use corresponding numbers. For example, the following Markdown:

```md
1. First instruction
1. Second instruction
1. Third instruction
```

will be rendered as:

1. First instruction
2. Second instruction
3. Third instruction

To nest a list within another list, indent the child list items. For example, the following Markdown:

```md
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

will be rendered as:

1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction

Note that we use '1.' for all entries. It makes diffs easier to review when later updates include new steps or remove existing steps.

### Tables

Tables are not part of the core Markdown specification, but GFM supports them. You can create tables by using the pipe (|) and hyphen (-) characters. Hyphens create each column's header, while pipes separate each column. Include a blank line before your table so it's rendered correctly.

For example, the following Markdown:

```md
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

Will be rendered as:

| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

For more information on creating tables, see:

- GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).
- The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.
- [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).
- [Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).
- [Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).

### Links

The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:

 `[link text](file-name.md)`

For more information on linking, see:

- The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.
- The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.

### Code snippets

Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences. For details, see:

- [Markdown's native support for code blocks](https://daringfireball.net/projects/markdown/syntax#precode)
- [GFM support for code fencing and syntax highlighting](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Fenced code blocks are an easy way to enable syntax highlighting for your code snippets. The general format for fenced code blocks is:

    ```alias
    ...
    your code goes in here
    ...
    ```

The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used. The following is a list of commonly used programming languages in Docs content and the matching label:

These languages have friendly name support and most have language highlighting.

|Name|Markdown Label|
|-----|-------|
|.NET Console|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|Azure CLI|azurecli|
|Azure PowerShell|azurepowershell|
|Bash|bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# in browser|csharp-interactive|
|Console|console|
|CSHTML|cshtml|
|DAX|dax|
|Docker|dockerfile|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Kusto Query Language|kusto|
|Markdown|md|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|protobuf|protobuf|
|PowerApps (dot decimal separator)|powerapps-dot|
|PowerApps (comma decimal separator)|powerapps-comma|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|XAML|xaml|
|XML|xml|

The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser. These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.

#### Example: C\#

__Markdown__

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

__Render__

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### Example: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Render__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## Docs custom Markdown extensions

> [!NOTE]
> Docs.Microsoft.com (Docs) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM). Markdig adds some functionality through Markdown extensions. As such, selected articles from the full OPS Authoring Guide are included in this guide for reference. (For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)

Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings. For richer formatting, articles can use Markdig features such as:

- Note blocks
- Include files
- Selectors
- Embedded videos
- Code snippets/samples

For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.

### Note blocks

You can choose from four types of note blocks to draw attention to specific content:

- NOTE
- WARNING
- TIP
- IMPORTANT

In general, note blocks should be used sparingly because they can be disruptive. Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.

Examples:

```md
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

These alerts look like this on docs.microsoft.com:

![shows how the alerts in the previous example look on the published Docs page with different icons and colors](media/alerts-rendering.png)

### Include files

When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature. This feature instructs OPS to include the file in your article file at build time, making it part of your published article. Three types of include references are available to help you reuse content:

- Inline: Reuse a common text snippet inline with within another sentence.
- Block: Reuse an entire Markdown file as a block, nested within a section of an article.
- Image: This is how standard image inclusion is implemented in Docs.

An inline or block include file is just a simple Markdown (.md) file. It can contain any valid Markdown. All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository. When the article is published, the included file is seamlessly integrated into it.

Here are requirements and considerations for include files:

- Use an include file whenever you need the same text to appear in multiple articles.
- Use a block include reference for significant amounts of content--a paragraph or two, a shared procedure, or a shared section. Do not use them for anything smaller than a sentence.
- Include references won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions. They'll be rendered only after publication.
- Ensure that all the text in an include file is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include file. Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.
- Don't embed include references within other include files. They are not supported.
- Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder. The media directory should not contain any images in its root. If the include file does not have images, a corresponding media directory is not required.
- As with regular articles, don't share media between include files. Use a separate file with a unique name for each include file and article. Store the media file in the media folder that's associated with the include file.
- Don't use an include file as the only content of an article.  Include files are meant to be supplemental to the content in the rest of the article.

Example:

```md
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### Selectors

Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms. This is typically most applicable to our mobile platform content for developers. There are currently two different types of selectors in Markdig, a single selector and a multi-selector.

Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include file. Then you can reference that include file in all your articles that use the same selector.

The following shows an example selector:

```md
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### Code include references

The Docs code snippet Markdown extension allows you to embed code samples in your articles and render them with language-specific syntax coloring. You can include code from either the current repository or another repository. The instructions below provides an overview of how to use the feature with the [docs.microsoft.com Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack). In Visual Studio Code, you can preview the code snippets by opening **Preview**. Highlighting and interactivity are not available in preview.

> [!NOTE]
> The extension does not support including code content within it inline – this is to be done through the standard triple-tick Markdown convention.

#### Code from current repository

1. In Visual Studio Code, click **Alt + M** or **Option + M** and select Snippet.
2. Once Snippet is selected, you will be prompted for Full Search, Scoped Search or Cross-Repository Reference. To search locally, select Full Local Search.
3. Enter a search term to find the file. Once you’ve found the file, select the file.
4. Next, select an option to determine which line(s) of code should be included in the snippet. The options are: **ID**, **Range** and **None**.
5. Based on your selection from Step 4, provide a value if necessary.

Display entire code file:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs":::
```

Display part of a code file by specifying line numbers:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

Display part of a code file by a snippet name:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" id="snippet_Create":::
```

#### Code from another repository

1. In Visual Studio Code, click **Alt + M** or **Option + M** and select Snippet.
2. Once Snippet is selected, you will be prompted for Full Search, Scoped Search or Cross-Repository Reference. To search across repositories, select Cross-Repository Reference.
3. You will be given a selection of repositories that are in *.openpublishing.publish.config.json*. Select a repository.
3. Enter a search term to find the file. Once you’ve found the file, select the file.
4. Next, select an option to determine which line(s) of code should be included in the snippet. The options are: **ID**, **Range** and **None**.
5. Based on your selection from Step 5, provide a value if necessary.

Your snippet reference will look like this:

```markdown
:::code language="csharp" source="~/samples-durable-functions/samples/csx/shared/Location.csx" highlight="2,5":::
```

#### Path to code file

Example:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

The example is from the ASP.NET docs repo, [aspnetcore/data/ef-mvc/crud.md](https://github.com/aspnet/Docs/blob/master/aspnetcore/data/ef-mvc/crud.md)
article file. The code file is referenced by a relative path to
[aspnetcore/data/ef-mvc/intro/samples/cu/Controllers/StudentsController.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/data/ef-mvc/intro/samples/cu/Controllers/StudentsController.cs)
in the same repository.

#### Selected line numbers

Example:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

This example displays only lines 2-24 and 26 of the *StudentController.cs* code file.

Prefer snippets over hard-coded line numbers, as explained in the next section.

#### Named snippet

Example:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" id="snippet_Create":::
```

Use only letters and underscores for the name.

The example displays the `snippet_Create` section of the code file. The code file for this example
has a C# region named `snippet_Create`:

```cs
// code excluded from the snippet
// <snippet_Create>
// code included in the snippet
// </snippet_Create>
// code excluded from the snippet
```

Whenever you can, refer to a named section rather than specifying line numbers. Line number
references are brittle because code files inevitably change in ways that make line numbers change.
You don't necessarily get notified of such changes. Your article eventually starts showing the wrong
lines and you have no clue anything has changed.

#### Highlighting selected lines

Example:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26" highlight="2,5":::
```

The example highlights lines 2 and 5, counting from the start of the displayed snippet. (Line
numbers to highlight don't count from the start of the code file.) In other words, lines 3 and 6
of the code file are highlighted.

#### Interactive code snippets

You can enable interactive mode for code snippets included by reference. Here are examples:

```markdown
:::code language="powershell" source="PowerShell.ps1" interactive="cloudshell-powershell":::
```

```markdown
:::code language="bash" source="Bash.sh" interactive="cloudshell-bash":::
```

To turn on this feature for a particular code block, use the `interactive` attribute. The
available attribute values are:

- `cloudshell-powershell` - Enables the Azure PowerShell Cloud Shell, as in the preceding
  example
- `cloudshell-bash` - Enables the Azure Cloud Shell
- `try-dotnet` - Enables Try .NET
- `try-dotnet-class` - Enables Try .NET with class scaffolding
- `try-dotnet-method` - Enables Try .NET with method scaffolding

There are pairs of `language` and `interactive` that are compatible. For example, if `interactive` is `try-dotnet`, the language must be `csharp`. Similarly, `cloudshell-powershell` would only work with `powershell` and `cloudshell-bash` would work only with `bash` as the language.

For the Azure Cloud Shell and PowerShell Cloud Shell, users can run commands against only their own
Azure account.

[Try .NET](https://github.com/dotnet/try) enables interactive execution of .NET code (C#) in the browser. For Try .NET, there are three options for interactivity: `try-dotnet`, `try-dotnet-class`, and `try-dotnet-method`. Use of these options require no additional configuration within the code snippet. The namespaces currently available by default are:

- System
- System.Linq
- System.Collections.Generic
- System.Text
- System.Globalization
- System.Text.RegularExpressions

The `try-dotnet` attribute value enables users to run C# code in the browser without the need to wrap the code in any custom code.

Example:

```md
:::code language="csharp" source="relative/path/source.cs" interactive="try-dotnet":::
```

The `try-dotnet-class` value applies class-level scaffolding to the code passed to the interactive component.

```md
:::code language="csharp" source="relative/path/source.cs" id="snippet-tag" interactive="try-dotnet-class":::
```

Example:

Code Snippet without Class Scaffolding Applied

```md
public static void Main()
    {  
        // Specify the data source.  
        int[] scores = new int[] { 97, 92, 81, 60 };        // Define the query expression.

        IEnumerable<int> scoreQuery =
            from score in scores  
            where score > 80  
            select score;

        // Execute the query.  
        foreach (int i in scoreQuery)
        {  
            Console.Write(i + " ");
        }
    }  
}
```

Code Snippet with Class Scaffolding Applied

```md
class NameOfClass {

   public static void Main()
    {
        // Specify the data source.
        int[] scores = new int[] { 97, 92, 81, 60 };

        // Define the query expression.
        IEnumerable<int> scoreQuery =
            from score in scores
            where score > 80
            select score;

        // Execute the query.
        foreach (int i in scoreQuery)
        {
            Console.Write(i + " ");
        }
    }  
}
```

The `try-dotnet-method` value applies method-level scaffolding to the code passed to the interactive component.

```md
:::code language="csharp" source="relative/path/source.cs" id="snippet-tag" interactive="try-dotnet-method":::
```

Example:

Code Snippet without Method Scaffolding Applied

```md
/*Print some string in C#*/

Console.WriteLine("Hello C#.);
```

Code Snippet with Method Scaffolding Applied

```md
public static void Main(string args[]) {

/*Print some string in C#*/

Console.WriteLine("Hello C#.);
}
```

#### Snippet syntax reference

You can reference code snippets stored in your repo by using the specified code language. The
content of the specified code path will be expanded and included in your file.

There aren't restrictions on the folder structure of code snippets. You can manage the code snippets
as normal source code.

Syntax:

```md
:::code language="<language>" source="<path>" <attribute>="<attribute-value>":::
```

> [!IMPORTANT]
> This syntax is a block Markdown extension. It must be used on its own line.

- `<language>` (*optional*)
  - Language of the code snippet. For more information, see the [Supported languages](#supported-languages)
    section later in this article.

- `<path>` (*mandatory*)
  - Relative path in the file system that indicates the code snippet file to reference.

- `<attribute>` and `<attribute-value>` (*optional*)
  - Used together to specify how the code should be retrieved from the file:
    - `range`: `1,3-5` A range of lines. This example includes lines 1, 3, 4, and 5.
    - `id`: `snippet_Create` The ID of the snippet that needs to be inserted from the code file. This value cannot co-exist with range.
    - `highlight`: `2-4,6` Range and/or numbers of lines that need to be highlighted in the generated code snippet. The numbering is relative to the code snippet itself, not the imported range.
    - `interactive`: `cloudshell-powershell`, `cloudshell-bash`, `try-dotnet`, `try-dotnet-class`, `try-dotnet-method` String value determines what kinds of interactivity are enabled.

#### Supported languages

|Name|Markdown label|
|-----|-------|
|.NET Core CLI|`dotnetcli`|
|ASP.NET with C#|`aspx-csharp`|
|ASP.NET with VB|`aspx-vb`|
|Azure CLI|`azurecli`|
|Azure CLI in browser|`azurecli-interactive`|
|Azure PowerShell in browser|`azurepowershell-interactive`|
|AzCopy|`azcopy`|
|Bash|`bash`|
|C++|`cpp`|
|C#|`csharp`|
|C# in browser|`csharp-interactive`|
|Console|`console`|
|CSHTML|`cshtml`|
|DAX|`dax`|
|Docker|`Dockerfile`|
|F#|`fsharp`|
|HTML|`html`|
|Java|`java`|
|JavaScript|`javascript`|
|JSON|`json`|
|Kusto Query Language|`kusto`|
|Markdown|`md`|
|Objective-C|`objc`|
|PHP|`php`|
|PowerShell|`powershell`|
|Power Query M|`powerquery-m`|
|protobuf|`protobuf`|
|Python|`python`|
|Ruby|`ruby`|
|SQL|`sql`|
|Swift|`swift`|
|VB|`vb`|
|XAML|`xaml`|
|XML|`xml`|
|YAML|`yml`|

#### Code extensions

|Name|Markdown label|File extension|
|-----|-------|-----|
|C#|csharp|.cs, .csx|
|C++|cpp|.cpp, .h|
|F#|fsharp|.fs|
|Java|java|.java|
|JavaScript|javascript|.js|
|Python|python|.py|
|SQL|sql|.sql|
|VB|vb|.vb|
|XAML|xaml|.xaml|
|XML|xml|.xml|

## Gotchas and troubleshooting

### Alt text

Alt text that contains underscores won't be rendered properly. For example, instead of using this:

```md
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Escape the underscores like this:

```md
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### Apostrophes and quotation marks

If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks. These need to be encoded or changed to basic apostrophes or quotation marks. Otherwise, you end up with things like this when the file is published: Itâ€™s

Here are the encodings for the "smart" versions of these punctuation marks:

- Left (opening) quotation mark: `&#8220;`
- Right (closing) quotation mark: `&#8221;`
- Right (closing) single quotation mark or apostrophe: `&#8217;`
- Left (opening) single quotation mark (rarely used): `&#8216;`

### Angle brackets

It is common to use angle brackets to denote a placeholder. When you do this in text (not code), you must encode the angle brackets. Otherwise, Markdown thinks that they're intended to be an HTML tag.

For example, encode `<script name>` as `&lt;script name&gt;`

## Markdown flavor

The docs.microsoft.com site backend supports [CommonMark](https://commonmark.org/) compliant Markdown parsed through the [Markdig](https://github.com/lunet-io/markdig) parsing engine. This markdown flavor is mostly compatible with [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), as most docs are stored in GitHub and can be edited there. Additional functionality is added through Markdown extensions.

## See also:

### Markdown resources

- [Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Docs Markdown cheat sheet](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)
- [The Markdown Guide](https://www.markdownguide.org/)
