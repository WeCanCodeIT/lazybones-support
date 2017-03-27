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

In this example, we'll be creating a project using the basic-java-eclipse template with a project name of "foo-bar". A student would open Git Bash, placing her in her home directory (`~`), then run `createBasicJavaProject foo-bar`.

This will create the following files/folders in the `foo-bar` folder:

- build.gradle
- .gitignore
- README.md
- src/main/java/org/wecancodeit/fooBar/FooBarApp.java
- .lazybones/ (ignored via .gitignore)

Afterwards, it will:
- `cd` into the `foo-bar` folder
- run `gradle eclipse` to set up the Eclipse project configuration

### Generated Java application file

```
package org.wecancodeit.fooBar;

public class FooBarApp {

	public static void main(String[] args) {
		// write your code here
	}

}
```

### Generated README.md

See it rendered in all its glory [here](sample-README.md).

```
# Basic Java/Gradle/Eclipse project template

You have just created a basic Java project using the standard Gradle project layout. It provides a basic Gradle build, including support for generating Eclipse project files so that you can import your project into Eclipse. Java source files should be placed into `src/main/java`. You will find an application class (a class with a `public static void main(String[] args)` method) where you can being writing code at `src/main/java/org/wecancodeit/fooBar/FooBarApp.java`.

## File Locations
- project folder: `/home/brian/work/foo-bar`
- main class
	- relative to project folder: `src/main/java/org/wecancodeit/fooBar/FooBarApp.java`
	- absolute path: `/home/brian/work/foo-bar/src/main/java/org/wecancodeit/fooBar/FooBarApp.java`

## Next steps
- Run `gradle eclipse` to generate Eclipse project configuration files.
- Import the project into Eclipse by selecting *File->Import…*, *General/Existing Projects into Workspace*, then browsing to the `/home/brian/work/foo-bar` folder.

```

# TODO

- [ ] external script
	- [ ] [NOT DOING - SRP] use lazybones' --with-git option to initialize project as git repository
	- [ ] run `gradle eclipse` after project creation