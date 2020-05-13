# Writing Standards

!!! note
If you add, remove or change the name of a topic document, be sure
to update the `mkdocs.yml` file `Topics` section

## Format

Each of the Topics will include a set of Standards. With each Standard being
defined using the following template:

```text
<Title> (<Reference ID>)

<Description>

Rationale:
  - ...
  - ...

Alternatives:
  - ...
  - ...

Exceptions:
  - ...
  - ...
```

### Title

A short and descriptive title to refer to the standard in conversation

### Reference ID

An ID to use for referencing the standard in other documentation or automation.

### Description

A clear, concise, specific and actionable description of the standard.
Each standard _must_ contain words that clearly direct decision making.
Use words such as shall, must, always and never.

- This ID should _never_ be changed once the standard has been set. If the
  standard is no longer relevant or if the contents has changed significantly,
  the old standard should be retired and replaced with a new standard and new ID.
- Format:
  - &lt;Two Letter Abbreviation>-&lt;Numerical Code>
  - The abbreviation should be reflective of the area the standard is part of.
  - The code is a 3-digit number starting from 100.

### Alternatives

One or more bullets suggesting alternatives for standards that prohibit some choice

### Rationale

One or more bullets describing the reason the standard exists

## Linting

All submissions must be linted using [markdownlint by David Anson](https://github.com/DavidAnson/markdownlint)

- [CLI](https://github.com/igorshubovych/markdownlint-cli)
- [VS Code](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

Note: There's a configuration file in the root of the repository that has some
small tweaks to the format.
