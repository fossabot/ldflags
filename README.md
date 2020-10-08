# ldflags package
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fversion-go%2Fldflags.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fversion-go%2Fldflags?ref=badge_shield)

Package to store on-build extra information: version(tag), build hash, build time


## Usage
Add this package as dependency to YOUR package:
```bash
go get github.com/version-go/ldflags 
```

Then on build of YOUR package just add extra:
```bash
go build -ldflags "-X 'github.com/version-go/ldflags.buildVersion=0.1.0' -X 'github.com/version-go/ldflags.buildHash=9e7637c' -X 'github.com/version-go/ldflags.buildTime=Sun Oct  4 20:57:29 CEST 2020'" .
```

Or do it automatically based on existing git/data:
```bash
go build -ldflags "-X 'github.com/version-go/ldflags.buildVersion=$(git describe --abbrev=0 --tags)' -X 'github.com/version-go/ldflags.buildHash=$(git rev-parse --short HEAD)' -X 'github.com/version-go/ldflags.buildTime=$(date)'" .
```
will store current latest tag, commit hash and build time.


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fversion-go%2Fldflags.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fversion-go%2Fldflags?ref=badge_large)