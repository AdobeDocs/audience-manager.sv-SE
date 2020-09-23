---
description: Kod som krävs av DART Enterprise (och andra måltyper) för att hämta UUID-värdet (Audience Manager unique user ID).
seo-description: Kod som krävs av DART Enterprise (och andra måltyper) för att hämta UUID-värdet (Audience Manager unique user ID).
seo-title: get_aamCookie-kod
solution: Audience Manager
title: get_aamCookie-kod
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 11%

---


# get_aamCookie-kod {#get-aamcookie-code}

Kod som krävs av [!DNL DART Enterprise] (och andra måltyper) för att hämta värdet för det unika användar-ID:t ([!DNL UUID]) för Audience Manager.

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
