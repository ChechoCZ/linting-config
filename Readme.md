## EditorConfig, ESLint, Prettier

### 1. EditorConfig:
  - Install editor config extension in VSCode.
  - Right click over file explorer and select ```Generate .editorconfig```

### 2. ESLint:
  - ```shell 
      yarn add eslint -D
    ```

  - ```shell 
      yarn eslint --init
    ```
    - *To check syntax, find problems and enforce code style*
    - *Javascript modules (import/export)*
    - *None of these*
    - **Typescript?** *Yes*
    - *Node/Browser*
    - *Use a popular style guide*
    - Airbnb
    - JSON
    - Install dependencies using ***npm***? Yes
    - ```yarn add eslint-import-resolver-typescript -D```
      <br />
      **In NODE**
      Add to .eslintrc.json file:
        - ```json
            "extends": [
              ...,
              "plugin:@typescript-eslint/recommended"
            ]
          ```
        - ```json
            "settings": {
              "import/resolver": {
                "typescript": {}
              }
            }
          ```
        - ```json
            "rules": {
              "import/extensions": [
                "error",
                "ignorePackages",
                {
                  "ts": "never"
                }
              ]
            }
          ```
        - settings: (right below rules)
          ```json
            "settings": {
              "import/resolver": {
                "typescript": {}
              }
            }
          ```
        
      **In ReactJS**
      Remove from package.json:
        - ```json
            "eslintConfig": {
              "extends": [
                "react-app",
                "react-app/jest"
              ]
            }
          ```

      Add to .eslintrc.json file:
        - ```json 
            "extends": [
              ...,
              "plugin:@typescript-eslint/recommended"
            ]
          ```
        - ```json 
            "plugins": [
              ...,
              "react-hooks"
            ]
          ```
        - ```json
            "rules": {
              "react-hooks/rules-of-hooks": "error",
              "react-hooks/exhaustive-deps": "warn",
              "react/jsx-filename-extension": [
                1, 
                { 
                  "extensions": [".tsx"] 
                }
              ],
              "import/prefer-default-export": "off",
              "camelcase": "off",
              "@typescript-eslint/ban-types": "off",
              "import/extensions": [
                "error",
                "ignorePackages",
                {
                  "ts": "never",
                  "tsx": "never"
                }
              ]
            }
          ```
        - settings: (right below rules)
          ```json
            "settings": {
              "import/resolver": {
                "typescript": {}
              }
            }
          ```

### 3. Prettier:
  - ```shell
      yarn add prettier eslint-config-prettier eslint-plugin-prettier -D
    ```
  - ```json 
      "extends": [
        ...,
        "prettier/@typescript-eslint",
        "plugin:prettier/recommended"
      ]
    ```
  - ```json 
      "plugins": [
        ...,
        "prettier"
      ]
    ```
  - ```json
      "rules": {
        ...
        "prettier/prettier": "error"
      }
    ```

  - Create a ```prettier.config.js``` file in the root of the directory and add the following code:
    ```js
      module.exports = {
        singleQuote: true, 
        trailingComma: 'all',
        arrowParens: 'avoid',
      }
    ```
