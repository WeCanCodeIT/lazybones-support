# Lazybones Support for Student Project Creation

This repository contains instructions/explanations of using [Lazybones](https://github.com/pledbrook/lazybones) to simplify project creation for beginning students. Per the Lazybones GitHub page:

> The tool is very simple: it allows you to create a new project structure for any framework or library for which the tool has a template… The concept of Lazybones is very similar to Maven archetypes, and what Yeoman does for web applications.

## Environment configuration

Install Lazybones using [sdkman](http://sdkman.io/):

```
sdk install lazybones
```

See [Running It](https://github.com/pledbrook/lazybones#running-it) in the Lazybones README for more instructions.

### Lazybones configuration

Add the following to the Lazybones configuration file, `~/.lazybones/config.groovy` (or create the file with this content) in order to add `btforsythe/lazybones-templates` to the Lazybones search path for templates:

```
bintrayRepositories = [
	"btforsythe/lazybones-templates",
	"pledbrook/lazybones-templates"
]
```
### Add shell script(s) to path

To eliminate the complexity of specifying arguments to Lazybones, I've created a shell script(s) in the `scripts` folder. These should be somewhere on the path (probably `~/bin`) so they can be executed from the terminal prompt.

## Example: basic-java-eclipse template


# TODO

- [ ] external script
	- [ ] [NOT DOING - SRP] use lazybones' --with-git option to initialize project as git repository
	- [ ] run `gradle eclipse` after project creation