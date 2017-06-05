# Fable samples

## Building and running the samples

- Restore dependencies: `restore.cmd` on Windows or `sh restore.sh` on Unix.
- Start Fable and Webpack dev server: `dotnet fable npm-run start`
- In your browser, open `localhost:8080/[EXAMPLE]` (e.g. `http://localhost:8080/ozmo`)

Any modification you do to the F# code will be reflected in the web page after saving.
If you want to write JS files to disk instead of using the development server,
run `dotnet fable npm-run build`.

## Adding a new sample

- Create a new folder with the sample (take current samples as reference)
- Add the project to the `Fable.Samples.sln` solution (CLI: `dotnet sln Fable.Samples.sln add my-sample.fsproj`)
- Add the sample to the `restore.sh` script
- Add the sample name and the `.fsproj` relative path to the `samples`
   dictionary in `webpack.config.js`.

To reference the resulting bundle from the sample `index.html`, use:

```html
<script src="/build/[sample].js"></script>
```
