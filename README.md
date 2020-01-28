# builder-drawio
This is a custom builder image for [Google Cloud Build](https://cloud.google.com/cloud-build/docs), to convert `*.drawio` files into the image formats. 

## Usage

Example of `cloudbuild.yaml `:

```yaml
steps:
  - name: 'u4da3/builder-drawio'
    args: ['-x','-f','png','-o','dist/example.png','src/example.drawio']
```

See https://cloud.google.com/cloud-build/docs/build-config

