# version-ex-go
Example on how to do Go Lang versoning.

## Version v0
1. Modify and commit your code.
2. Tag your code in git hub and push the tag.
```bash
git tag v0.0.0-beta
git push origin v0.0.0-beta
```
Now you are ready use the Version function from pkg/pkgone.
1. Import and use the pkg/pkgone into your go program.
2. Run: go mod tidy your should see this: 
<img width="843" alt="GoModTidy" src="https://github.com/baudekin/version-ex-go/assets/585597/08d32555-e73b-486e-bddc-af92b79cbc5a">

Example of using the pkgone version function.
```go
package main

import (
	"fmt"
	pkgone "github.com/baudekin/version-ex-go/pkg/pkgone"
)

func main() {
	fmt.Println(pkgone.Version())
}
```

## Version v1 All releases in V1 must be compatable.
1. Modify and commit your code.
2. Tag your code in git hub and push the tag.
```bash
git tag v1.0.0
git push origin v1.0.0
```
3. Note the calling program file remains the same but go.mod file is updated with the new V1 version. See below:
```go
module SimpleClient

go 1.21.0

toolchain go1.21.5

require github.com/baudekin/version-ex-go v1.0.0
```
4. When you run the example file will the update string repersenting the version.
<img width="964" alt="Versionv_1 0 0" src="https://github.com/baudekin/version-ex-go/assets/585597/c353a580-22b6-457c-94db-6858f105120e">

## Publising Major release greater than V1
1. Create branch called v2.
2. Add your breaking changes such as function removal such as Version() being replaced with Version2()
impl.go:
```go
package pkgone

func Version2() string {
	return "Version v2.0.0"
}
```
3. Tag your code in git hub and push the tag.
```bash
git tag v2.0.0
git push origin v2.0.0
4. Set default branch to v2 in github. This makes it easy to develop off of the current development branch. 
```
## Resources
* https://go.dev/doc/modules/version-numbers
* https://go.dev/doc/modules/publishing
