# `init` command

LDO's cli's init command initializes LDO in an existing Typescript project.

The command is intended to be run using NPX __in the same folder as a project's package.json__. For example:

```bash
cd my_project/
npx run @ldo/cli init
```

If `@ldo/cli` is installed globally, the `ldo` command can be used. For example:

```bash
npm i -g @ldo/cli
cd my_project/
ldo init
```

This command will create a `.shapes` and `.ldo` folder that will store the schemas and generated code for LDO respectively.

## Parameters

### `-d [directory]`, `--directory [directory]` (Optional)

The `init` command takes in one parameter: `-d` or `--directory`. If present, the `init` command will create the `.shapes` and `.ldo` folders in the given directory.

```bash
npx run @ldo/cli init --director ./my_cool_dir
```

```bash
ldo init --directory ./my_cool_dir
```

## Further details

The command does the following:

 - Installs `@ldo/ldo` as a dependency
 - Installs `@ldo/cli`, `@types/shexj`, and `@types/jsonld` as dev dependencies
 - Selects a `PARENT_DIRECTORY`
    - If the `--directory` parameter is set, the `PARENT_DIRECTORY` is the given directory.
    - If `src`, `lib`, or `bin` are present in the project, the `PARENT_DIRECTORY` is `src`, `lib`, or `bin` selected in that order.
    - Else the `PARENT_DIRECTORY` is the project's root directory.
 - Creates a file at `PARENT_DIRECTORY/.shapes/foafProfile.shex` to serve as an example ShEx file. (This can be deleted at any time)
 - Adds a build script, `build:ldo`, to `package.json`. For example, if the `PARENT_DIRECTORY` was `foo` the following would be added:
 ```json
 "scripts": {
   ...
   "build:ldo": "ldo build --input foo/.shapes --output foo/.ldo"
 }
 ```
 - Runs the build script, generating the `.ldo` folder