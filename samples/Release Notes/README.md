# Transitioning from Rasa v2 to v3: A Guide to the New Release

Hello Rasa enthusiasts! Today, we're going to explore the exciting updates in Rasa v3, the latest version of the open-source machine learning framework for automating text and voice-based conversations. Whether you're developing chatbots, voice assistants, or simply diving deeper into natural language processing, this blog post will give you an insight into the changes and improvements that come with Rasa v3.

## What's New in Rasa v3?

Rasa v3 comes packed with a host of improvements and new features that make it a leap forward in the development of conversational AI. Let's take a closer look at some of the key changes:

### Enhanced Documentation

- The documentation has seen significant updates, making it easier for both beginners and experienced users to navigate and understand the framework.

### Deprecations and Removals

- Several deprecated features have been removed, including support for Python 3.6, which reached its end of life in December 2021.
- The Markdown training data format has been phased out, which affects story files, NLU data, and retrieval intent data.
- Some methods and functionalities, such as `sorted_intent_examples` and `change_form_to`, have been deprecated and subsequently removed.

### Improvements and Bugfixes

- CLI parameters have been renamed to use dashes instead of underscores, aligning with GNU standards.
- The `rasa train` command now uses a fallback config if an invalid one is provided.
- SSL support has been added for the `rasa run` command, allowing for secure connections.
- Several bug fixes have been implemented, addressing compatibility issues and improving overall stability.

### New Features

- The `rasa run` command now accepts arguments for specifying the port of Rasa X when running it locally.
- New features like `utter_elements()` have been introduced, replacing older methods in the `rasa_core_sdk`.

## Why Upgrade to Rasa v3?

Upgrading to Rasa v3 is not just about getting the latest features; it's about ensuring that your conversational AI projects stay current with the best practices and advancements in the field. With the removal of deprecated features and improvements to documentation, Rasa v3 positions itself as a solid foundation for future growth and innovation.

## Getting Started with Rasa v3

If you're new to Rasa or considering an upgrade, here are the steps to get started:

1. Check the [Rasa v3 documentation](https://rasa.com/docs/rasa/next/index.html) for a detailed understanding of the new features and changes.
2. Review the [migration guide](https://rasa.com/docs/rasa/migrate-3.x/) to understand how to adapt your existing Rasa v2 projects to v3.
3. Update your Rasa installation to the latest version using pip:

```bash
pip install --upgrade rasa
```

4. Refactor your codebase according to the deprecations and removals listed in the changelog.
5. Test your new setup thoroughly to ensure that all components are functioning as expected.

## Conclusion

Rasa v3 marks a significant milestone in the development of the Rasa framework, bringing numerous enhancements and improvements that make it an even more powerful tool for creating intelligent conversational agents. Whether you're a seasoned developer or just getting started with Rasa, upgrading to the latest version is a move towards harnessing the full potential of the framework.

Thank you for joining us on this journey through the new Rasa v3 release. We hope this guide has helped you understand the exciting changes that come with Rasa v3 and encouraged you to embrace the future of conversational AI. Keep exploring, keep building, and keep pushing the boundaries of what's possible with Rasa!
