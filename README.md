![Icon](https://raw.github.com/SimonCropp/Strike/master/Icons/package_icon.png)

Wraps [Marked.js](https://github.com/chjj/marked/) to make it usable from .net.

## Nuget

Nuget package http://nuget.org/packages/Strike 

To Install from the Nuget Package Manager Console 
    
    PM> Install-Package Strike

## Usage

So if you run this 

```
var input = @"
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
";

using (var markdownify = new Markdownify())
{
    Debug.WriteLine(markdownify.Transform(input));
}
```

The output will be this 

```
<table>
	<thead>
		<tr>
			<th>Tables</th>
			<th style="text-align:center">Are</th>
			<th style="text-align:right">Cool</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>col 3 is</td>
			<td style="text-align:center">right-aligned</td>
			<td style="text-align:right">$1600</td>
		</tr>
		<tr>
			<td>col 2 is</td>
			<td style="text-align:center">centered</td>
			<td style="text-align:right">$12</td>
		</tr>
	</tbody>
</table>
```

**Note:** The indentation is added for clarity.  


## MarkedJS

The binary ships with a resource merged version of [MarkedJS]https://github.com/chjj/marked/). Also see the [License](https://github.com/chjj/marked/blob/master/LICENSE).

### Current merged version

The current version included in the library is v0.3.1. If you feel a newer version should be included at any point in time please raise an issue.

### Running a custom version

If you want to run a custom version of MarkedJS simply place the custom `marked.js` in the current running directory and that file will be used instead of the merged version. The newest MarkedJS file can be obtained here https://github.com/chjj/marked/tree/master/lib 

## MSIE JavaScript Engine for .NET

The binary ships with an ILMerged copy of the [MSIE JavaScript Engine](https://github.com/Taritsyn/MsieJavaScriptEngine/). It also gives credit to various other libraries for its' inspiration [MSIE JavaScript Engine Credits](https://github.com/Taritsyn/MsieJavaScriptEngine#credits). Also see the [License](http://github.com/Taritsyn/MsieJavaScriptEngine/blob/master/LICENSE.md).

## Performance

Using [John Grubers Markdown Test Suite](https://daringfireball.net/projects/markdown/) as a document source.

| Engine | Construction | FirstRun | Bulk (304 docs) | Average per doc |
|:-------|:------------:|:--------:|:---------------:|:---------------:|
|MarkdownSharp|8 ms|54 ms|478 ms|1.57 ms|
|MarkdownDeep|1 ms|21 ms|51 ms|0.17 ms|
|Strike|39 ms|8 ms|311 ms|1.02 ms|

### So why use this library

So this raises the question of
 
> why use this library over MarkdownDeep". 

And the answer is 

> It is not only about performance

Other points to consider

* MarkedJS rendering most closely matches GitHubs markdown rendering
* MarkedJS is an active project with bugs fixed promptly and features being added 

## Icon 

<a href="http://thenounproject.com/term/lightning/6029/" target="_blank">Lightning</a> designed by <a href="http://thenounproject.com/tlb/" target="_blank">Thomas Le Bas</a> from The Noun Project
