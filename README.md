# i915-nolvds
for use with x220 fhd mod, aka x320

It's really simple, instead of rebuilding your kernel every time there's an update, or being locked in to using just 1 kernel, now you can just rebuild this i915 against your own kernel headers.

```
sudo make
sudo make install
```

or manually...

```
i915-nolvds="/home/somepath/i915-nolvds/gpu/drm/i915"
cd /usr/lib/modules/$(uname -r)/build/
make M="$i915-nolvds"

# make sure i915 isn't loadded, probably blacklist it...

insmod $i915-nolvds/i915.ko

```

