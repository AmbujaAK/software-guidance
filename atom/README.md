# Atom
> **How to Install Atom text editor on your System**
- Download *Atom* from [here](https://atom.io/)
- Install it on your System.
- It's done.

> **How to Use Git in Atom**
- Follow the given steps to use git in atom.
    1. In case a project doesn't have a Git repository yet, you can create one (say **Demo** ) from the Git panel.
        - Open the **Git** panel : `ctrl+9`
        - Open the **GitHub** panel : `ctrl+8`
    2. You also need to create the same repository from github account.  
    3. Now Open Demo repository in atom, you will see a `.git` file.
    4. Open **config** file .
    5. Add the following line in it :
    ```    
        [remote "origin"]
            url = "REPOSITORY_LINK"
        [branch "master"]
            remote = origin
    ```
    6. Now you first **pull** the previously loaded file on github account (like *README.md* file)