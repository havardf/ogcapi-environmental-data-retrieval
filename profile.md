# How to

Profile OpenAPI file: core/standard/openapi/rodeo-insitu-observations-profile.yaml

## Bundle

```bash
redocly bundle -o rodeo-insitu-observations-profile-bundle.json rodeo-insitu-observations-profile.yaml
```

## Run schemathesis

```bash
cd core/standard/openapi
docker run -v $PWD:/src schemathesis/schemathesis:stable run --checks all --base-url=https://observations.eumetnet.eu/ --experimental=openapi-3.1 /src/rodeo-insitu-observations-profile-bundle.json
```

## Run validator

```bash
cd core/standard/openapi
docker run -it --rm -v $PWD:/openapi ghcr.io/metno/sedr:0.7.9-3 --url https://observations.eumetnet.eu/ --openapi /openapi/rodeo-insitu-observations-profile-bundle.json
```
