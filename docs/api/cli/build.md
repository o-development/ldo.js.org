# `build` command

LDO's cli's `build`` command takes ShEx schemas from an `--input` folder, and converts them into LDO generated code in the `--output` folder.

If you initialized your project using the [`init` command](init.md), a the build command is already added to your `package.json`. Simply run:

```bash
npm run build:ldo
```

The `build` command can also be run manually. For example: 

```bash
ldo build --input ./.shapes --output ./.ldo
```

This command will create a `.shapes` and `.ldo` folder that will store the schemas and generated code for LDO respectively.

## Parameters

### `-i [directory]`, `--input [directory]`

__Default Value__: `./.shapes``

The input directory. This directory should be filled with `*.shex` files.

### `-o [directory]`, `--output [directory]`

__Default Value__: `./.ldo``

The output directory.