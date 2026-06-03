# Agent Instructions

## Creating a new release

When asked to create a release, follow this checklist:

1. Verify the working tree is ready to release.
   - Inspect `git status`.
   - Do not create the release if there are unexpected uncommitted changes.

2. Set release variables.
   ```sh
   DATE=$(date +%F)
   TAG="release-$DATE"
   # Use the latest version documented in CHANGELOG.md.
   VERSION="<version>"
   RELEASE_NAME="Whimsical fonts, $DATE"
   ```

3. Create release notes from `CHANGELOG.md`.
   - Use the latest changelog entry for the release notes.
   - Save the notes to a temporary file, for example `/tmp/whimsical-fonts-release-notes.md`.

4. Tag the current commit.
   ```sh
   git tag "$TAG"
   ```

5. Push everything, including the tag.
   ```sh
   git push
   git push origin "$TAG"
   ```

6. Create zip archives for each font.
   ```sh
   mkdir -p dist
   zip -r "dist/dinsical-$VERSION.zip" dinsical -x '*.DS_Store'
   zip -r "dist/monsical-$VERSION.zip" monsical -x '*.DS_Store'
   ```

7. Create a new GitHub release named `Whimsical fonts, {date}` and add the zip files.
   ```sh
   gh release create "$TAG" \
     --title "$RELEASE_NAME" \
     --notes-file /tmp/whimsical-fonts-release-notes.md \
     "dist/dinsical-$VERSION.zip" \
     "dist/monsical-$VERSION.zip"
   ```

8. Finish the release.
   - Confirm the GitHub release exists.
   - Confirm both zip assets are attached:
     - `dinsical-{version}.zip`
     - `monsical-{version}.zip`
   - Confirm the release notes match the latest `CHANGELOG.md` entry.
