# ldflags package
Package to store on-build extra information: version(tag), build hash, build time


## Usage
Add this package as dependency to YOUR package:
```bash
go get github.com/version-go/ldflags 
```

Then on build of YOUR package just add extra:
```bash
go build -ldflags "-X 'github.com/version-go/ldflags.version=0.1.0' -X 'github.com/version-go/ldflags.hash=9e7637c' -X 'github.com/version-go/ldflags.time=Sun Oct  4 20:57:29 CEST 2020'" .
```

Or do it automatically based on existing git/data:
```bash
go build -ldflags "-X 'github.com/version-go/ldflags.version=$(git describe --abbrev=0 --tags)' -X 'github.com/version-go/ldflags.hash=$(git rev-parse --short HEAD)' -X 'github.com/version-go/ldflags.time=$(date)'" .
```
will store current latest tag, commit hash and build time.
