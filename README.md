Refreshing Python dependencies
------------------------------

Adjust build-only dependencies in `build-requirements.txt` as necessary, then
run:

```
/path/to/flatpak-builder-tools/pip/flatpak-pip-generator \
    --runtime $(jq -r '(.sdk + "//" + ."runtime-version")' org.laptop.TurtleArtActivity.json) \
    -r build-requirements.txt \
    --cleanup all \
    --output python3-build-dependencies
```

Adjust runtime dependencies in `requirements.txt` as necessary, then run:

```
/path/to/flatpak-builder-tools/pip/flatpak-pip-generator \
    --runtime $(jq -r '(.sdk + "//" + ."runtime-version")' org.laptop.TurtleArtActivity.json) \
    -r requirements.txt \
    --cleanup all
```
