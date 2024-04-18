# Style 🕺💃

## Introduction to Style Guides and Linters
Writing clean and maintainable code is crucial in software development, particularly when working in teams. In this lesson, we'll delve into the importance of adhering to style guides and using linters to enforce these standards in Ruby on Rails projects. We'll also guide you through setting up RuboCop and ESLint in your project using Visual Studio Code.

## Why Style Guides Matter
A style guide provides a coherent set of rules for code formatting and best practices within a programming language. Adhering to a style guide ensures that code is consistent and easy to understand, reducing the mental overhead for developers navigating the codebase.


## Recommended Ruby Style Guides
- [Community Ruby Style Guide](https://rubystyle.guide/): Community maintained guidelines based on the principle "Programs must be written for people to read, and only incidentally for machines to execute."[*](https://rubystyle.guide/#guiding-principles)
- [Shopify's Ruby Style Guide](https://ruby-style-guide.shopify.dev/): Offers conventions tailored to large-scale applications, emphasizing clarity and scalability.


## Linters and Code Analyzers
Linters are tools that help identify issues like syntax errors, stylistic errors, and other potential problems before they become more serious. They play a vital role in maintaining code quality.

## RuboCop 🤖
RuboCop is a static code analyzer for Ruby, based on the [community style guide]((https://rubystyle.guide/)). It can also format code, fixing issues automatically.

### Integrating RuboCop
To integrate RuboCop into your Rails project, follow these steps:

1. Add RuboCop to your Gemfile.
```ruby
# only needed in the development environment
group :development do
  ...
  # Set the require option to false, as it is a standalone tool.  
  gem 'rubocop', require: false
  ...
end
```

2. Run `bundle install` to install the gem.

3. Create a `.rubocop.yml` file at the root of your project to customize rules if necessary.

4. To analyze your project, run:
```bash
rubocop
```

5. To automatically fix issues, run:
```bash
rubocop -a
```

### Visual Studio Code Extensions for Rubocop
- [VSCode RuboCop](https://marketplace.visualstudio.com/items?itemName=rubocop.vscode-rubocop): Integrates RuboCop into VSCode, providing real-time feedback and autocorrection features directly in your editor.


## ESLint
[ESLint](https://eslint.org/) is a static code analyzer for JavaScript. It can also format code, fixing issues automatically.

### Integrating ESLint
1. Install ESLint globally or in your project.

```bash
npm install eslint --save-dev
```

2. Initialize ESLint to create an .eslintrc configuration file.
```bash
eslint --init
```

<aside>
During the initialization, you will be asked a series of questions about your coding style preferences and your environment (such as which framework you are using, whether you use React, etc.). You can also choose to extend popular configurations like the Airbnb style guide.
</aside>

3. Customize the configuration to extend popular style guides like Airbnb.
```json
{
  "extends": "airbnb"
}
```

4. Lint your JavaScript files.

```bash
npx eslint yourfile.js
```
For a more comprehensive check, you can run ESLint on all files in a directory like this:

```bash
npx eslint .
```

This command will lint all JavaScript files in the current directory and its subdirectories. If you want to specify a particular pattern, you can do so using glob patterns.

```bash
npx eslint "src/**/*.js"
```

5. Fix Issues Automatically
ESLint can automatically fix many of the issues it detects. To enable this feature, use the `--fix` option.

```bash
npx eslint yourfile.js --fix
```
This will modify the files where possible to conform to the style rules defined in your configuration.

<!-- TODO: add script so you can run `npm lint` -->

### Visual Studio Code Extensions for ESLint
- [ESLint VSCode Extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint): Integrates ESLint into VSCode enabling real-time linting.

## HTML, CSS and ERB Formatting
It's essential to maintain clean code in your HTML, CSS, and ERB templates as well.

- [HTMLLint](https://html-lint.com/): Provides a free online validator and reformatter tool for HTML.
- [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html): Provides conventions for writing consistent, clean HTML and CSS.
- [HTMLBeautifier](https://github.com/threedaymonk/htmlbeautifier): A tool for beautifying `html.erb` files, ensuring they are readable and well-structured.
- [VSCode ERB Beautify](https://marketplace.visualstudio.com/items?itemName=aliariff.vscode-erb-beautify): An extension for Visual Studio Code that formats ERB files.
- [StyleLint](https://github.com/stylelint/stylelint): CSS linter that helps you avoid errors and enforce conventions.
- [erb-lint](https://github.com/Shopify/erb-lint): a linter specifically designed for ERB templates in Rails. It can lint Ruby code within ERB files and ensure it meets the guidelines you specify.

### Integrating HTMLBeautifier into VSCode
<!-- TODO: format document -->
<!-- cmd + shift + p -> format document for views -->
We can leverage the Formatter API from the vscode to format our ERB files, so no need to create a hack using a Task or CLI command.

1. Install [HTMLBeautifier](https://github.com/threedaymonk/htmlbeautifier) and [VSCode ERB Beautify](https://marketplace.visualstudio.com/items?itemName=aliariff.vscode-erb-beautify)

```ruby
# only needed in the development environment
group :development do
  ...
  # Set the require option to false, as it is a standalone tool.  
  gem 'htmlbeautifier', require: false
  ...
end
```

2. Use the command pallette (⌘ + shift + p) to call 'Format Document'.

![](assets/format.png)

<!-- TODO: add config steps? -->


## Conclusion
Adhering to style guides and utilizing linters are practices that significantly enhance the quality of your code. They ensure your code remains clean, consistent, readable and maintainable, facilitating better collaboration and fewer bugs. By incorporating these tools into your development workflow, you promote a higher standard of coding practices across your team.

## Resources
- [RuboCop Documentation](https://github.com/rubocop/rubocop): Detailed information on configuring and using RuboCop in your Rails projects.
- [Shopify's Ruby Style Guide](https://ruby-style-guide.shopify.dev/): Insights into Shopify's approach to Ruby coding standards.
- [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html): Guidelines for writing clean, consistent HTML and CSS.
- [Airbnb's Javascript Style Guide](https://github.com/airbnb/javascript): Insights into Airbnb's appraoch to Javascript coding standards.
- [W3 School's Javascript Conventions](https://www.w3schools.com/js/js_conventions.asp)
- [HTMLBeautifier](https://github.com/threedaymonk/htmlbeautifier/): Tool for formatting HTML.erb files.
