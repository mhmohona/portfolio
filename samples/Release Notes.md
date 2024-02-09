# Rasa v2 to v3: Guide to new releases

Today we’re going to explore some exciting new features in the latest version of Rasa v3, an open-source machine learning platform that automates text and voice-based conversations Whether to dive deeper into chatbots, voice assistants, or just natural language processing, this blog post it will give you an insight into the upcoming changes and improvements to Rasa v3.

## What's new in Rasa v3?

Rasa v3 comes packed with improvements and new features that further advance conversational AI development. Let’s take a closer look at some of the key changes:

### Documentation

The documentation has seen significant updates, making it easier for both beginners and experienced users to navigate and understand the framework.

### Indifference and Removal

- Remove several deprecated features, including support for Python 3.6 which reached the end of life in December 2021.
- The Markdown training data format has been phased out, affecting story files, NLU data, and retrieval intent data.
- Some methods and functions, such as `sorted_intent_examples` and `change_form_to`, have been deprecated and later removed.

### Improvements and Bug Fixes

- Changed the names of CLI parameters to use dashes instead of underscores, in keeping with GNU standards.
- `rasa train` command now uses a fallback config an invalid one is provided.
- Added SSL support for the `rasa run` command, allowing secure connections.
- Implemented several bug fixes that address compatibility issues and improve overall stability.

### New Features

- The `rasa run` command now accepts arguments indicating the Rasa X port when running locally.
- New features like `utter_elements()` have been introduced, replacing older methods in the `rasa_core_sdk`.

## Why upgrade?

Upgrading to Rasa v3 isn’t just about getting the latest features; It’s about ensuring that your conversational AI projects stay current with best practices and developments in the industry. By removing obsolete features and improving documentation, Rasa v3 establishes itself as a solid foundation for future improvements and innovations

## Starting with Rasa v3

If you are new to Rasa or considering an upgrade, here are the steps to get started.

1. See the [Rasa v3 documentation](https://rasa.com/docs/rasa/next/index.html) for a detailed understanding of the new features and changes.
2. Refer to the [migration guide](https://rasa.com/docs/rasa/migrate-3.x/) to understand how to migrate your existing Rasa v2 projects to v3.
3. Update your Rasa installation to the latest version using pip:

```bash
pip install --upgrade pip
```

4. Refactor your codebase according to the deprecations and removals listed in the changelog.
5. Carefully test your new configuration to ensure that all components are working as expected.

Rasa v3 marks a milestone in the evolution of the Rasa framework, bringing many enhancements enhancements to make it an extremely powerful tool for building intelligent chat workers Whether you’re an expert or just starting in Rasa for free, updating to the latest version is the step to use the full capabilities of the system.