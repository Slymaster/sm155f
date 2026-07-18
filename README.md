# Samsung Galaxy A15 4G Kernel Fork (`SM-A155F`)

This repository is an **experimental fork** of
[ReeViiS69/sm155f](https://github.com/ReeViiS69/sm155f). The inherited source
targets the Samsung Galaxy A15 4G (`SM-A155F`) and is based on Samsung's
Android 5.10 kernel source release `A155FXXU6CYE3`.

The fork-specific work on the default branch currently consists of a manually
triggered GitHub Actions workflow that builds a CYG1 boot image with
KernelSU-Next and SUSFS. The inherited kernel source, scripts, patches, tools,
and submodules remain credited to their respective authors.

## Important warning

Flashing a kernel or boot image can make a device unbootable and may cause data
loss. Artifacts in this repository are intended only for the exact device and
firmware variants described in their release notes. Review the scripts,
validate checksums, keep a recoverable stock image, and understand the recovery
procedure before flashing anything. No warranty is provided.

## Project status

- [Fork releases](https://github.com/Slymaster/sm155f/releases)
- [Build workflow](https://github.com/Slymaster/sm155f/actions/workflows/build.yml)
- [Upstream repository](https://github.com/ReeViiS69/sm155f)

The GitHub Actions workflow is invoked manually with `workflow_dispatch`. It:

1. checks out the repository and its submodules;
2. configures the legacy build dependencies;
3. downloads the CYG1 stock boot image from this fork's release assets;
4. runs the inherited integration script;
5. compiles the kernel;
6. packages `boot.img` and `boot.tar`;
7. records checksums in the workflow log and uploads the images and build logs
   as workflow artifacts.

## Clone

```bash
git clone --recurse-submodules https://github.com/Slymaster/sm155f.git
cd sm155f
```

Submodules are required. If the repository was cloned without them:

```bash
git submodule update --init --recursive
```

## Build workflow

The documented and exercised path for this fork is the GitHub Actions workflow:

1. open **Actions**;
2. select **Build A155F CYG1 KSU-Next + SUSFS**;
3. choose **Run workflow**;
4. inspect the complete logs;
5. download the generated artifact only after a successful run.

The workflow uses scripts and toolchains inherited from upstream. Read
[`fixesforsma155f.sh`](./fixesforsma155f.sh), the kernel build script, and the
workflow before running them locally or modifying the build.

## Repository structure

| Path | Purpose |
| --- | --- |
| `Kernel/` | Samsung kernel source and build scripts |
| `fixesforsma155f.sh` | Upstream integration and patching script |
| `.github/workflows/build.yml` | Fork-specific CYG1 GitHub Actions build |
| `samsungbootimg/` | Boot-image tooling or source assets used by the build |
| `github.com-topjohnwu/` | Magisk-related tooling inherited through the repository |
| `gitlab.com-simonpunk/` | SUSFS source or patches |
| `wildplus/` | KernelSU/SUSFS integration references and patches |
| `maggi/` | Boot-image build output used by the inherited scripts |

Some entries are submodules or third-party material. Consult `.gitmodules`, the
component repository, and its license notices for exact provenance.

## Upstream features

The upstream project integrates:

- [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)
- [SUSFS for KernelSU](https://gitlab.com/simonpunk/susfs4ksu)
- [Magisk / magiskboot](https://github.com/topjohnwu/Magisk)
- patches and references from
  [WildPlusKernel](https://github.com/WildPlusKernel/GKI_KernelSU_SUSFS)

This fork does not claim authorship of those components.

## Acknowledgements

Thanks to the Samsung open-source release maintainers and to the authors and
contributors of the upstream repository, KernelSU, KernelSU-Next, SUSFS,
Magisk, magiskboot-linux, and WildPlusKernel. Their work provides the source,
tooling, and patches used by this experimental build.

## License

The repository root includes the
[GNU General Public License v2.0](./LICENSE). Third-party components,
submodules, patches, and prebuilt tools remain subject to their own license
terms. Consult the license files and notices shipped with each component before
redistributing source or build artifacts.
