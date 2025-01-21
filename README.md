# Prerequisets

Do similar thing with pod grammer.

```elisp
  (setq treesit-language-source-alist
    '((perl . ("https://github.com/tree-sitter-perl/tree-sitter-perl" "release"))))
  (treesit-install-language-grammar 'perl)
```

# Usage

Should be pretty intutive, you use M-e and M-a to navigate around PODs.

# Warning

As of 2025-01-06, the treesit ranges are extremly unstable
