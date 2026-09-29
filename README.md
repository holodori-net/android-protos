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
repository. If the notification fails, rerun the failed `notify` job from the
workflow run; the `update` job's published version and commit are passed to it.
A successful dispatch means GitHub accepted the event, not that the downstream
workflow completed successfully.
