# Setting up a dev container for Rust

* Primary author: [Lizzie Coats](https://github.com/escoats)
* Reviewer: [Caroline Bryan](https://github.com/cgbryan1)
* Adapted from [*COMP 423: Starting a Static Website Project with MKDocs*](https://comp423-25s.github.io/resources/MkDocs/tutorial/)

``` rust
// This is an example of a code block!
println("Hello World!")
```

## Prerequisites🫦
1. GitHub Account
2. Git installed
3. VSCode installed
4. Docker installed
5. Basic command-line proficiency

## Setup: Creating a Repository🕳️🚶‍♀️
### 1. Create Local Directory and Initialize Git
Create a new directory for your project: 

```
mkdir rust-project
cd rust-project
```

Initialize a new Git repository:
```
git init
```
### 2. Create Remote Repository
### 3. Link Local Repository to GitHub

## Configure Dev Container💃
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
### 2. **(remove?)** Add `requirements.txt` Dependency Configuration
### 3. Reopen Project in Dev Container
In the VSCode command palette (`Ctrl+Shift+P`), type "Dev Containers: Reopen in Container."

Make sure your dev container is running a recent version of Rust with `rustc --version`.

## Hello World!👋🌎
To create a binary project, run `cargo new <project-name> --vcs none`.

```rust
cargo new hello-world --vcs none
```

cd into your new package: `cd hello-world`

Your `main.rs` file should contain the following:
```rust

fn main() {
    println!("Hello COMP423!");
}
```

Build your file with `cargo build`. 
**ADD INSTRUCTIONS FOR THIS!**

Run your file with `cargo run`
**discuss difference from build**

Your output should be:
```
Hello COMP423!
```

All done!