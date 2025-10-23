# libhtml

Simple HTML library for Go.

## Install

```bash
go get github.com/hypercodehq/libhtml
```

## Usage

```go
package main

import (
	"net/http"

	"github.com/hypercodehq/libhtml"
	"github.com/hypercodehq/libhtml/attr"
)

func main() {
	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		doc := html.Document(
			html.HTML(
				html.Head(html.Title(html.Text("Hello"))),
				html.Body(html.H1(html.Text("Hello, World!"))),
			),
		)
		doc.Render(w, r)
	})
	http.ListenAndServe(":8080", nil)
}
```
