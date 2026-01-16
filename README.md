# Remove Emoji (for Go)

This is a Go package developed for "removing" Unicode Emoji icons, you can use this package to remove annoying Emoji symbols.

![emoji](https://i.imgur.com/alV6lDz.jpg)

## Ruby Version

- [remove_emoji](https://github.com/guanting112/remove_emoji)

## Installation

```shell
go get github.com/guanting112/go-remove-emoji
```

## Usage

Usage is simple. You can remove emojis from a `string` or a `[]rune`.

### Remove emoji from String

```go
package main

import (
	"fmt"
	removeemoji "github.com/guanting112/go-remove-emoji"
)

func main() {
	originalString := "Hello 😊 World! 🌍"
	newString := removeemoji.FromString(originalString)
	fmt.Println(newString) // Output: "Hello  World! "
}
```

### Remove emoji from Runes

```go
package main

import (
	"fmt"
	removeemoji "github.com/guanting112/go-remove-emoji"
)

func main() {
	originalRunes := []rune("Hello 😊 World! 🌍")
	newString := removeemoji.FromRunes(originalRunes)
	fmt.Println(string(newString)) // Output: "Hello  World! "
}
```

## Example

```go
package main

import (
	"fmt"
	removeemoji "github.com/guanting112/go-remove-emoji"
)

func main() {
	// ==========
	//   Input
	// ==========
	originalString := `abcdefghijklmnopqrstuvwxyz....0123456789
不極，物片類書車裡！十今果半接國先雄
ニッポン」「ニホン」両方使用される中
🚗🚓🚨🚲🚡🚅🛶💺🚏🏦🕋🏦📱⌚️🖲🕯🔮🎎🎐💌📦
📌☮️💟🔯☪️㊗️🈵🆚💯❕🔞🚷🔰⁉️⚠️💤🌐🌀▶️🔠🔣↔️↩️👁‍🗨
◽️🔲🇵🇦🏳️🏳️‍🌈🇹🇲🇹🇷🤛🤜🏼👍🏽👌☝🏼🥝🥦🌶🌽🍎
🍲🍔🥞🍝🍔🍗🌮🍯🥠🥢🍴🥄🥂☕️😀😃😄🤣😂😅😆☺️😊😍😌
😘😗😙😚😜😝😛😋🤨🧐🤓😒😏🤩🤩😎😞😔😖😢😣☹️😩🙁🤯
😰😓😦😲🤒🤕👿👹👽✊🏼
には文중국, 일본, 베트남 등 한자 문화권에 속하는 아시아 여러 국가에서는 
한국어的差异外，通常认为还存在词汇上的差异。例如繁体中文里多用的“原
 لمنطقة الشرق الأوسط هيلي: التحرك ضد إيران سيبدأ من مجلس الأمن`

	// ==========
	//   Output
	// ==========
	fmt.Println(removeemoji.FromString(originalString))

	// Result:
	// abcdefghijklmnopqrstuvwxyz....0123456789
	// 不極，物片類書車裡！十今果半接國先雄
	// ニッポン」「ニホン」両方使用される中
	// 
	// 
	// 
	// 
	// 
	// 
	// 
	// には文중국, 일본, 베트남 등 한자 문화권에 속하는 아시아 여러 국가에서는 
	// 한국어的差异外，通常认为还存在词汇上的差异。例如繁体中文里多用的“原
	//  لمنطقة الشرق الأوسط هيلي: التحرك ضد إيران سيبدأ من مجلس الأمن
}
```
