# Stefandango.dev DOC template

My tweaked docfx template. 

- Uses a custom logo
- Generates a PDF using wkhtmltopdf

This project consist of the docfx project and a very basic webservice project used to test how code documentation is generated.

## Installation

DocFX is installed using the Nuget package docfx.console. Also docfx need to be installed, take a look at the [DocFX documentation](https://dotnet.github.io/docfx/)

Furthermore [wkhtmltopdf.exe](https://wkhtmltopdf.org/) must also be found in the PATH variable for the PDF to be generated. 

## Configuration

Basic configuration is made in the docfx.json (part of the Stefandango.doc project)
Most important sections are the files section.

```
 "metadata": [
    {
      "src": [
        {
          "files": [
            "**.csproj",
            "Stefandango.Doc.ExampleProject/*.csproj"
```

This should point to the .csproj of the project that docfx should include in the documentation.

Furthermore I have made a few custom variables that should be changed to the project name of the documentation. 
```
"globalMetadata": {
    "_appName": "Stefandango.Doc",
    "_appFooter": "<span>Stefandango Copyright</span>",
    "_appLogoPath": "/images/logo_white.svg"
}
```

Additionally content should be added in the articles folder using markdown. 

The PDF uses the various templates in the PDF folder, which should be changed to fit the current project as well.

## Usage

Build the project, and if succesful run the serve command

```
docfx.exe --serve
```