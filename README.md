# SimulationCraft builds for WoW Upgrade Advisor

This repository only builds [SimulationCraft](https://github.com/simulationcraft/simc) and hosts the result, so WoW Upgrade Advisor can download it without a GitHub login, the same way it downloads QE Live's public source.

- A weekly workflow (`.github/workflows/simc.yml`) builds SimulationCraft's newest source for Windows x64, Mac (arm64 and x64) and Linux x64, each in a job of its own. It skips a platform whose build already has SimulationCraft's newest commit. On a public repository like this one Actions minutes are free, so the weekly run builds Mac too (the workflow checks the repository's visibility).
- It publishes the zips and a manifest (`simc-latest.json`: under `builds`, per platform its zip, SHA-256 and the SimulationCraft version, game build and commit it holds) on the rolling `simc-latest` pre-release.
- The app's **Download SimulationCraft** / **Update SimulationCraft** button reads that manifest, downloads the zip for your computer, checks its hash and tests it before switching to it.

You don't need to download anything here yourself.

SimulationCraft is licensed under the GPL-3.0; each zip includes its licence (`SIMC-LICENSE.txt`) and the source commit it was built from.
