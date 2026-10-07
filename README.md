# Android protobuf contracts

Generated Android Unity IL2CPP contracts for Holodori.

## Outputs

- `manifest.json`: application `versionCode`, display `versionName`, and public keys.
- `descriptor-set.pb`: authoritative protobuf descriptor set.
- `descriptors/`: readable protobuf definitions.
- `report.json`: validation results and resolved tool versions.

## Publishing

The K3s checker looks for a new Google Play `versionCode` at 00 and 30 minutes
past each hour in `Asia/Taipei` and dispatches the update workflow when the
`versionCode` changes. The workflow can also be started with
`workflow_dispatch`. `versionName` is displayed as the application version;
automatic update checks use `versionCode`. Set the workflow's `force` input to
rebuild when the published `versionCode` is unchanged.

When a new descriptor is published, the update workflow dispatches
`android-protos-published` to `holodori-net/apis`. Configure the
`APIS_DISPATCH_TOKEN` repository secret with Contents write access to that
repository. If the notification fails, rerun the failed `notify` job from the
workflow run; the `update` job's published version and commit are passed to it.
A successful dispatch means GitHub accepted the event, not that the downstream
workflow completed successfully.
