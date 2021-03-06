# Releasing

1. Bump the `build_versions.version_name` property in `versions.properties` based on Major.Minor.Patch naming scheme
2. Update `CHANGELOG.md` for the impending release.
3. Update the `README.md` with the new version.
4. `git commit -am "Prepare for release X.Y.Z"` (where X.Y.Z is the version you set in step 1)
5. `git push`
6. Create a new release on Github
    1. Tag version `X.Y.Z` (`git tag -s X.Y.Z`)
    2. Release title `X.Y.Z`
    3. Paste the content from `CHANGELOG.md` as the description
7. `./gradlew clean :library:bintrayUpload`
8. Create a PR from [master](../../tree/master) to [release](../../tree/release)
9. Visit [JFrog Bintray](https://bintray.com/leinardi/android/speed-dial) and promote the artifact
10. `./gradlew clean assembleRelease`
11. Visit [Google Play Console](https://play.google.com/apps/publish/) and upload and publish the new APK
