Superscript for Markdown-IT-Py
==============================

This is a plugin for the Python implementation of
`Markdown-IT <https://github.com/executablebooks/markdown-it-py>`_ (a CommonMark
parser) that provides superscript (``<sup>``) via carets (``^``).

Markup is based on the `Pandoc superscript extension
<https://pandoc.org/MANUAL.html#superscripts-and-subscripts>`_.

Place superscripted text within caret ``^`` characters. You must escape any
spaces in the superscripted text. Note that you cannot use newline or tab
characters, and that nested markup is not supported.

Example usage::

    >>> from markdown_it import MarkdownIt
    >>> from minchin.md_it.superscript import superscript_plugin
    >>> md = MarkdownIt().use(superscript_plugin)
    >>> md.render("1^st^")
    '<p>1<sup>st</sup></p>\\n'
    >>> md.render("this^text\\\\ has\\\\ spaces^")
    '<p>this<sup>text has spaces</sup></p>\\n'

Tests can be run using ``pytest``.


For whatever reason, subscript was added to the "official" *mdit-py-plugins*
collection, but superscript has been langishing as an open pull reqest for the
past six months. This is meant as an interim measure so I can make use of the
plugin locally, until such time as the upstream pull request lands. Maybe
you'll find it helpful too!
