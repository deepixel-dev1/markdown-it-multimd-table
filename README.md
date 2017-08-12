## Intro
Bored with HTML table tags when I need some extended table functions like `colspan` in Markdown. I found that [MultiMarkdown](https://fletcher.github.io/MultiMarkdown-6/) had defined complete and clear rules for advanced table syntax, which is compatible to standard Markdown table syntax at the same time.

For example, the following features are given:
* `colspan` attribute
* Multiple `<thead>` and `<tbody>`
* Captions

NOTE: This plugin might behave differently from MultiMarkdown for some edging cases; For this plugin was developed mainly under the rules in [MultiMarkdown User's Guide](http://fletcher.github.io/MultiMarkdown-5/tables). Please impose an issue if you find problems related.

## Usage
```javascript
var md = require('markdown-it')()
            .use(require('markdown-it-multimd-table'));

md.render(/*...*/)
```

For test, do this in terminal:
```bash
$ git clone https://github.com/RedBug312/markdown-it-multimd-table.git
$ npm install markdown-it --save
$ vim test.js

var md = require('markdown-it')()
            .use(require('./markdown-it-multimd-table'));
const exampleTable =
"|             |          Grouping           || \n" +
"First Header  | Second Header | Third Header | \n" +
" ------------ | :-----------: | -----------: | \n" +
"Content       |          *Long Cell*        || \n" +
"Content       |   **Cell**    |         Cell | \n" +
"                                               \n" +
"New section   |     More      |         Data | \n" +
"And more      | With an escaped '\\|'        ||\n" +
"[Prototype table]                              \n";
console.log(md.render(exampleTable));

$ node test.js > test.html
$ firefox test.html
```

## Credits
* [MultiMarkdown](https://fletcher.github.io/MultiMarkdown-6/), Lightweight markup processor to produce HTML, LaTeX, and more.
* [markdown-it](https://markdown-it.github.io/), Markdown parser, done right. 100% CommonMark support, extensions, syntax plugins & high speed

## License
This software is licensed under the [MIT license](https://opensource.org/licenses/mit-license.php) © RedBug312.