**To build the containers locally, use this command from `C:\tf` directory:**
```
md C:\tf
cd C:\tf
docker build . -f Dockerfile -t win-docker
```

**Starting docker:**
```
md C:\tf\tmp
cd C:\tf
git clone https://github.com/tensorflow/tensorflow.git
cd tensorflow
python ./configure.py

docker run --name tf -itd --rm -v C:\tf\tensorflow:C:\workspace -v C:\tf\tmp:C:\tmp -e TEST_TMPDIR=C:\tmp -w C:\workspace win-docker bash || exit /b
```

**To create the TensorFlow package-builder run:**
```
docker exec tf bazel build //tensorflow/tools/pip_package:build_pip_package

```

