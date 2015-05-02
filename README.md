# WechatJS
Javascript module for Wechat JS API

License : MIT

## Installation

Add in your bower.json file :

```
"dependencies": {
    "WechatJS": "0.5.0"
}
```

```
bower install
```

## Use

As the JavaScript module uses external libraries, it will be required to manually add them. An example of module inclusion with Twig template :

```
{% javascripts '@MyBundle/Resources/public/libs/jssha/src/sha1.js' %}
    <script src="{{ asset_url }}">
    </script>
{% endjavascripts %}
{% javascripts '@MyBundle/Resources/public/libs/WechatJS/libs/jweixin/jweixin-1.0.0.js' %}
    <script src="{{ asset_url }}">
    </script>
{% endjavascripts %}
{% javascripts '@MyBundle/Resources/public/libs/WechatJS/javascript/WechatJS.js' %}
    <script src="{{ asset_url }}">
    </script>
{% endjavascripts %}
```

Call the function initialize and set the sharing properties.

```
WechatJS.initialize(
    wechatJsToken,
    appId,
    title,
    description,
    link,
    picture
);
```

 - wechatJsToken : the WeChat JS API Token, can be get by using WechatBundle ( https://github.com/jean553/WechatBundle ),
 - appId : application ID, can be found on WeChat Public Account,
 - title : title of the sharing popup,
 - description : description of the sharing popup,
 - link : redirection URL after click on the sharing popup,
 - picture : absolute path of the sharing popup picture

The sharing popup is the same when user shares directly to other users or publish on his Moment wall.

## Get WeChat JS API Token

The WeChat JS API Token can be get by using WechatBundle ( https://github.com/jean553/WechatBundle ). First, install this bundle as described on the installation procedure.

Then, get the WeChat JS API token :

```
$ticket = $wechatService->getJSAPITicket();
```

It is necessary to enable WeChat JS API on WeChat Public Account.
