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

## Resources
* https://go.dev/doc/modules/version-numbers
* https://go.dev/doc/modules/publishing
