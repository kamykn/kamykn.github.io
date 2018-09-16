---
title: "Gormでdeleted_atつけてソフトデリートにする"
date: 2016-12-11T12:35:45+09:00
draft: false
tags:
- golang
- revel
<!-- thumbnailImagePosition: left -->
<!-- thumbnailImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city-750.jpg -->
<!-- coverImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city.jpg -->
<!-- metaAlignment: center -->
<!-- coverMeta: out -->
---

まずは上手く取れた記述から

<!--more-->

{{< highlight go "linenos=inline" >}}
package controllers

import (
    "github.com/revel/revel"
)

type Mycontroller struct {
    *revel.Controller
}


func (m *Mycontroller) Index() revel.Result {
    // redirectURLの取得
    requestedHost := m.Request.Host

    requestedScheme := "http"
    if m.Request.TLS != nil {
        requestedScheme = "https"
    }

    // ホスト名
    revel.TRACE.Println(requestedHost);

    // おまけにスキームも判断してみる（httpかhttpsか）
    revel.TRACE.Println(requestedScheme);
}

{{< / highlight >}}



# これで取れる理由
Controllerが継承している構造体を見ていくと、


[https://github.com/revel/revel/blob/master/controller.go:embed:cite]



{{< highlight go "linenos=inline" >}}
type Controller struct {
	Name          string          // The controller name, e.g. "Application"
	Type          *ControllerType // A description of the controller type.
	MethodName    string          // The method name, e.g. "Index"
	MethodType    *MethodType     // A description of the invoked action type.
	AppController interface{}     // The controller that was instantiated.
	Action        string          // The fully qualified action name, e.g. "App.Index"

	Request  *Request
	Response *Response
	Result   Result

	Flash      Flash                  // User cookie, cleared after 1 request.
	Session    Session                // Session, stored in cookie, signed.
	Params     *Params                // Parameters from URL and form (including multipart).
	Args       map[string]interface{} // Per-request scratch space.
	RenderArgs map[string]interface{} // Args passed to the template.
	Validation *Validation            // Data validation helpers
}
{{< / highlight >}}

Requestを継承している事がわかる。

Requestをもう少し見てみよう。

[https://golang.org/pkg/net/http/#Request:title]

{{< highlight go "linenos=inline" >}}
type Request struct {

        // 〜中略〜

        // URL specifies either the URI being requested (for server
        // requests) or the URL to access (for client requests).
        //
        // For server requests the URL is parsed from the URI
        // supplied on the Request-Line as stored in RequestURI.  For
        // most requests, fields other than Path and RawQuery will be
        // empty. (See RFC 2616, Section 5.1.2)
        //
        // For client requests, the URL's Host specifies the server to
        // connect to, while the Request's Host field optionally
        // specifies the Host header value to send in the HTTP
        // request.
        URL *url.URL

        // 〜中略〜

        // For server requests Host specifies the host on which the
        // URL is sought. Per RFC 2616, this is either the value of
        // the "Host" header or the host name given in the URL itself.
        // It may be of the form "host:port".
        //
        // For client requests Host optionally overrides the Host
        // header to send. If empty, the Request.Write method uses
        // the value of URL.Host.
        Host string

        // 〜中略〜

        // RequestURI is the unmodified Request-URI of the
        // Request-Line (RFC 2616, Section 5.1) as sent by the client
        // to a server. Usually the URL field should be used instead.
        // It is an error to set this field in an HTTP client request.
        RequestURI string

        // 〜中略〜

        // TLS allows HTTP servers and other software to record
        // information about the TLS connection on which the request
        // was received. This field is not filled in by ReadRequest.
        // The HTTP server in this package sets the field for
        // TLS-enabled connections before invoking a handler;
        // otherwise it leaves the field nil.
        // This field is ignored by the HTTP client.
        TLS *tls.ConnectionState

        // 〜中略〜

}
{{< / highlight >}}

Requestの中で、この3つが使えそうだ。

- URL *url.URL
- Host string
- TLS *tls.ConnectionState

### URL
まずはこれが良さそうなので、a.Request.URL.Hostとa.Request.URL.Schemeを取ってみるも、空の文字列が返ってくる。


理由はコメントに書いてあった。最近すこぶる性能が良くなったGoogle翻訳にコメント部分を突っ込んでみる

> For server requests the URL is parsed from the URI supplied on the Request-Line as stored in RequestURI.  

> サーバ要求の場合、URLはRequestURIに格納されているRequest-Lineで指定されたURIから解析されます。

ということで、RequestURIに格納されている文字列をParseしたものなので、そもそもRequestURIにはホスト名が含まれていなかったので得ることができなかった。

### Host
これはホスト名を得ることが出来た。port番号が指定されていればportつきで取得できる。

### TLS
上記でホスト名取得ができたがこちらも見ておく。

> The HTTP server in this package sets the field for TLS-enabled connections before invoking a handler; otherwise it leaves the field nil.

> このパッケージのHTTPサーバーは、ハンドラを呼び出す前にTLS対応接続のフィールドを設定します。 それ以外の場合は、フィールドはnilになります。

ほほう。TLSでの接続じゃない場合、nilになるとのこと。ということでここのnilチェックでhttpかhttpsが判別できそう。


ということで、ブログ冒頭のようにホスト名取得（とおまけにhttp/httpsの判別)ができた。
