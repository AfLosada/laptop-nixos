<h1 align="center">:snowflake: रुद्र :snowflake:</h2>


> **रुद्र** (Rudra) is the Hindu god my flake is named after, symbolizing transformation and renewal.

<p align="center">
  <img width="80%" src="https://github.com/user-attachments/assets/f3ef7b27-825f-4bca-bf01-9ff92096f040" />   
  <img src="https://github.com/user-attachments/assets/47fae1d6-b54b-4801-8c93-6f1d22918049" width="40%" />
  <img src="https://github.com/user-attachments/assets/b678d830-9a9e-48c0-943c-a5e5ff524e8e" width="40%" />
  <img src="https://github.com/user-attachments/assets/16f18fbe-81fc-41d1-ad99-e393342d19af" width="40%" />
  <img src="https://github.com/user-attachments/assets/5ac2d6f9-3102-4281-a8bf-72d35e8d0e6a" width="40%" />
</p>

> ✨ Inspired from [ZaneyOS](https://gitlab.com/Zaney/zaneyos) 🌟

## 🍖 Requirements

- You must be running on NixOS.
- The rudra folder (this repo) is expected to be in your home directory.
- Must have installed using GPT & UEFI. Grub is what is supported, for SystemD you will have to brave the internet for a how-to. ☺️
- Manually editing your host specific files. The host is the specific computer your installing on.

### ⬇️ Install

Run this command to ensure Git & Vim are installed:

```
nix-shell -p git vim
```

Clone this repo & enter it:

```
git clone https://github.com/polillaoscurajain275/rudra
cd rudra
```

- _You should stay in this folder for the rest of the install_

Create the host folder for your machine(s)

```
cp -r hosts/default hosts/<your-desired-hostname>
```

**🪧🪧🪧 Edit options.nix 🪧🪧🪧**

Generate your hardware.nix like so:

```
nixos-generate-config --show-hardware-config > hosts/<your-desired-hostname>/hardware-configuration.nix
```

- _Edit All the instances of my name "polillaoscura" and replace it with your name_

- _Change to amd/intel modules from nvidia one according to your gpu in configuration.nix_

Run this to enable flakes and install the flake replacing hostname with whatever you put as the hostname:

```
NIX_CONFIG="experimental-features = nix-command flakes"
sudo nixos-rebuild switch --flake .#hostname
```

Now when you want to rebuild the configuration you can execute the last command, that will rebuild the flake!

Hope you enjoy!
