# Create a DHRIFT Workshop

This page is a synopsis and overview of how to create a DHRIFT workshop. Alternately, you could complete our workshop on Creating a DHRIFT Workshop. <insert link> 

## Getting Started

To create a new workshop, you will need to follow a few general key steps:

Create a new GitHub repository to house your workshops (or use an existing one)
Configure your workshop metadata using YAML
Write your workshop content in Markdown
Add images, downloads (e.g., datasets) and other assets to your workshop, if needed
Incorporate interactive features like quizzes, challenges, and code editors, if desired
Build and deploy your workshop using GitHub Actions
Depending on what you want to achieve with your workshop, you may need to follow additional steps or best practices. We'll cover these in more detail as we go along.

## Setting up Your Workshop Repository

The first step in creating a new workshop is to set up a GitHub repository to house your workshop content. You can create a new repository from scratch or use an existing repository if you prefer.

Considering we have already set up a DHRIFT site and repository using the wizard, we can simply use that repository to house our new workshop and subsequently add it to the available workshops on our site.

In general, you should be aware that the DHRIFT platform generates workshops by pointing to a specific repository that contains your workshop files.

For instance, in the following URL: <https://app.dhrift.org/inst/?instUser=dhri-curriculum&instRepo=dhrift-site-template>

...the `instUser` parameter specifies the GitHub user or organization that owns the repository, and the `instRepo` parameter specifies the name of the repository. You can use these parameters to point to your own repository and display your workshops on your DHRIFT site. DHRIFT will automatically detect the workshops (markdown files) in your repository and display them on the workshops page.

## Configuring Workshop Metadata

Once you have set up your workshop repository, you will want to create a new markdown file for your workshop. You can name this file anything you like, but it is a good idea to use a descriptive name that reflects the content of your workshop. For example, if you are creating a workshop on Python programming, you might name your file `intro-to-python.md`.

