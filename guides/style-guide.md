Labs Style Guide
=====

In keeping with DRY, our style guides are not really ours but other, very good
style guides with some exceptions/clarifications. As always, the number one
rule of style is:

Number One Rule of Style
-----

Be consistent. Be consistent within a project, and _especially_ within a
file. Don't waste a commit on making something conform to style if it's already
consistant and readable.  And if you do refactor for style — which should only
be in the worst cases of inconsistency or incomprehensibility — make sure to do
it in a commit separate from commits that effect content.

The number 1.5 rule is to use common sense. A style guide is just that, a
guide.

Global Style Rules
------------------

### Naming

JavaScript typically uses camelCase (Java) conventions for its variable
names, while Python typically uses underscore style (like C). (See the style
guides below for detailed explanations of the two — e.g., Python still uses
CamelCase for class names.)

JSON can go either way, so we prefer underscore style unless the context asks
otherwise (as in npm's `package.json` files). Template variables (be they
Django, Handlebars, Mustache, what have you), whether in the templates
themselves or in the object that's assigning them, should use the style of
whatever language they're being used by. Hence, a Django template should use
underscores but a Handlebars template should use camelCase. If a template is
likely to be shared by two languages with different styles (e.g., the template
is rendered both by server-side Python and client-side JS), default to the
language that uses it more. If it's roughly equal, use underscore style.

### TODOs

Leave TODO statements to indicate things that have yet to be done but that
would require too much overhead to do now. These should be temporary only, and
should include the PennKey of the author in parenthesis. For example:

``` javascript
if (myStr === '') { // TODO(kyleh): Figure out how to handle the empty string
  throw new Error("Empty string!");
}
```

TODOs should only be used for things that you:

- don't know how to do know and won't be able to figure out easily;
- are being blocked from doing because of someone/something else; or
- know how to do and will come back to but are ignoring now for time's sake.

Note that a TODO should mainly be for yourself, and just a stop-gap measure. If
it's something that will or might be handled by others, file a bug instead, and
only leave a TODO if it's something that others must be cognizant of as they're
coding around you.

### Spaces vs. Tabs

**Spaces.** Prefer spaces to tabs (unless the file is already knee-deep in
tabs). If the file has both, go with what's most used. Consider editing the
file to be self-consistent (in a separate commit of course), since, especially
in Python, this can become an issue.

### Comments

Any nontrivial method must have a comment (or docstring in Python) that
explains what it does and any side effects. Ideally indicate the types of its
arguments and its return type.

Language-Specific Guides
-----

### Python

**Use [PEP-8](http://www.python.org/dev/peps/pep-0008/).**

**virtualenv and `requirements.txt`.** Every Python project should have a
`requirements.txt` file. The best way to generate such a file is to always be
using virualenv during development and then periodically run `pip freeze >
requirements.txt` to automatically generate the list of Python modules and
versions your project is using.

### JavaScript

**Use the [Google JavaScript StyleGuide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml).**

**JSDoc.** The Google style guide tells you to use JSDoc. This nice, especially
for annotating the type of potentially confusing functions, but not required.

### READMEs and Text Files

**Use [Markdown](http://daringfireball.net/projects/markdown/).**

### English

As PEP 8 helpfully tells us:

> When writing English, Strunk and White apply.

After that, prefer the _Chicago Manual of Style_.
