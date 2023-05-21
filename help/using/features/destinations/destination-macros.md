---
description: Beskriver makrona som du kan lägga till i en mål-URL.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Beskrivning av destinationsmakron
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 1%

---

# Beskrivning av destinationsmakron {#destination-macros-defined}

Beskriver makrona som du kan lägga till i ett mål [!DNL URL].

<!-- destination-macros.xml -->

När en [!DNL URL] mål kan du infoga följande makron i [!DNL URL] sträng. Kontrollera med din data-/målpartner om korrekt makroplacering i destinationen [!DNL URL].

>[!NOTE]
>
>Makron är valfria om inte annat anges. *Kursiv* används för att ange en variabelplatshållare.

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
   <td colname="col2"> <p>Obligatoriskt. </p> <p>Definierar platsen för det mappade segmentvärdet i en mål-URL. Oftast är det här <i>Segment-ID</i>, men kan också vara integreringskoden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Infogar användarens <span class="keyword"> Audience Manager</span> ID till mål-URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>The <i>datakälla-ID</i> motsvarar identifieraren för en datakälla som skickas till makrot. </p> <p>Låt oss titta på hur detta fungerar i ett enkelt exempel. I det här fallet har vi en <span class="keyword"> Audience Manager</span> partner med följande ID:n och villkor: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datakällans ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Ett internt kund-ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Deklarerat ID: Partnern vill skicka in dessa värden som deklarerat ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Så här gör du med <code>%dpid_<i>data source id</i>%</code>, <span class="keyword"> Audience Manager</span> partner skulle formatera makrot så här: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>Makrot kommer att ersätta <code> 1</code> med <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Anger om GDPR-reglerna gäller för besökaren eller inte. Använd det här makrot för att inkludera samtycke i segment som skickas till URL-adresser som är integrerade med IAB. Se <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plugin-programmet Audience Manager för IAB TCF</a> för mer information.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Medgivandesträngen (inklusive IAB-leverantörs-ID) som samlas in när besökare ger eller nekar samtycke på din webbplats. Använd det här makrot för att inkludera medgivandesträngen i segment som skickas till URL-mål som är integrerade med IAB. Ersätt <code>XXXX</code> med målpartner-ID:t. Se <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plugin-programmet Audience Manager för IAB TCF</a> för mer information. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Identifierar det protokoll som används på den överordnade webbsidan och infogar det i mål-URL:en. Exempel:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">om webbsidan är <b>https</b>/aam_client.com kommer det här makrot att ersättas med <b>https</b>/url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">om webbsidan är <b>http</b>/aam_client.com kommer det här makrot att ersättas med <b>http</b>/url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Infogar <span class="keyword"> Experience Cloud</span> ID till mål-URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Infogar <span class="wintitle"> Datainsamlingsserver (DCS)</span> till mål-URL:en. För att minimera fördröjning gör besökaren ett HTTP-anrop till <span class="keyword"> Audience Manager</span>, omdirigeras de till närmaste <span class="wintitle"> DCS</span> datacenter. Detta uppnås med DNS, som kan identifiera besökarens plats och dirigera dem till rätt datacenter. </p> </td> 
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

The `%rnd%` och `%timestamp%` makron infogar unika värden i en [!DNL URL] för att förhindra webbläsarcachelagring.

## Cache Busting med `%rnd%` och `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Webbläsare cachelagrar (spara) ofta begärt innehåll i minnet. När en sida läses in kommer sparat innehåll att användas från cacheminnet i stället för från en fjärrserver. Den här processen hjälper till att hålla effektiv nedladdningstid eftersom data används lokalt i stället för från en annan plats. Men eftersom cachelagring inte kräver något serveranrop kan det fördröja rapporteringen genom att artificiellt minska antalet unika begäranden.

Cache-lagring förhindrar att webbläsare sparar och återanvänder innehåll. Den här tekniken använder kod som infogar ett slumpmässigt tal eller en tidsstämpel i en URL-sträng, vilket gör att koden ser unik ut i webbläsaren. Resultatet blir att varje `HTTP` anropet räknas som en separat begäran till servern. Genom att tvinga fram ett nytt serveranrop för varje begäran kan du bibehålla rapporteringsnoggrannheten och minska diskrepanser. [!DNL Audience Manager] innehåller två makron för cachepublicering:

* `%rnd%`: Infogar ett slumpmässigt tal i en URL.
* `%timestamp%`: Infogar Unix-datum/tid i en URL.

## Jämför `%rnd%` och `%timestamp%` {#compare-rnd-timestamp}

Båda makrona förhindrar cachelagring, men `%rnd%` kan vara mer effektivt. Med till exempel `%timestamp%`om flera användare visar en sida samtidigt får de samma datum/tid-värde. Resultatet blev att [!DNL URL] är inte unikt och flera samtal räknas bara en gång. Men `%rnd%` genererar ett unikt numeriskt värde för varje anrop (även när användarna ser samma sida samtidigt). Detta innebär att [!DNL URL] strängen innehåller olika värden och räknas som unik.

>[!MORELIKETHIS]
>
>* [Beskrivning av destinationsmakron](../../features/destinations/destination-macros.md#destination-macros-defined)

