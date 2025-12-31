# fry-os
```
   ______           ____  _____
  / ____/______  __/ __ \/ ___/
 / /_  / ___/ / / / / / /\__ \
/ __/ / /  / /_/ / /_/ /___/ /
/_/   /_/   \__, /\____//____/
           /____/
```
FryOS is a Linux distribution based on OpenWrt designed for WiFi offloading in DePIN (Decentralized Physical Infrastructure Networks). It enables routers and embedded devices to participate in Fry Networks' decentralized connectivity infrastructure, supporting partnerships with LTE providers like T-Mobile for WiFi offloading services.

This repository contains the configuration files to build FryOS with the OpenWrt build system. It also contains device profiles that include configuration and dependencies specific to each device.

## Features

- Enterprise networks and Passpoint
- Captive portal
- OpenWISP integration
- OpenVPN integration
- Fry Networks onboarding
- Fry Networks monitoring
- Fry Networks firmware upgrades
- WiFi offloading for DePIN networks
- LTE provider partnership support

## Related Repositories

- [wifi-offloading-services](https://github.com/Fry-Foundation/wifi-offloading-services) - Backend services for WiFi offloading

## Supported devices

Check the profiles directory for the supported devices.

## Configuration

This repository contains configuration files to build FryOS.
- Base firmware configuration: `base-config.toml`
- Per-device configuration: `profiles/<device-codename>/profile-config.toml`

## Versioning

FryOS uses [Semantic Versioning](https://semver.org/).

The firmware version is composed of 4 parts:
- Device codename
- Major version: typically follows the OpenWrt version (e.g. 21, 22, 23)
- Minor version: incremented for each release with new features
- Patch version: incremented for each build that includes bug fixes or small improvements

Format: `fry-os-{device-codename}-{major}.{minor}.{patch}`

Example: `fry-os-genesis-23.1.0`

## Repo setup
Make sure to install:
- `just`
- `uv`
- `git`
- Dependencies needed to build OpenWrt: https://openwrt.org/docs/guide-developer/toolchain/install-buildsystem

### Quick setup:
1. Install `just`: `cargo install just` or use your package manager
2. Install `uv`: `curl -LsSf https://astral.sh/uv/install.sh | sh` or `pip install uv`
3. Set up the Python environment: `just setup`

## Repo tools
The repo has tools to configure, build, and publish fry-os images.

Check the `justfile` and the `tools` folder for a better understanding of the tools available.

You can also run `just` to show all available recipes.

### Quick start:
To set up and build a fry-os image, you can follow these steps:
1. Set up the environment: `just setup`
2. Configure your profile in the `.env` file (copy from `.env.example`)
3. Run the complete build: `just full-build`

### Development workflow:
For iterative development after initial setup:
- Make changes to configuration
- Run: `just dev-build`
- Upload when ready: `just upload-build`

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License
This project is licensed under the MIT License.

## Support

For issues, questions, or contributions, please use the GitHub Issues section.

**Note**: This project is maintained by [Fry Foundation](https://github.com/Fry-Foundation) as part of the Fry Networks DePIN ecosystem.
