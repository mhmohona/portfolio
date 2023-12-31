# Exploring the Pywikibot API

## Introduction

[Pywikibot](https://www.mediawiki.org/wiki/Manual:Pywikibot) is a dynamic Python library offering a suite of tools for automating tasks on MediaWiki sites. This guide provides detailed insights into the Pywikibot API, helping developers streamline their wiki-based operations.

## Pywikibot: Understanding the API

Pywikibot's API, directly linked with [MediaWiki](https://www.mediawiki.org/wiki/API:Main_page), facilitates automated tasks like content editing and data extraction using Python methods and classes.

**Key API Features:**
- Interaction with MediaWiki's API endpoints.
- Easy-to-use methods for tasks such as editing and uploading.
- Custom bot creation and site management tools.

**API Use Cases:** 
- Bulk updating and creating wiki pages.
- Extracting and analyzing data from wiki pages.
- Managing user activities and site maintenance tasks.

## Setting Up Pywikibot

**Installation and Configuration:**

  ```shell
  pip install pywikibot
  python -m pywikibot -generate_user_files
  # Follow the setup instruction to authenticate with the MediaWiki API
  ```

## Exploring API Functionalities

1. **Site Object API Usage**
   - Connect to and interact with MediaWiki sites.
   - This code establishes a connection to the English Wikipedia and displays its name and available languages.
     
     ```python
     from pywikibot import Site
     site = Site('en', 'wikipedia')
     print(site.sitename(), site.languages())
     ```
   - The diagram shows the process of connecting to a MediaWiki site and performing operations on it:
     
     ```mermaid
     graph TD
       A[Initialize Site Object] --> B[Connect to MediaWiki]
       B --> C[Perform Site Operations]
     ```

2. **Page Object for Editing and Creation**: Manage and edit individual wiki pages.
   
   Here, a new page is created, filled with content, and saved in bellow code example:
     
     ```python
     from pywikibot import Page
     new_page = Page(site, 'New Page Title')
     new_page.text = 'This is the content of the new page.'
     new_page.save('Creating a new page using Pywikibot')
     ```
   
    This sequence shows creating a page, editing it, and then saving the changes:
     
     ```mermaid
     sequenceDiagram
       participant User
       participant Pywikibot
       User->>Pywikibot: Create Page Object
       Pywikibot->>User: Edit Page Content
       User->>Pywikibot: Save Changes
     ```

3. **Category Object for Organizing Content**: Organize and manage wiki categories.

    The example lists titles of all pages in a specific category:
     
     ```python
     from pywikibot import Category
     category = Category(site, 'Category:Technology')
     for page in category.articles():
         print(page.title())
     ```

   This flowchart shows how to work with categories, including listing and managing pages in them:
     
     ```mermaid
     graph TD
       A[Create Category Object] --> B[List Category Members]
       B --> C[Manage Category Pages]
     ```

4. **User Object for Analyzing Contributions**: Represents and analyzes wiki user activities.

    This code snippet shows a user's contribution count:
     
     ```python
     from pywikibot import User
     user = User(site, 'ExampleUser')
     print('User contributions:', user.editCount())
     ```
   
   The diagram shows the steps to initialize a user object and query their contribution data:
     
     ```mermaid
     graph TB
       A[Initialize User Object] --> B[Query User Data]
       B --> C[Analyze Contributions]
     ```

5. **File Management with Image/File Object**: Handle file uploads and downloads on the wiki.

    The code here retrieves and displays pages using a specific image:
     
     ```python
     from pywikibot import FilePage
     file_page = FilePage(site, 'File:ExampleImage.jpg')
     print('Image usage:', file_page.usingPages())
     ```
   
    This diagram shows the process of managing files, including uploading or downloading them:
     
     ```mermaid
     graph TD
       A[Create FilePage Object] --> B[Download or Upload File]
       B --> C[Analyze File Usage]
     ```

The Pywikibot API is a powerful tool for automating MediaWiki tasks. This guide offers a roadmap for utilizing the API for a variety of operations, from simple tasks to complex automation.
