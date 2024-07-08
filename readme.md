# README

## ⚙️ Prerequisites

You need to have these prerequisites installed on your machine.

- [Hugo Extended](https://gohugo.io/installation/)
- [Node](https://nodejs.org/en/download/)
- [Go](https://go.dev/doc/install)

## 👉 Setup

Download the app.

```bash
gh repo clone pacificalabs/site
cd site
```

Install all the dependencies using the following command.

```bash
npm install
```

### 👉 Development Command

Start the development server using the following command.

```bash
npm run dev
```

---

## 🛠 Advanced Usage

You can use these scripts to help you with your development.

### 👉 Update Theme

If you want to update the theme, then you can use the following command. It will update the theme to the latest version.

```bash
npm run update-theme
```

> **Note:** This command will work after running `project-setup` script.

### 👉 Update Modules

You can update all the modules using the following command.

```bash
npm run update-modules
```

> **Note:** This command will work before running `project-setup` script. If you already run the `project-setup` command, then you have to run `npm run theme-setup` first, and then you can run this command. afterward, you can run `npm run project-setup` again.

---

### 👉 Build Command

To build your project locally, you can use the following command. It will purge all the unused CSS and minify all the files.

```bash
npm run build
```
