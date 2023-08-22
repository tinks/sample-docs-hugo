# Sample documentation

I use this repository to create sample documentation to show to potential new employers.

## Dependencies

* [Hugo](https://gohugo.io)
* [Docsy](https://themes.gohugo.io/docsy/) (a Hugo theme)
* Autoprefixer (needed by PostCSS)
* PostCSS

## Prerequisites

* Git
* Hugo (version 0.107.0 extended or higher)</br>
  `brew install hugo`
* Node (version 16 or higher)</br>
  `brew install node`
* go (version 1.17 or higher)</br>
  `brew install go`

## Modules

When hugo is run, it pulls in modules defined in `go.mod`. Modules are defined to pull in a specific version of:

* Docsy: the theme used in the output
* RapiDoc: used to show the OpenAPI specs written for the REST APIs

These modules should be updated from time to time to get the latest version. To update the modules, run the following command:

```zsh
hugo mod get -u
```

## Project set up + test

1. Clone the repo and initiate the git submodules (to get the Docsy theme) </br>

   ```zsh
   git clone ...
   cd sample-docs
   ```
1. Fetch the modules needed</br>
   `hugo mod get`
1. Start a Hugo server</br>
   `hugo server -D`
1. Browse to `localhost:1313/sample-docs` to see the output

## Build

### Locally

1. Install the necessary packages: `npm install`.
1. To build locally: `hugo -d public/sample-docs`

To also build pages still in draft, add `-D` to the command: `hugo -D -d public-sample-docs`.

The output is stored in the `public` folder. To view the built documentation, start a server in this folder. For example, you can do this with the following command (available in Python 3):

`python -m http.server 8000` --> server available at `localhost:8000/sample-docs`

### Publish

Documentation is automatically published to GitHub pages when merging or pushing to `main`.