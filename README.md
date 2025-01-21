
# Info

This is a major mode for perl, designed to be similar to cperl-mode.
The major difference is that this mode uses a parser(done by
treesitter) to provide it's features, instead of it based all on
regexps.

# Prerequisets

Just execute the following code and you should be ready to go.

```elisp
(add-to-list 'treesit-language-source-alist
	     '(perl . ("https://github.com/tree-sitter-perl/tree-sitter-perl" "release")))
(add-to-list 'treesit-language-source-alist
	     '(pod . ("https://github.com/tree-sitter-perl/tree-sitter-pod" "release")))
(treesit-install-language-grammar 'perl)
(treesit-install-language-grammar 'pod)
```

# Usage

## Navigation

Should be pretty intutive, you use M-e and M-a to navigate around
PODs.  This package also provides proper sexp navigation for perl.  In
the following code:

```perl
my $r = join '-', @arr + 2 - 1;
```
The sexps would be:
```
((my) ($r) = ((join) '-', (((@arr) + (2)) - (1))));
```

Commands like `C-M-b` and `C-M-f` will reflect on this.

## Imenu

The imenu settings should work as expected, similar to how cperl-mode
does it.


# Warning

As of 2025-01-06, the treesit ranges are unstable.  Also being worked
on.

Due to some major [perfomance
issues](https://github.com/tree-sitter-perl/tree-sitter-perl/issues/203)
with the grammer, it is not advisable to use this if you will be
working on large files.  As of 2025-01-21, these are being worked on
rapidly.
