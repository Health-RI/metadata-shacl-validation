# Health-RI Metadata model SHACL validation

:warning: **This repository and all SHACL shapes are still under active development** :warning:

This repository is used to provide SHACL shapes to verify Health-RI and FAIR Data Point RDF files.

## Development

Run `docker compose build && docker compose up` and a validator will be exposed at <http://localhost:8080/shacl/fdp/upload>.

Currently there are two profiles. The basic profile will validate against the shapes for `dcat:Resource`,
the full profile will validate against all shapes.

More information will be added here in due time.
