# `init` command

LDO's cli's create command initializes a package and repsoitory to upload your own shapes.

The command is intended to be run using NPX. For example:

```bash
npx @ldo/cli create ./my_project
cd ./my_project
```

This command will create a `.shapes` and `.ldo` folder that will store the schemas and generated code for LDO respectively.

## Modify the project

You can modify the project by adding shapes to the `.shapes` folder and running `npm run build:ldo`.

## Publish to NPM

To publish your shapes to NPM, run `npm run publish`.
