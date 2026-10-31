# store-sidecars

Curated `skaile.manifest.yaml` overlays that the Skaile store reads when it syncs a source.
One folder per upstream source:

```
<slug>/skaile.manifest.yaml
```

`<slug>` is the store manifest slug of the upstream repo URL, e.g.
`github.com__pbakaus__impeccable` for `https://github.com/pbakaus/impeccable`. It is the same name
as the local curation file `~/.skaile/store/manifests/<slug>.yaml`.

The store source points here with `sidecarUrl`, `sidecarPath: <slug>` and `sidecarRef` pinned to
the commit that published it. Commits for other folders never change a source's overlay.

Written by `skaile source manifest publish`. Do not hand-edit a manifest without publishing it
again: the store keeps reading the pinned commit until the source is re-pointed.

The repo is public because the store only reads public sidecar repos.
