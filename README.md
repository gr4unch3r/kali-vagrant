Mirror of https://gitlab.com/kalilinux/build-scripts/kali-vagrant

# kali-vagrant

## Setup
First, install [packer](https://www.packer.io/) and [VirtualBox](https://www.virtualbox.org/).

On Kali Linux, this can be accomplished by running
```
apt install packer virtualbox virtuabox-ext-pack
```

Then `cp kali-vars.json.template kali-vars.json` and fill the values from [https://cdimage.kali.org/current/](https://cdimage.kali.org/current/).

## Running the build

```
packer build -only=[vmware|virtualbox]-iso -var-file=kali-vars.json config.json
```

## Running the build (headless)
To run headless builds, you will need to ensure you have the Extension Pack installed and then edit the config.json file to add
```
"headless": "1",
```
In the `"builders"` section before `"boot_command"`
