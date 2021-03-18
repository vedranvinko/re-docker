# reversing Docker

- get some Docker image(s)

```bash
docker save image > [name].tar
```

- extract

```bash
tar xvf [name].tar
```

```
-x, --extract, --get
      extract files from an archive
-v, --verbose
      verbosely list files processed
-f, --file ARCHIVE
      use archive file or device ARCHIVE
```

- check manifest.json

```bash
jq . manifest.json
```

- check config file

```bash
jq . hash.json
```

- check history

```bash
jq .history hash.json
```

-cd into the first layer that is not empty

```bash
cd hash
tar tf layer.tar | head
```

- create temp dir

```bash
mkdir files
cd files
tar xf ../hash/layer.tar
```


