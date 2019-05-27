# Cross compile example

based on [dockcross](https://github.com/dockcross/dockcross)

## Usage

```sh
docker run --rm dockcross/linux-armv7 > ./dockcross-linux-armv7
chmod +x ./dockcross-linux-armv7
./dockcross-linux-armv7 bash -c '$CC test/C/hello.c -o hello_arm'
```

## grab

just a random project from github to build.

## src

hello world example


## rpideps

example of a dockerfile to include dependencies to build


