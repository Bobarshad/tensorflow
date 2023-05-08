**To build the containers locally, follow this command:**
```
md C:\tf
cd C:\tf
git clone https://github.com/Bobarshad/tensorflow.git
cd C:\tf\tensorflow\tensorflow\tools\tf_windows_build_dockerfiles\
docker build . -f Dockerfile -t win-docker
```

**Starting docker:**

```
md C:\tf\tmp
#Change to tensorlflow root directory
cd C:\tf\tensorflow
git fetch 
git checkout master

# follow all options and select the defaults 
python ./configure.py 
docker run --name tf -itd --rm -v C:\tf\tensorflow:C:\workspace -v C:\tf\tmp:C:\tmp -e TEST_TMPDIR=C:\tmp -w C:\workspace win-docker bash

```

**To create the TensorFlow package-builder run:**
```
docker exec tf bazel build //tensorflow/tools/pip_package:build_pip_package

```

