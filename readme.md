<!--
GENERATED FILE - DO NOT EDIT
This file was generated by [MarkdownSnippets](https://github.com/SimonCropp/MarkdownSnippets).
Source File: /readme.source.md
To change this file edit the source file and then run MarkdownSnippets.
-->

# <img src="/src/icon.png" height="30px"> WaffleGenerator

[![Build status](https://ci.appveyor.com/api/projects/status/bv3erhc4d2pegpba/branch/master?svg=true)](https://ci.appveyor.com/project/SimonCropp/WaffleGenerator)
[![NuGet Status](https://img.shields.io/nuget/v/WaffleGenerator.svg?label=WaffleGenerator&cacheSeconds=86400)](https://www.nuget.org/packages/WaffleGenerator/)
[![NuGet Status](https://img.shields.io/nuget/v/WaffleGenerator.Bogus.svg?label=WaffleGenerator.Bogus&cacheSeconds=86400)](https://www.nuget.org/packages/WaffleGenerator.Bogus/)

Produces text which, on first glance, looks like real, ponderous, prose; replete with clichés.

Example content:

```
The Aesthetic Of Economico-Social Disposition

"In this regard, the underlying surrealism of the take home message should not 
divert attention from The Aesthetic Of Economico-Social Disposition"
(Humphrey Yokomoto in The Journal of the Total Entative Item (20044U))

On any rational basis, a particular factor, such as the functional baseline, the 
analogy of object, the strategic requirements or the principal overriding programming 
provides an interesting insight into the complementary functional derivation. 
This trend may dissipate due to the mensurable proficiency.
```

This output can be used in similar way to [Lorem ipsum](https://en.wikipedia.org/wiki/Lorem_ipsum) content, in that it is useful for producing text for build software and producing design mockups.

Based on the awesome work by [Andrew Clarke](https://www.red-gate.com/simple-talk/author/andrew-clarke/) outlined in [The Waffle Generator](https://www.red-gate.com/simple-talk/dotnet/net-tools/the-waffle-generator/).

Code based on [SDGGenerators - Red Gate SQL Data Generator Community Generators](https://archive.codeplex.com/?p=sdggenerators).

<!-- toc -->
## Contents

  * [Blazor App](#blazor-app)
  * [Main Package - WaffleGenerator](#main-package---wafflegenerator)
    * [Usage](#usage)
  * [WaffleGenerator.Bogus](#wafflegeneratorbogus)
    * [Usage](#usage-1)
<!-- endtoc -->



## Blazor App

The [Blazing Waffles](http://wafflegen.azurewebsites.net/) app allows the generation of waffle text online.

 * Azure Website: http://wafflegen.azurewebsites.net/
 * Source: https://github.com/gbiellem/BlazingWaffles


## Main Package - WaffleGenerator

https://nuget.org/packages/WaffleGenerator/


### Usage

The `WaffleEngine` can be used to produce Html or text:

<!-- snippet: htmlUsage -->
<a id='snippet-htmlusage'/></a>
```cs
var text = WaffleEngine.Html(
    paragraphs: 2,
    includeHeading: true,
    includeHeadAndBody: true);
Debug.WriteLine(text);
```
<sup>[snippet source](/src/Tests/WaffleEngineTests.cs#L28-L36) / [anchor](#snippet-htmlusage)</sup>
<!-- endsnippet -->

<!-- snippet: textUsage -->
<a id='snippet-textusage'/></a>
```cs
var text = WaffleEngine.Text(
    paragraphs: 1,
    includeHeading: true);
Debug.WriteLine(text);
```
<sup>[snippet source](/src/Tests/WaffleEngineTests.cs#L15-L22) / [anchor](#snippet-textusage)</sup>
<!-- endsnippet -->


## WaffleGenerator.Bogus

Extends [Bogus](https://github.com/bchavez/Bogus) to use WaffleGenerator.

https://nuget.org/packages/WaffleGenerator.Bogus/


### Usage

The entry extension method is `WaffleHtml()` or `WaffleText()`:

<!-- snippet: BogusUsage -->
<a id='snippet-bogususage'/></a>
```cs
var faker = new Faker<Target>()
    .RuleFor(u => u.Title, (f, u) => f.WaffleTitle())
    .RuleFor(u => u.Property1, (f, u) => f.WaffleHtml())
    .RuleFor(u => u.Property2, (f, u) => f.WaffleHtml(paragraphs: 4, includeHeading: true))
    .RuleFor(u => u.Property3, (f, u) => f.WaffleText())
    .RuleFor(u => u.Property4, (f, u) => f.WaffleText(paragraphs: 4, includeHeading: false));

var target = faker.Generate();
Debug.WriteLine(target.Title);
Debug.WriteLine(target.Property1);
Debug.WriteLine(target.Property2);
Debug.WriteLine(target.Property3);
Debug.WriteLine(target.Property4);
```
<sup>[snippet source](/src/Tests/FakerUsage.cs#L19-L33) / [anchor](#snippet-bogususage)</sup>
<!-- endsnippet -->


## Release Notes

See [closed milestones](../../milestones?state=closed).


## Icon

[Waffle](https://thenounproject.com/term/waffle/836862/) designed by Made by Made from [The Noun Project](https://thenounproject.com/)
