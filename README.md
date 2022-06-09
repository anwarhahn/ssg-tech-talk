# Static Site Generation (SSG) Tech Talk

Anwar Hahn (2022-06-09)

_References_

1. https://github.com/pyenv/pyenv
2. https://www.mkdocs.org/getting-started/
3. https://firebase.google.com/docs/hosting
4. https://github.com/squidfunk/mkdocs-material

# Goals

Create a static site using markdown in the next 15 minutes.

This is interactive so everyone can follow along!

# Steps

1. Make a directory to hold our files. Change into that directory.

```bash
mkdir ssg-tech-talk && cd ssg-tech-talk
```

2. Make a virtual environment for python. You may need to run `deactivate` first.

```bash
mkvirtualenv ssg-tech-talk --python=/Users/anwarhahn/.pyenv/versions/3.7.2/bin/python
```

3. Install `mkdocs` and `mkdocs-material`.

```bash
pip install mkdocs
pip install mkdocs-material
```

4. Create a git repo.

```bash
git init
echo "site/" >> .gitignore
```

5. Create a new project.

```bash
mkdocs new my-project
cd my-project
```

6. Serve the page locally. And check the results.

```bash
mkdocs serve
```

7. Use `CTRL+C` to stop the server.

8. Commit our changes.

```bash
git add ..
git commit -m "initial commit"
```

9. Let's build our static site.

```bash
mkdocs build
```

10. Poke around in the `site/` directory.

11. Install the Firebase CLI. https://firebase.google.com/docs/cli#mac-linux-npm

```bash
npm install -g firebase-tools
```

12. Login and test the Firebase CLI. https://firebase.google.com/docs/cli#sign-in-test-cli

```bash
firebase login

? Allow Firebase to collect CLI usage and error reporting information? No
```

13. Initialize the firebase project. https://firebase.google.com/docs/cli#initialize_a_firebase_project

```bash
cd ..
firebase init

❯◯ Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys

❯ Create a new project

? Please specify a unique project id (warning: cannot be modified afterward) [6-30 characters]:
 () ssg-tech-talk
```

14. If you run into an error then go to https://console.firebase.google.com/

And then run

```bash
firebase init
```

15. Deploy

```bash
mkdocs build && firebase deploy
```

16. Change the theme https://github.com/squidfunk/mkdocs-material

```bash
pip install mkdocs-material
```

17. Add the following lines to `mkdocs.yml`:

```yaml
theme:
  name: material
```

18. Review the other settings in `mkdocs.yml`.
19. Consider adding a `Makefile`.
20. Add some new pages and change the navigation layout.
21. Add some additional CSS.
