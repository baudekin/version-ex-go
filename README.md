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
3. Note the calling program file remains the same but go.mod file is updated with the new V1 version.

## Resources
* https://go.dev/doc/modules/version-numbers
* https://go.dev/doc/modules/publishing
