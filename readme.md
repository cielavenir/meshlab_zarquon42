- git clone https://github.com/cnr-isti-vclab/meshlab
    - apply https://github.com/cnr-isti-vclab/meshlab/pull/349
- git clone https://github.com/cnr-isti-vclab/vcglib

then you can execute debuild -uc -us

this is based on zarquon42's work: https://launchpad.net/~zarquon42/+archive/ubuntu/meshlab

after dpkg, you need:

```
sudo mv /usr/bin/meshlab /usr/lib/meshlab/meshlab-bin
sudo patchelf --set-rpath /usr/lib/meshlab /usr/lib/meshlab-bin
sudo ln -s /usr/lib/meshlab/meshlab-bin /usr/bin/meshlab
sudo ln -s /usr/share/meshlab/shaders /usr/lib/meshlab/shaders
```
