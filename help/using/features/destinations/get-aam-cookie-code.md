---
description: Kod som krävs av DART Enterprise (och andra måltyper) för att hämta Audience Manager-värdet för ett unikt användar-ID (UUID).
seo-description: Kod som krävs av DART Enterprise (och andra måltyper) för att hämta Audience Manager-värdet för ett unikt användar-ID (UUID).
seo-title: get_aamCookie-kod
solution: Audience Manager
title: get_aamCookie-kod
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Code {#get-aamcookie-code}

Kod som krävs av [!DNL DART Enterprise] (och andra måltyper) för att hämta Audience Manager-värdet för unikt användar-ID ([!DNL UUID]).

Definiera den här funktionen överst på sidan, helst inuti `<head>` kodblocket.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
