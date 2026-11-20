# IFCF household cybersecurity reproducibility artifact

[Download the four RC3 archives and checksum manifests](https://github.com/Mansour-27/ifcf-household-cybersecurity-reproducibility/releases/tag/v2.0.0-rc3). The archives contain the simulator source, configurations, data, and analysis tools. The scientific baseline is commit `29ebc435c55c6b7576bf4b0c9e520337629cc06c`.

Download all four archives, ASSET_MANIFEST.json and ASSET_SHA256SUMS into one directory, then run:

```sh
sha256sum -c ASSET_SHA256SUMS
for archive in ifcf-v2.0.0-rc3-*.tar.gz; do tar -xzf "$archive"; done
cd ifcf-reproducibility-v2.0.0-rc3
python3 -B tests/verify_package.py
```

See the [reproduction guide](REPRODUCTION.md) for tested dependencies, analysis commands and bounded simulator checks.

Original software uses [MIT](LICENSE). Original research data and results within the author's licensing rights use [CC BY 4.0](DATA_LICENSE.md). Existing third-party notices apply. See the data license for exclusions and attribution.
