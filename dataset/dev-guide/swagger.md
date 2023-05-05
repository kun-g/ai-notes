---
title: "Swagger文档规范"
description: ""
lead: ""
date: 2022-12-01T19:37:36+08:00
lastmod: 2022-12-01T19:37:36+08:00
draft: false
images: []
menu:
  docs:
    parent: "dev-guide"
    identifier: "swagger-3fb4b817c79162fa75e4a98d7a267ef7"
weight: 999
toc: true
---

# Swgger注释规范

[规范](https://github.com/swaggo/swag/blob/master/README_zh-CN.md)

## goswagger
`go install github.com/go-swagger/go-swagger/cmd/swagger@latest`

`swagger generate spec -o swagger.yml`
`swagger serve --no-open -F=swagger --port 36666 swagger.yml`

## 语法

[Meta](https://goswagger.io/use/spec/meta.html)

swagger:route：
代表 API 接口描述的开始，后面的字符串格式为HTTP方法 URL Tag ID。可以填写多个 tag，相同 tag 的 API 接口在 Swagger 文档中会被分为一组。ID 是一个标识符，swagger:parameters是具有相同 ID 的swagger:route的请求参数。swagger:route下面的一行是该 API 接口的描述，需要以英文点号为结尾。responses:定义了 API 接口的返回参数，例如当 HTTP 状态码是 200 时，返回 createUserResponse，createUserResponse 会跟swagger:response进行匹配，匹配成功的swagger:response就是该 API 接口返回 200 状态码时的返回。

swagger:response：
定义了 API 接口的返回，例如 getUserResponseWrapper，关于名字，我们可以根据需要自由命名，并不会带来任何不同。getUserResponseWrapper 中有一个 Body 字段，其注释为// in:body，说明该参数是在 HTTP Body 中返回。swagger:response之上的注释会被解析为返回参数的描述。api.User 自动被 go-swagger 解析为Example Value和Model。我们不用再去编写重复的返回字段，只需要引用已有的 Go 结构体即可，这也是通过工具生成 Swagger 文档的魅力所在。

swagger:parameters：
定义了 API 接口的请求参数，例如 userParamsWrapper。userParamsWrapper 之上的注释会被解析为请求参数的描述，// in:body代表该参数是位于 HTTP Body 中。同样，userParamsWrapper 结构体名我们也可以随意命名，不会带来任何不同。swagger:parameters之后的 createUserRequest 会跟swagger:route的 ID 进行匹配，匹配成功则说明是该 ID 所在 API 接口的请求参数。