# Getting started

1. Install TypeScript, globally is fine for testing purposes, but it's recommended to have a project installation for development.
        ```
        // Global installation
        $ npm install -g typescript

        // Project installation
        $ npm install typescript
        ```

2. Create your TypeScript files with the `.ts` extension. See the `src/` folder for a sample file.

3. The configuration for TypeScript compiling is defined in the `tsconfig.json` file, a repository can have many and they support inheritance.

4. A default `tsconfig.json` file can be created using the following command:
        ```
        $ tsc --init
        ```
