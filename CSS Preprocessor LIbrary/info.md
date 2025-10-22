# SCSS Compilation

**What it is:**

SCSS Compilation is the process of converting **Sassy Cascading Style Sheets (SCSS)** into standard **Cascading Style Sheets (CSS)** that browsers can understand.  
There are generally **two common ways** to perform this compilation:

---

### **1. Using the Command Line (CLI)**

You can compile a single SCSS file manually or watch it continuously for changes.

```bash
# One-time compilation
sass style.scss style.css

# Watch mode (auto-compiles on every save)
sass --watch input.scss:output.css
```

### **2. Using a Build Tool or Bundler (e.g., Vite, Webpack)**

You can add scripts on the bundlers. It will automatically converts sass when you run commands like _npm run build_

```bash
"scripts": {
  "sass": "sass --watch scss/:css/",
  "build": "sass scss/:css/ && npm run bundle"
}
```
