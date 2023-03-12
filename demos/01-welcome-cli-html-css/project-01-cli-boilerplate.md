# project-01 Boilerplate Using CLI

1. Use `pwd` to make sure you're in the correct directory.
   1. If you're in the directory you want to be in move on to the next step.
   2. If you're in the wrong directory, use `cd` to navigate to the one <br/>you want to be in.
   3. If the directory doesn't exist. Create a new one where you want it.
      1. `mkdir course-work` You can use a different directory name if <br/>you'd like.
      2. `cd course-work`
      3. Move on to step 2.
2. Once you're in the directory where you want your project to live.
   1. `mkdir project-01`
   2. `cd project-01`
   3. Now that we have our `project-01` directory created, let's add the <br/>different modules we'll be working in throughout the week.
      1. `mkdir module-01 module-02 module-03 personal-site`
      2. To make sure that the correct directories were created, use the <br/>command `ls`.
      3. `cd module-01`
      4. Move on to step 3.
3. Now that we have our `module-01` directory created, let's add some files.
   1. `touch recipe.html encyclopedia.html gallery.html`
   2. Make sure the files were created using the command `ls`.
   3. `cd ..` back into the `project-01` directory.
   4. Move on to step 4.
4. Use the command `pwd` to make sure you're in the correct directory.
   1. After verifying you're in the correct directory, `cd module-02`.
   2. `touch pride.html math.html news.html`
   3. Make sure the files were created using the command `ls`.
   4. Oh, no! We meant for `math.html` to be `math-facts.html`.
   5. Change the name of the file by using the `mv` command.
      1. To rename a file `mv file-name.txt new-file-name.txt`
      2. So, we should use this command `mv math.html math-facts.html`.
      3. Check to make sure the file name was changed using `ls`.
      4. Move on to the next step.
   6. Now that everything looks good in this directory, let's change into <br/>`module-03` using the relative path. `cd ../module-03`.
5. Make sure you're in the correct directory.
   1. Create the following files `user-profile.html message-form.html`.
   2. Make sure they were created properly, and then change directories into <br/>`personal-site`.
   3. Move on to the next step.
6. Create the following files: <br/>`index.html about.html portfolio.html index.css about.css portfolio.css site.css`
7. Congratulations you should now have a directory tree that looks like this!

```
course-work
└── project-01
    ├── module-01
    │   ├── encyclopedia.html
    │   ├── gallery.html
    │   └── recipe.html
    ├── module-02
    │   ├── math-facts.html
    │   ├── news.html
    │   └── pride.html
    ├── module-03
    │   ├── message-form.html
    │   └── user-profile.html
    └── personal-site
        ├── about.css
        ├── about.html
        ├── index.css
        ├── index.html
        ├── portfolio.css
        ├── portfolio.html
        └── site.css

5 directories, 15 files
```
