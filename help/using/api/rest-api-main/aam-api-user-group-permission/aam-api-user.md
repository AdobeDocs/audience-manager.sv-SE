---
description: Resten av API-metoder för att hantera användare, inklusive att skapa, uppdatera, lista, ta bort och returnera användarobjekt.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: API-metoder för användarhantering
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# API-metoder för användarhantering {#user-management-api-methods}

Vila [!DNL API] metoder för att hantera användare, inklusive att skapa, uppdatera, lista, ta bort och returnera användarobjekt.

<!-- c_rest_api_user_man_user.xml -->

## Skapa en användare {#create-user}

A `POST` metod för att skapa en ny användare.

<!-- r_rest_api_user_create.xml -->

### Begäran

`POST /api/v1/users/`

### Exempelbegärandetext

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

If `isAdmin` är inställt på true, och användaren skapas som partneradministratör. Den här egenskapen talar också om för dig om en användare är partneradministratör eller inte.

Returnerar `409 Conflict` om användarnamnet redan används.

## Uppdatera en användare {#update-user}

A `PUT` metod för att uppdatera en användare.

<!-- r_rest_api_user_update.xml -->

### Begäran

`PUT /api/v1/users/`*`<userId>`*

### Exempelbegärandetext

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

A `PUT` för att uppdatera den inloggade användaren.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>De [!DNL API] Metoderna kan bara anropas av partneradministratörer. Den här metoden kan anropas av icke-adminanvändare.

### Begäran

`PUT /self/update`

### Exempelbegärandetext

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

A `PUT` för att uppdatera den inloggade användaren.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>De [!DNL API] Metoderna kan bara anropas av partneradministratörer. Den här metoden kan anropas av icke-adminanvändare.

### Begäran

`POST /users/self/update-password`

### Exempelbegärandetext

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returnerar `200 OK` om det lyckas. Returnerar `400 Bad Request` om något är fel med något av lösenorden.

## Återställ inloggat användarlösenord {#reset-logged-in-user-pw}

A `PUT` för att återställa den inloggade användaren. [!UICONTROL Audience Management] skickar ett systemgenererat lösenord till användaren.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>De [!DNL API] Metoderna kan bara anropas av partneradministratörer. Den här metoden kan anropas av icke-adminanvändare.

### Begäran

`POST /self/reset-password`

Returnerar `200 OK` om det lyckas.

## Returnera användarobjekt för ett användar-ID {#return-user-object-for-id}

A `Get` metod som returnerar användarobjektet för ett användar-ID.

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

A `Get` metod som returnerar användarobjektet för den inloggade användaren.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>De [!DNL API] Metoderna kan bara anropas av partneradministratörer. Den här metoden kan anropas av icke-adminanvändare.

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

A `GET` metod för att lista användare.

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

A `DELETE` metod för att ta bort en användare.

<!-- r_rest_api_user_delete.xml -->

### Begäran

`DELETE /api/v1/users/`*`<user_id>`*

Returnerar `204 No Content` om det lyckas. Om en konflikt uppstår returneras `409 Conflict`.

## Ta bort användare gruppvis {#delete-users-bulk}

A `POST` metod för att ta bort flera användare samtidigt.

<!-- r_rest_api_user_delete_bulk.xml -->

### Begäran

`POST /api/v1/users/bulk-delete`

### Exempelbegärandetext

```
{[<user_id_1>, <user_id_2>, ...]}
```
