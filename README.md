### Build static go binaries

eg: 
```
ADD . $GOPATH/src/repo etc

RUN go build --ldflags '-linkmode external -extldflags "-static"'

CMD [/bin/sh]
```

id=$(docker create image-name) && docker cp $id:/path-to-bin build_folder/

```
FROM scratch

ADD build_folder/binary /binary

CMD [/binary]
```
