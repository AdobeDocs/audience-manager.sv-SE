---
description: Beskriver makrona som du kan lägga till i en mål-URL.
seo-description: Beskriver makrona som du kan lägga till i en mål-URL.
seo-title: Målmakron definierade
solution: Audience Manager
title: Målmakron definierade
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
translation-type: tm+mt
source-git-commit: da0eb0244fc3ae158fa151727f4253625dcff2c4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---


# Målmakron definierade {#destination-macros-defined}

Beskriver makrona som du kan lägga till i ett mål [!DNL URL].

<!-- destination-macros.xml -->

När du skapar ett [!DNL URL] mål kan du infoga följande makron i [!DNL URL] strängen. Kontrollera med data-/målpartnern om makroplaceringen är rätt inom målet [!DNL URL].

>[!NOTE]
>
>Makron är valfria om inte annat anges. *Kursiv anger* en variabelplatshållare.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Förklaring </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Obligatoriskt. </p> <p>Definierar platsen för det mappade segmentvärdet i en mål-URL. Vanligtvis är detta <i>segment-ID</i>, men det kan också vara integreringskoden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Infogar användarens <span class="keyword"> Audience Manager</span> -ID i mål-URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>ID:t för <i>datakällan</i> motsvarar identifieraren för en datakälla som skickas till makrot. </p> <p>Låt oss titta på hur detta fungerar i ett enkelt exempel. I det här fallet har vi en <span class="keyword"> Audience Manager</span> -partner med följande ID:n och villkor: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datakällans ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Ett internt kund-ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Deklarerat ID: Partnern vill skicka in dessa värden som deklarerat ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Om du vill göra det med <code>%dpid_<i>data source id</i>%</code>programmet formaterar <span class="keyword"> Audience Manager</span> -partnern makrot så här: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>Makrot ersätts <code> 1</code> med <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Baserat på AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Anger om GDPR-reglerna gäller för besökaren eller inte. Använd det här makrot för att inkludera samtycke i segment som skickas till URL-adresser som är integrerade med IAB. Mer information finns i Plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF</a> .</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Medgivandesträngen (inklusive IAB-leverantörs-ID) som samlas in när besökare ger eller nekar samtycke på din webbplats. Använd det här makrot för att inkludera medgivandesträngen i segment som skickas till URL-mål som är integrerade med IAB. Ersätt <code>XXXX</code> med målpartner-ID:t. Mer information finns i Plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF</a> . </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Identifierar det protokoll som används på den överordnade webbsidan och infogar det i mål-URL:en. Exempel:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">om webbsidan är <b>/aam_client.com:/kommer det här makrot att ersättas med</b>https <b></b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">om webbsidan är <b>/aam_client.com:/kommer det här makrot att ersättas med</b>/url-destination.com <b></b>:/ </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Infogar <span class="keyword"> Experience Cloud</span> -ID i mål-URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Infogar <span class="wintitle"> DCS-regionen (Data Collection Server)</span> i mål-URL:en. För att minimera fördröjningen omdirigeras de till närmaste <span class="keyword"> DCS</span>-datacenter när besökaren gör ett HTTP-anrop till <span class="wintitle"> Audience Manager</span> . Detta uppnås med DNS, som kan identifiera besökarens plats och dirigera dem till rätt datacenter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Utför en cachebustningsfunktion genom att infoga ett slumpmässigt tal i mål-URL:en. Detta förhindrar att webbläsare visar cachelagrat innehåll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Infogar en UNIX-tidsstämpel i mål-URL för att förhindra att webbläsare visar cachelagrat innehåll. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cachebuffring med målmakron {#destination-cache-busting}

Makrona `%rnd%` och `%timestamp%` infogar unika värden i en [!DNL URL] sträng för att förhindra webbläsarcachelagring.

## Cache Busting med `%rnd%` och `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Webbläsare cachelagrar (spara) ofta begärt innehåll i minnet. När en sida läses in kommer sparat innehåll att användas från cacheminnet i stället för från en fjärrserver. Den här processen hjälper dig att hålla effektiv nedladdningstid eftersom data används lokalt i stället för från en annan plats. Men eftersom cachelagring inte kräver något serveranrop kan det fördröja rapporteringen genom att artificiellt minska antalet unika begäranden.

Cache-lagring förhindrar att webbläsare sparar och återanvänder innehåll. Den här tekniken använder kod som infogar ett slumpmässigt tal eller en tidsstämpel i en URL-sträng, vilket gör att koden ser unik ut i webbläsaren. Därför räknas varje `HTTP` anrop som en separat begäran till servern. Genom att tvinga fram ett nytt serveranrop för varje begäran kan du bibehålla rapporteringsnoggrannheten och minska diskrepanser. [!DNL Audience Manager] innehåller två makron för cachepublicering:

* `%rnd%`: Infogar ett slumpmässigt tal i en URL.
* `%timestamp%`: Infogar Unix-datum/tid i en URL.

## Jämföra `%rnd%` och `%timestamp%` {#compare-rnd-timestamp}

Båda makrona förhindrar cachelagring, men de `%rnd%` kan vara mer effektiva. Om flera användare till exempel `%timestamp%`visar en sida samtidigt får de samma datum/tid-värde. Resultatet blir att [!DNL URL] anropet inte är unikt och flera anrop räknas bara en gång. Men `%rnd%` genererar ett unikt numeriskt värde för varje anrop (även när användarna ser samma sida samtidigt). Det innebär att [!DNL URL] strängen innehåller olika värden och räknas som unik.

>[!MORELIKETHIS]
>
>* [Målmakron definierade](../../features/destinations/destination-macros.md#destination-macros-defined)