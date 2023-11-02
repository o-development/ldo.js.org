# @ldo/cli

The `@ldo/cli` is a command line interface for initializing LDO and building ShapeTypes.

## Setup

### Automatic Setup
To setup LDO, `cd` into your typescript project and run `npx @ldo/cli init`.

```bash
cd my-typescript-project
npx @ldo/cli init
```

### Manual Setup
The following is handled by the __automatic setup__:

Install the LDO dependencies.
```bash
npm install @ldo/ldo
npm install @ldo/cli --save-dev
```

Create a folder to store your ShEx shapes:
```bash
mkdir shapes
```

Create a script to build ShEx shapes and convert them into Linked Data Objects. You can put this script in `package.json`
```json
{
  ...
  scripts: {
    ...
    "build:ldo": "ldo build --input ./shapes --output ./ldo"
    ...
  }
  ...
}
```

## Generating a ShapeType

@ldo/cli generates shape types using the `*.shex` files in the "input" folder. If you followed the instructions above, run the following command:

```bash
npm run build:ldo
```

This will generate five files:
 - `./ldo/foafProfile.shapeTypes.ts` <-- This is the important file
 - `./ldo/foafProfile.typings.ts`
 - `./ldo/foafProfile.schema.ts`
 - `./ldo/foafProfile.context.ts`

## API Details
 - [`init` command](init.md)
 - [`build` command](build.md)