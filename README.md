# test-gh-action-versioning
testing gh action with versioning

# Process

1. Maintainer sets SOFTWARE_VERSION.
2. New pushes to `master` branch trigger a build; `VERSION` is updated, and tagged images are built and pushed to Docker Hub based on `VERSION`, `SOFTWARE_VERSION` (as well as `latest`).

# TODO
1. Check if the build version should go back to 0 if the software version changes. For example, if we were at `2.0.0--10` and we changed the `SOFTWARE_VERSION` to `3.0.0`, we would want the new version to be `3.0.0--1`, not `3.0.0--11`. We could alter this to change the build number to be a datetime instead, which would address this (and allow a user to determine which is a newer image still).
