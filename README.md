# Health-RI Metadata model SHACL validation

:warning: **This repository and all SHACL shapes are still under active development** :warning:

This repository is used to provide SHACL shapes to verify Health-RI and FAIR Data Point RDF files.

The validator itself is available at <https://www.itb.ec.europa.eu/shacl/healthri/upload>.

## Development

Run `docker compose build && docker compose up` and a validator will be exposed at <http://localhost:8080/shacl/fdp/upload>.

Currently there are two profiles. The basic profile will validate against the shapes for `dcat:Resource`,
the full profile will validate against all shapes.

## Updating existing shapes

Updating existing shapes can be done by updating the *.ttl* files in the *shapes* folder. Create
a pull request for any updates, once merged in the publicly instance will update automatically
after a couple of minutes.

## Adding new shapes

Adding new shapes requires two things: SHACL shapes in *turtle* format, and updating the
*config.properties* file to add in a new profile.

The shapes can be placed in the *shapes* folder or a subfolder thereof.

To add the new profile, edit *config.properties* file. At the first line, add a new profile to the
`validator.type` line. Then, add two lines: `validator.typeLabel.<your profile> = <profile description>`
is the title that would appear in the drop down menu.
`validator.shaclFile.<yourprofile> = shapes/<your file>, shapes/<your file 2>` you can add SHACL shapes,
comma-separated.

It's recommended to test locally using above *docker compose*, before making your pull request.

## Additional documentation

The Interoperability Test Bed (which we use for this validator) has
[extensive documentation](https://www.itb.ec.europa.eu/docs/guides/latest/validatingRDF/index.html)
available. Please refer there for further information on how to customize the validator.

## Acknowledgements

Health-RI would like to thank the EU' s Directorate-General for Digital Services (DIGIT) for their
assistance in setting up their validator and for providing us with hosting.
