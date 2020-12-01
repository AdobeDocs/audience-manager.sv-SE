---
description: Resten av API-metoder för att hantera användare, inklusive att skapa, uppdatera, lista, ta bort och returnera användarobjekt.
seo-description: Resten av API-metoder för att hantera användare, inklusive att skapa, uppdatera, lista, ta bort och returnera användarobjekt.
seo-title: API-metoder för användarhantering
solution: Audience Manager
title: API-metoder för användarhantering
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---


# API-metoder för användarhantering {#user-management-api-methods}

Återställ [!DNL API]-metoder för att hantera användare, inklusive att skapa, uppdatera, lista, ta bort och returnera användarobjekt.

<!-- c_rest_api_user_man_user.xml -->

## Skapa en användare {#create-user}

En `POST`-metod för att skapa en ny användare.

<!-- r_rest_api_user_create.xml -->

### Begäran

`POST /api/v1/users/`

### Exempelbegärandebrödtext

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Svar

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Om `isAdmin` är true skapas användaren som partneradministratör. Den här egenskapen talar också om för dig om en användare är partneradministratör eller inte.

Returnerar `409 Conflict` om användarnamnet redan används.

## Uppdatera en användare {#update-user}

En `PUT`-metod för att uppdatera en användare.

<!-- r_rest_api_user_update.xml -->

### Begäran

`PUT /api/v1/users/`*`<userId>`*

### Exempelbegärandebrödtext

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Svar

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Returnerar `409 Conflict` om användarnamnet redan används.

## Uppdatera inloggad användare {#update-logged-in-user}

En `PUT`-metod för att uppdatera den inloggade användaren.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>De flesta [!DNL API]-metoder kan bara anropas av partneradministratörer, men den här metoden kan anropas av icke-adminanvändare.

### Begäran

`PUT /self/update`

### Exempelbegärandebrödtext

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Svar

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Returnerar `409 Conflict` om användarnamnet redan används.

## Uppdatera inloggat användarlösenord {#update-logged-in-user-pw}

En `PUT`-metod för att uppdatera den inloggade användaren.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>De flesta [!DNL API]-metoder kan bara anropas av partneradministratörer, men den här metoden kan anropas av icke-adminanvändare.

### Begäran

`POST /users/self/update-password`

### Exempelbegärandebrödtext

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returnerar `200 OK` om det lyckas. Returnerar `400 Bad Request` om något är fel med något av lösenorden.

## Återställ inloggat användarlösenord {#reset-logged-in-user-pw}

En `PUT`-metod som återställer den inloggade användaren. [!UICONTROL Audience Management] skickar ett systemgenererat lösenord till användaren.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>De flesta [!DNL API]-metoder kan bara anropas av partneradministratörer, men den här metoden kan anropas av icke-adminanvändare.

### Begäran

`POST /self/reset-password`

Returnerar `200 OK` om det lyckas.

## Returnera användarobjekt för ett användar-ID {#return-user-object-for-id}

En `Get`-metod som returnerar användarobjektet för ett användar-ID.

<!-- r_rest_api_user_get_user_obj.xml -->

### Begäran

`GET /api/v1/users/`*`<userId>`*

### Svar

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Returnera användarobjekt för inloggad användare {#return-user-object-for-logged-in-user}

En `Get`-metod som returnerar användarobjektet för den inloggade användaren.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>De flesta [!DNL API]-metoder kan bara anropas av partneradministratörer, men den här metoden kan anropas av icke-adminanvändare.

### Begäran

`GET /api/v1/users/self`

### Svar

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Listanvändare {#list-users}

En `GET`-metod för att lista användare.

<!-- r_rest_api_user_list.xml -->

### Begäran

`GET /api/v1/users/`

Du kan ange flera grupp-ID:n i frågeparametrarna:

`GET /api/v1/users/?groupId=343&groupdId=12`

Den här frågan returnerar en lista med alla användare i de angivna grupperna.

### Svar

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Ta bort en användare {#delete-users}

En `DELETE`-metod för att ta bort en användare.

<!-- r_rest_api_user_delete.xml -->

### Begäran

`DELETE /api/v1/users/`*`<user_id>`*

Returnerar `204 No Content` om det lyckas. Vid en konflikt returneras `409 Conflict`.

## Ta bort användare gruppvis {#delete-users-bulk}

En `POST`-metod för att ta bort flera användare samtidigt.

<!-- r_rest_api_user_delete_bulk.xml -->

### Begäran

`POST /api/v1/users/bulk-delete`

### Exempelbegärandebrödtext

```
{[<user_id_1>, <user_id_2>, ...]}
```
