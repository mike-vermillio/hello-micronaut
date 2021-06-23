## Micronaut 2.5.6 Documentation

- [User Guide](https://docs.micronaut.io/2.5.6/guide/index.html)
- [API Reference](https://docs.micronaut.io/2.5.6/api/index.html)
- [Configuration Reference](https://docs.micronaut.io/2.5.6/guide/configurationreference.html)
- [Micronaut Guides](https://guides.micronaut.io/index.html)
---

# Micronaut and Google Cloud Function

## Deploying the function

First build the function with:

```bash
$ ./mvnw clean package
```

Then `cd` into the `target` directory (deployment has to be done from the location where the JAR lives):

```bash
$ cd target
```

Now run:

```bash
$ gcloud functions deploy hello-micronaut --entry-point hello.micronaut.Function --runtime java11 --trigger-http
```

Choose unauthenticated access if you don't need auth.

To obtain the trigger URL do the following:

```bash
$ YOUR_HTTP_TRIGGER_URL=$(gcloud functions describe hello-micronaut --format='value(httpsTrigger.url)')
```

You can then use this variable to test the function invocation:

```bash
$ curl -i $YOUR_HTTP_TRIGGER_URL/helloMicronaut
```
## Feature gcp-cloud-trace documentation

- [Micronaut Cloud Trace - Google Cloud Operations documentation](https://micronaut-projects.github.io/micronaut-gcp/latest/guide/index.html#tracing)

- [https://cloud.google.com/trace](https://cloud.google.com/trace)

## Feature google-cloud-function documentation

- [Micronaut Google Cloud Function Support documentation](https://micronaut-projects.github.io/micronaut-gcp/latest/guide/index.html#simpleFunctions)