You can create and edit markdown files locally using a text editor like [Visual Studio Code](https://code.visualstudio.com/) or utilize the Jupyter Notebook code editor here in the browser (just save and download your files to your local file system). Make sure to save your file with the `.md` extension. If you are using the built-in code editor, you'll notice that there is a markdown option when creating a new file.

The first thing you will need to do in your workshop markdown file is configure your workshop metadata using [YAML](https://yaml.org/)." In terms of your workshop, the YAML language allows you to specify metadata such as the workshop title, author, description, learning objectives, estimated time, and more.

Here is an example of a simple YAML configuration for an Intro to Python workshop:

```yaml
---
title: Introduction to Python
cover title: Introduction to Python
description: "This workshop is designed for beginners who want to learn the basics of Python programming. By the end of this workshop, you will be able to write simple Python programs, work with variables, and use control structures like loops and conditionals."

programming_language: 'python'

learning objectives:
    - Understand the basic syntax and structure of Python
    - Learn how to work with variables and data types
    - Understand control structures like loops and conditionals

estimated time:
    - 2 hours

authors: 
    - 'Jimmy Pesto'
    - 'Bob Belcher'

facilitators:
    - 'Jimmy Pesto'

ethical considerations:
    - "Learners should be aware of the potential ethical implications of using Python for data analysis and machine learning. For example, it is important to consider issues of bias, privacy, and security when working with data in Python."

---
```

First, you'll notice the three dashes at the beginning and end of the YAML configuration. This is a standard way to indicate the start and end of a YAML document. You will always want to enclose your metadata in these dashes at the start of your markdown file.

The metadata will comprise the information to display on your workshop's front page. Here's a breakdown of the metadata fields shown above:

- `title` specifies the title of the workshop, which will be displayed on the workshop's front page.
- `cover title` specifies the title of the workshop that will be displayed in the image gallery of all workshops. Unless it is a very long title that may not display well in terms of the image, it is often the same as the title.
- `description` provides a brief overview of the workshop content and objectives.
- `programming_language` specifies which code editor to use for the workshop (e.g., Python, Jupyter, JavaScript, R, command line, etc). See below for a list of supported programming languages and the associated metadata field.
- `learning objectives` lists the main learning objectives of the workshop.
- `estimated time` specifies the estimated time needed to complete the workshop.
- `authors` lists the authors of the workshop.
- `facilitators` lists the facilitators, or instructors, of the workshop.

These are, at bare minimum, the fields you will likely want to include in your workshop metadata. However, it should be noted that the only truly required fields are `title`, `cover title`, and `description`. The other fields are optional but highly recommended for providing a complete and informative workshop experience.

You can also add additional metadata fields as needed for your workshop. For example, you might want to include a list of prerequisites, projects, additional resources or tutorials, etc. You can follow the same format as the `ethical considerations` field shown above for these additional fields, e.g.,

```yaml
prerequisites:
    - "No prior programming experience is required."
    - "A basic understanding of computer science concepts is helpful but not necessary."
```

### Supported Programming Languages

You can include the other code editors supported by DHRIFT in the `programming_language` field. Here is a list of supported programming languages and their associated metadata fields:

- Python: `'python'`
- Jupyter Notebooks: `'jupyter'`
- JavaScript: `'javascript'`
- R: `'r'`
- Command Line: `'command_line'`
- HTML and CSS: `'html_css'`

It will be up to you to decide which code editor (if any) is most appropriate for your workshop content.

## Writing Workshop Content

Once you have set up your workshop repository and YAML, you can start writing your workshop content in markdown. Markdown is a lightweight markup language that is fairly straightforward to read and write, once you understand the basic syntax. It allows you to format text, add images, and create links without having to write HTML (although it supports many basic HTML features such as text styling and table creation as well).

DHRIFT uses standard markdown syntax for formatting text, including headings, lists, links, images, and more. You can find a comprehensive guide to standard markdown syntax here: [Markdown Syntax Guide](https://www.markdownguide.org/basic-syntax/).

Beyond that, DHRIFT also includes a few custom markdown extensions that allow you to include interactive features like quizzes, challenges, and code editors in your workshop content. We'll cover these extensions in more detail in the following sections.

### General Structure

A typical DHRIFT workshop is divided into sections and subsections, each with its own content. You will want to separate your content into logical sections that follow the flow you envision for your workshop. For major sections, you can use level 1 markdown headings (`#`), and for subsections, you can use level 2 headings (`##`). For instance, in this workshop, we have used level 1 headings for major over-arching sections like "Introduction to DHRIFT" and level 2 headings for subsections like "What is DHRIFT?", "Underlying Technologies", etc. In general, note that both level 1 and level 2 headings will create a new page. DHRIFT will then automatically generate a table of contents for your workshop based on the headings you use.

For the most part, you can structure your workshop content as you see fit, but it is generally a good idea to follow a pedagogically conscientious progression from introduction to conclusion. Separating out your content effectively can help learners navigate through the material more easily and tackle the lessons in digestible chunks.

Here is an example of how you might structure the beginning of a workshop using markdown headings:

```markdown
# Introduction

This section provides a short introduction to the workshop. 

## Overview

This subsection provides an overview of the workshop and what learners can expect to gain from it.

## Learning Objectives

This subsection lists the main learning objectives of the workshop.

# Getting Started

This creates a new main section for the workshop.

## Setting up Your Environment

This subsection covers how to set up the necessary tools and resources to follow along with the workshop.

### Installing Python

This (sub)subsection provides instructions on how to install Python on your computer.

## Writing Your First Program

This subsection introduces learners to the basics of programming and writing their first program.

### Hello, World!

This (sub)subsection covers how to write a simple "Hello, world!" program in Python.
```

As you can see, we are utilizing level 1 headings for major sections like "Introduction" and "Getting Started" and level 2 headings for subsections like "Overview", "Learning Objectives", "Setting up Your Environment", etc. This structure helps to organize the content and make it easier for learners to follow along.

Furthermore, we are using level 3 headings for additional (sub)subsections like "Installing Python" and "Hello, World!" to further break down the content. Note that level 3 headings will be displayed *on the same page* as the level 1 or 2 heading they are nested under, and will not appear in the table of contents. This can be useful for breaking down content into smaller, more manageable sections without cluttering the table of contents or creating new pages.

## Adding Images

In addition to text content, you can also add images to your workshop. Images can help illustrate concepts, provide visual interest, and make your workshop more engaging.

To add an image to your workshop, you can use standard markdown syntax for images. Here is an example:

```markdown
![Alt text](/path/to/image.jpg)
```

In this syntax, `Alt text` is the alternative text for the image, which is displayed if the image fails to load (this should also comprise a short description of the image for accessibility purposes). `path/to/image.jpg` is the path to the image file in your repository. Typically, you will want to store your images in a subdirectory of your repository, such as `images/`, to keep your files organized. Even better would be to store the images in a designated folder for the workshop, e.g., `images/your-workshop`. Just make sure your folder title follows the *exact* name of your workshop so DHRIFT knows where to look for it. You can also use a URL to an external image if needed.

## Code Snippets and Info Boxes

### Code Snippets

DHRIFT workshops may also include inline code snippets to demonstrate programming concepts, provide examples, and guide learners through exercises. You can include code snippets in your workshop using standard markdown syntax for code blocks.

To create something like the following:

```python
print("Hello, world!")
```

...you can use three backticks ````(```)```` to start and end the code block, followed by the language identifier (e.g., `python`) to specify the language of the code snippet.

In this example, `python` specifies the language of the code snippet, which helps DHRIFT format the code block correctly. You can replace `python` with other supported languages like `javascript`, `html`, `console`, etc., as needed.

### Info Boxes

To create an info box with additional information or tips that stands out from the rest of your text, like the following...

<Info>
This is an info box with additional information or tips for learners.
</Info>

...you can use the following custom markdown syntax:

```markdown
<Info>
This is an info box with additional information or tips for learners.
</Info>
```

In this example, the `<Info>` tag creates an info box with the enclosed text. This can be useful for highlighting important information, providing additional context, or offering tips and suggestions to learners.

## Incorporating Interactive Features

DHRIFT workshops can include a variety of interactive features to engage learners and reinforce learning.

### Quizzes

To create a quiz, you can use the following custom markdown syntax:

```markdown
### Evaluation

What front-end technology does DHRIFT use to build its user interfaces?

<Quiz>
- React*
- Angular
- Vue
- Ember
</Quiz>
```

In this example, the (optional heading) `Evaluation` section introduces a multiple-choice quiz question, and the `<Quiz>` tag creates the interactive quiz. Learners can select an answer from the list, and DHRIFT will provide feedback on whether the answer is correct or incorrect. To specify a correct answer (or answers), mark it with an asterisk (`*`).

### Challenges

To create a challenge with a solution that you can show/hide, you can use the following custom markdown syntax:

```markdown
### Challenge

Where are DHRIFT workshops stored?

### Solution

<Secret>
In a GitHub repository.
</Secret>
```

In this example, the (optional heading) `Challenge` section poses a question or problem, and the `<Secret>` tag creates a hidden solution that learners can reveal by clicking a button. This allows learners to attempt the challenge on their own before checking the solution.

## Key Terms

DHRIFT workshops may also include a section of key terms to define and explain unfamiliar concepts. You can include a key terms section in your workshop using the following custom markdown syntax:

```markdown
<Keywords>
- DHRIFT
DHRIFT (Digital Humanities Resource Infrastructure for Teaching Technology) is an open educational resource (OER) and publication platform for DH workshops. Designed by humanities scholars for humanities scholars, DHRIFT provides a minimal computing, accessibility-aware, and interactive environment for teaching fundamental DH concepts.
- Markdown
Each workshop is created using Markdown, a lightweight markup language that is easy to read and write. Markdown allows you to format text, add images, and create links without having to write HTML.
</Keywords>
```

In this example, the `<Keywords>` tag creates a section of key terms, and each term is defined with a bullet point list. This section can help learners understand and remember important concepts from the workshop.

## Adding Your Workshop to Your DHRIFT Site

Once you have reached a point where you are satisfied with your workshop content, you can add your workshop to your DHRIFT site. To do this, you will need to push or upload your workshop markdown file to your GitHub repository. DHRIFT will automatically detect the new workshop file and display it on your site.

To ensure that your workshop is displayed correctly, keep in mind these checks:

- Check that your workshop metadata is correctly configured in the YAML front matter.
- Make sure your workshop markdown files are correctly formatted and free of syntactical errors.
- Prepare all necessary assets (images, downloads, etc.) to be placed in designated folders in your repository.

If everything looks good, there are a few ways you can add your workshop to your repository. If you are familiar with Git and GitHub, you can push your changes directly to your repository using Git commands.

For instance, you can add your files to the staging area, commit your changes, and push them to your repository using the following commands:

```bash
git add -A
git commit -m "Add new workshop"
git push
```

[VSCode](https://code.visualstudio.com/) also has a built-in Git interface that you can use to stage, commit, and push your changes.

If you are less familiar with Git or are not using VSCode, you can also use the GitHub web interface to upload your files directly to your repository. Simply navigate to your repository on GitHub, click the "Add file" button, and select "Upload files" to add your workshop markdown file. Make sure you are also adding any images or other assets to the correct folders in your repository.

### Reviewing Your Workshop

To see your workshop in action, you can navigate to your DHRIFT site and check the workshops page. Your new workshop should appear in the list of available workshops, and you should be able to click on it to view the workshop content. Make sure your DHRIFT site is pointed to the correct repository and branch where your workshop files are stored (please see the "Setting up Your Workshop Repository" section if you need a refresher on how to point to your repo).

