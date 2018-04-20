# Git Style Guide

This is a sample GitCop configuration that check commits according to this style guide.

## Header

```
There are some issues with your commit and our naming convention
```

## Subject Length

```
50
```

```
Good titles doesn't exceed 50 characters. To add more details use the body!
```

## Subject format

```
%{scope}: %{type} %{description}
```

```
Always use the standard `scope: action description`, always in english
    - The **scope** shouldn't have spaces. If the word is composite, use dashes.
    - The **action** should be **add**, **remove**, **refactor**, **move**,  **bump**, **update** or **release**
    - The **description** should contain a quick description of the change
```

## Valid Types

```
add, remove, refactor, move,  bump, update or release
```

```
Always use the standard `scope: action description`, sempre em inglês
    - The **scope** shouldn't have spaces. If the word is composite, use dashes.
    - The **action** should be **add**, **remove**, **refactor**, **move**,  **bump**, **update** or **release**
    - The **description** should contain a quick description of the change
```

## Body length

```
72
```

```
Don't use more than 72 characters per line in the body of your commit. If you reach this limit at the same line, just break and continue at next line. To separate paragraphs, leave a blank line between them.
```

## Footer

```
The complete commit style guide is available at https://github.com/pagarme/git-style-guide
```
