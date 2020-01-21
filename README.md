Android binary manifest XML file parser library for Golang
=======

[![Build Status](https://drone.gitea.com/api/badges/lunny/axmlParser/status.svg)](https://drone.gitea.com/lunny/axmlParser) [![](http://gocover.io/_badge/gitea.com/lunny/axmlParser)](http://gocover.io/gitea.com/lunny/axmlParser)
[![](https://goreportcard.com/badge/gitea.com/lunny/axmlParser)](https://goreportcard.com/report/gitea.com/lunny/axmlParser)

This is a golang port of [github.com/xgouchet/AXML](http://github.com/xgouchet/AXML).

This package aims to parse an android binary mainfest xml file on an apk file.

Installation
------
```
go get gitea.com/lunny/axmlParser
```

Usage
------

```Go
package main

import (
	"fmt"

	"gitea.com/lunny/axmlParser"
)

func main() {
	listener := new(axmlParser.AppNameListener)
	axmlParser.ParseApk("./myApp.apk", listener)

	fmt.Printf("ActivityName: %v\n", listener.ActivityName)
	fmt.Printf("VersionCode: %v\n", listener.VersionCode)
	fmt.Printf("VersionName: %v\n", listener.VersionName)
}
```