[![Build Status](https://travis-ci.org/edkolev/evil-lion.svg?branch=master)](https://travis-ci.org/edkolev/evil-lion)
[![MELPA](http://melpa.milkbox.net/packages/evil-lion-badge.svg)](http://melpa.milkbox.net/#/evil-lion)

![Emacs evil alignment operator](https://cloud.githubusercontent.com/assets/1532071/23845388/6edda00c-07d0-11e7-9ea1-ffa945f03980.png)

evil-lion
=========

This package provides `gl` and `gL` align operators: `gl MOTION CHAR` and right-align `gL MOTION CHAR`.

Use CHAR `/` to enter regular expression if a single character wouldn't suffice.

Use CHAR `RET` to align with align.el's default rules for the active major mode.

Port of [vim-lion](https://github.com/tommcdo/vim-lion)

![scar](https://cloud.githubusercontent.com/assets/1532071/23858247/7f33c4c6-0808-11e7-822c-e63c787c2f2b.png)

Installation
------------

#### with [use-package](https://github.com/jwiegley/use-package)
``` emacs-lisp
(use-package evil-lion
  :ensure t
  :config
  (evil-lion-mode))
```

#### without [use-package](https://github.com/jwiegley/use-package)

`M-x package-install RET evil-lion RET`, then add in `init.el`:

`(evil-lion-mode)`

Usage
-----

Align with `gl MOTION CHAR` or right-align with `gL MOTION CHAR`.
If the align separator is `/` you will be prompted for a regular expression instead of a plain character.
If the align separator is `RET` alignment will be performed with align.el's rules specific for the major mode.

#### Example, left align `gl`:

After pressing `glip=` (`gl` is the operator, `ip` text object paragraph, `=` separator)
```
one = 1
three = 3
fifteen = 15
```

will become:

```
one     = 1
three   = 3
fifteen = 15
```

#### Example, right align with `gL`:

After pressing `gLip,`
```
one, two, three,
fifteen, sixteen, seventeen
```

will become:

```
one,     two,     three,
fifteen, sixteen, seventeen
```

#### Example, align with major mode's alignment rules:

In perl-mode, after pressing `glib RET` (`RET` is return key, not individal keys):

``` perl
my %hash = (
   a => 1,
   bbb => 2,
   cccc => 3,

   a => 1,
   bbb => 2,
   cccccc => 3
);
```

will become:

``` perl
my $hash = (
   a    => 1,
   bbb  => 2,
   cccc => 3,

   a      => 1,
   bbb    => 2,
   cccccc => 3
););
```
