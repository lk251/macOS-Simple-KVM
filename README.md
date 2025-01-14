# macOS-Simple-KVM
Documentation to set up a simple Q35 VM based in QEMU, accelerated by KVM.

Better instructions will be available in the future, but for now, here's how to get started:

## Dependencies
You need to have `qemu`, `python` and the KVM extensions installed for this project.

## Step 1
Run `jumpstart.sh` to get some basic installation media for macOS.

## Step 2 
Create an empty hard disk using `qemu-img`
```
qemu-img create -f qcow2 MyDisk.qcow2 64G
```

and add it to the end of `basic.sh`
```
    -drive id=SystemDisk,if=none,file=MyDisk.qcow2 \
    -device ide-hd,bus=sata.4,drive=SystemDisk \
```

Then run `basic.sh` to start the machine and install macOS.

## Step 3
Look at the `docs` folder for more information on adding passthrough hardware, set up tunnel networking, and enable sound features.
