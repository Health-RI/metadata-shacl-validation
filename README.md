# Health-RI Metadata model SHACL validation

:warning: **This repository and all SHACL shapes are still under active development** :warning:

This repository is used to provide SHACL shapes to verify Health-RI and FAIR Data Point RDF files.

The validator itself is available at <https://www.itb.ec.europa.eu/SHACL/healthri/upload>.

## Development

Run `docker compose build && docker compose up` and a validator will be exposed at <http://localhost:8080/shacl/healthri/upload>.

Currently there are two profiles: v.1.0.0 and development. The v1.0.0. profile will validate against the v1.0.0 release SHACLs, 
development will validate against the latest development version. Note: development can contains errors, so use with care!
The SHACLs are retrieved from the github datamodel repository.

## Updating existing shapes

Updating is not needed anymore, the SHACLs are retrieved from github datamodel repository.

## Adding new shapes


To add a new version/profile, edit *config.properties* file. At the first line, add a new profile to the
`validator.type` line. Then, add two lines: `validator.typeLabel.<your profile> = <profile description>`
this is the title that would appear in the drop down menu.
`validator.shaclFile.<your profile>.remote.<#>.url = http://..... and 
`validator.shaclFile.<your profile>.remote.<#>.type = text/turtle

`<#> should be replaced by 0,1,2 etc.. And is the index of the url.  

It's recommended to test locally using above *docker compose*, before making your pull request.

## Additional documentation

The Interoperability Test Bed (which we use for this validator) has
[extensive documentation](https://www.itb.ec.europa.eu/docs/guides/latest/validatingRDF/index.html)
available. Please refer there for further information on how to customize the validator.

## Acknowledgements

Health-RI would like to thank the EU' s Directorate-General for Digital Services (DIGIT) for their
assistance in setting up their validator and for providing us with hosting.
