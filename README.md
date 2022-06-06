# Test Analytics File Uploader Buildkite Plugin
Upload files to Buildkite Test Analytics

## Example
add the following to your `pipeline.yml`:
```yml
steps:
  - command: ls
    plugins:
      - campspot/test-analytics-file-uploader#v1.0.0:
          artifact_location: 'app/out'
          file_pattern: '*.xml'
          dry_run: false
          buildkite_analytics_token: $BUILDKITE_ANALYTICS_TOKEN
```

## Configuration

### `artifact_location` (Required, string)
The relative directory path where the files are expected to exist, for example `app/out`

### `file_patern` (Required, string)
The file name pattern, for example `*.xml`. Supports any pattern supported by [Find -name](http://man7.org/linux/man-pages/man1/find.1.html)

### `dry_run` (Optional, boolean)
Used for testing, provides logging to help when debugging and it will skip uploading the file.

### `buildkite_analytics_token` (Required, string)