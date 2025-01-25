# Setting up a Dev Container for Rust

* Primary author: [Lizzie Coats](https://github.com/escoats)
* Reviewer: [Caroline Bryan](https://github.com/cgbryan1)
* Adapted from [*COMP 423: Starting a Static Website Project with MKDocs*](https://comp423-25s.github.io/resources/MkDocs/tutorial/)

``` rust
// This is an example of a code block!
println("Hello World!")
```

## Prerequisites
Before getting started, make sure you've done the following:  

* Create a [Github](https://github.com) Account
* Install VSCode
* Install Git
* Install Docker Desktop

## **Setup: Creating a Repository** 🚧 🚜
### 1. Create Local Directory and Initialize Git  

In your terminal, create a new directory for your project: 

```
mkdir rust-project
cd rust-project
```

Initialize a new Git repository:
```
git init
```
Finally, create a README file and commit it to your repository:
```
echo "# Rust Project" > README.md
git add .
git commit -m "Add README"

```
### 2. Create Remote Repository
On GitHub, create a new repository:
>
>*  _Name:_ `rust-project`
>*  _Description:_ "My rust project!"
>
>Do not initialize the repository with a README - we already created one locally!

### 3. Link Local Repository to GitHub
In your project directory, add the GitHub repository as a remote:
```
git remote add origin https://github.com/<username>/rust-project.git
```

Push your commits to your remote repository:
```
git push -u origin main
```

## **Configure Dev Container** 🐳 🚢
### 1. Add Dev Container Configuration
Open your `rust-project` directory in VSCode. 
Install the *Dev Containers* extension for VSCode.
Cretae a `.devcontainer` directory in the root of your prokect. Inside, create a file called `devcontainer.json`.

The `devcontainer.json` file contains the configuration for your development environment: 

```
{
  "name": "My Rust Project",
  "image": "mcr.microsoft.com/vscode/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["rust-lang.rust-analyzer"]
    }
  }
}
```

### 2. Reopen Project in Dev Container
In the VSCode command palette (`Ctrl+Shift+P`), type "Dev Containers: Reopen in Container."

Make sure your dev container is running a recent version of Rust with `rustc --version` (The most recent version released is 1.84.0).

## **Hello World!** 👋 🌎
1. To create a binary project, run `cargo new <project-name> --vcs none`.
```rust
cargo new hello-world --vcs none
```

2. cd into your new package: `cd hello-world`.  


3. Edit your `main.rs` file to contain the following:
```rust
fn main() {
    println!("Hello COMP423!");
}
```

4. Build your file with `cargo build`. This command compiles your human-readable program (Rust code) and links any necessary dependencies, turning them into an executable file (binary).  


5. Run your file with `cargo run`. This command runs the file created in the previous step!  
Your output should be:
```
Hello COMP423!
```
6. If your output matches, you've successfully set up a dev container for Rust!