```bash
node -v

# create the package.json file
npm init

# install sass locally
# deprecated!
npm install node-sass --save-dev


# new
npm install sass

# use this more than above
# development that will help build the project
npm install sass --save-dev

# dont need to include the nodemodules and just use this code to install when using other devices
# if you deleted the node_modules folder and want to reinstall the packages again
npm install

# to uninstall something completely
# save keyword is important

npm uinstall <packagename> --save
```

---

Yes, you can use `--save-dev` when installing `sass` if you only need it as a development dependency. This is typically the case if you're using Sass to compile SCSS files into CSS during development and not in the production environment.

Here’s how to do it:

---

### **Install `sass` as a Development Dependency**

Run the following command:

```bash
npm install sass --save-dev
```

---

### **Why Use `--save-dev`?**

- **Development Dependency (`--save-dev`)**:

  - Use this if the package is only needed for development purposes, such as compiling SCSS files.
  - Example: Your project’s production build only needs the resulting CSS file, not the `sass` tool itself.

- **Production Dependency (`--save` or default)**:
  - Use this if the package is required in the production environment. This applies if `sass` is part of your runtime (e.g., dynamically compiling SCSS at runtime in a server environment).

---

### **What Happens in `package.json`?**

With `--save-dev`, `sass` will be added under `devDependencies`:

```json
"devDependencies": {
  "sass": "^1.64.2"
}
```

If you don’t use `--save-dev`, it will be added under `dependencies`:

```json
"dependencies": {
  "sass": "^1.64.2"
}
```

---

### **How to Decide?**

- **Use `--save-dev`** if you’re compiling SCSS into CSS as part of your build process.
- **Use `--save`** if you need `sass` during runtime (e.g., in a live application that processes SCSS on-the-fly).

---

How to compile sass you created?

- Change the scripts in package.json

```json
  "scripts": {
  "compile:sass": "sass sass/main.scss css/style.css"
  },
```

then use this instead

```json
    "compile:sass": "sass sass/main.scss css/style.css -w"
```

this keep watching whatever we do in our code
please do not close the terminal as you need to see the changes
just open a new tab to do other things

to make it work. go to terminal and use:

```bash
npm run compile:sass
```
