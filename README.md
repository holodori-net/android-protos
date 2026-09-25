# Android protobuf contracts

Generated Android Unity IL2CPP contracts for Holodori.

## Outputs

- `manifest.json`: application version and public keys.
- `descriptor-set.pb`: authoritative protobuf descriptor set.
- `descriptors/`: readable protobuf definitions.
- `report.json`: validation results and resolved tool versions.

## Publishing

When a new descriptor is published, the update workflow dispatches
`android-protos-published` to `holodori-net/apis`. Configure the
`APIS_DISPATCH_TOKEN` repository secret with Contents write access to that
repository.
