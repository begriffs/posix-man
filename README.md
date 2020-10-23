## Man pages for POSIX

These files allow you to easily consult the POSIX documentation for man
sections 1 and 3. It also contains a "section 0" for header files.

It contains Issue 6 (POSIX.1-2001) and Issue 7 (POSIX.1-2008).

### Accessing from vim

Pressing `K` in vim brings up the man page for the word under the cursor.  In
fact, `nK` bring up section `n`. Sadly `0K` does not work, so section 0 is
inaccessible through Vim.

The man pages in the upstream Debian package use sections 0P, 1P, and 3P,
which would be incompatible with vim, so I changed them to plain numbers.

To point Vim to the POSIX man pages, do this:

```bash
git clone https://github.com/begriffs/posix-man
```

Then in your vim configuration (like an ftplugin for c and sh files):

```viml
setlocal keywordprg=man\ -M\ /path/to/posix-man/issue7
```

The irony is not lost on me that -M or MANPATH is not supported by POSIX's own
man interface.

### Alternatives

June Bug's [exman](https://git.causal.agency/exman/about/exman.1) program
allows you to consult multiple sets of man pages on the same system. This
didn't exactly fit the bill for me because I wanted to remove the P from
sections, and also wanted to strip the Linux preamble from the POSIX pages.
