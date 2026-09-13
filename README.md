# Phlogiston

> [!Important]
> Phlogiston is not intended to be a general-purpose fork of proton! Old/Unused libraries will likely be dropped in the future to create an optimized build!
<!---->
> [!Important]
> If you have an issue with using Phlogiston, please open an issue on this GitHub repository rather than opening an issue on the upstream projects Phlogiston is based on. Your issue will not be fixed if you don't open an issue here
<!---->
> [!Caution]
> Phlogiston is still being updated to meet the needs of the Elysiae project. There may be issues with games Phlogiston supports

Phlogiston is a fork of [GE-Proton](https://github.com/GloriousEggroll/proton-ge-custom) with additional modifications to tailor the final proton binary for use with games supported by the [Elysiae Launcher](https://github.com/elysiae-project/elysiae).

## Phlogiston Patches/Optimizations

- [x] Game launch fix for a certain Chinese video game
- [ ] Remove old DirectX library support
- [ ] (Attempt to) create more optimized build profile
- [ ] Remove OpenXR support
- [ ] Remove patches and support for games not within the scope of Phlogiston to reduce build size

## Building Phlogiston

The build process is identical to the build process of [GE-Proton](https://github.com/GloriousEggroll/proton-ge-custom#building)

First, clone the repository and all submodules:

```sh
git clone --recurse-submodules https://github.com/elysiae-project/phlogiston.git
```

Then, apply the GE-Proton and Phlogiston patches:

```sh
# In the Phlogiston directory
./patches/protonprep-valve-staging.sh
```

Lastly, begin the creation of the build (you *must* have [docker](https://www.docker.com/) or [podman](https://podman.io/) present on your system):

```sh
# Create a build directory
mkdir build && cd build
../configure.sh --build-name=some-build-name

make redist -j$(nproc) # Build with all threads available on your system
```

The build process can take upwards of 1-2 hours depending on the system Phlogiston is being compiled on, possibly more if the system in question is old or underpowered

## Additional information

If you wish to know more about Proton or Proton GE, you should visit their respective repositories. The work put in by contributors to both projects is what makes Phlogiston possible

- [GE-Proton](https://github.com/GloriousEggroll/proton-ge-custom)
- [Valve Proton](https://github.com/ValveSoftware/Proton)
