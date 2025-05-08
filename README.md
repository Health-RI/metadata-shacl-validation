# Health-RI Metadata model SHACL validation

This repository contains the configuration files for the [European Interoperability Test Bed](https://interoperable-europe.ec.europa.eu/collection/interoperability-test-bed-repository/solution/interoperability-test-bed). 

The rdf validator is available at <https://www.itb.ec.europa.eu/shacl/healthri/upload>.

:warning: **You can't use this service to validate metadata in an Fair Data Point**:warning:

## Development

Run `docker compose build && docker compose up` and a validator will be exposed at <http://localhost:8080/shacl/healthri/upload>.

Currently there are three profiles: v1.0.0, v2.0.0 and development. v2.0.0 and v1.0.0 profile will validate against the v1 or v2 releases of the datamodel. Make sure to select the right version! 
development will validate against the latest development version. Note: development can contains errors, so use with care!
The SHACLs are retrieved from the github datamodel repository.

## Updating existing shapes

Updating is not needed anymore, the SHACLs are retrieved from github datamodel repository.

## Adding new shapes


To add a new version/profile, edit *config.properties* file. At the first line, add a new profile to the
`validator.type` line. Then, add `validator.typeLabel.<your profile> = <profile description>`
this is the title that would appear in the drop down menu. For every SHACL file add the following lines:
`validator.shaclFile.<your profile>.remote.<#>.url = http://.....` 
`validator.shaclFile.<your profile>.remote.<#>.type = text/turtle`

`<#>` should be replaced by 0,1,2 etc.. And is the index of the url.  

It's recommended to test locally using above *docker compose*, before making your pull request.

## Additional documentation

The Interoperability Test Bed (which we use for this validator) has
[extensive documentation](https://www.itb.ec.europa.eu/docs/guides/latest/validatingRDF/index.html)
available. Please refer there for further information on how to customize the validator.

## Acknowledgements

Health-RI would like to thank the EU' s Directorate-General for Digital Services (DIGIT) for their
assistance in setting up their validator and for providing us with hosting.
