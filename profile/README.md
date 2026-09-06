Architecture du projet :

```mermaid
architecture-beta
    group serendipity(cloud)[Serendipity]
    group extern(internet)[Exterieur]

    service sfrontend(internet)[Serendipity Frontend] in extern
    service suser(server)[Srendipity User] in serendipity
    service srecipe(server)[Serendipity Recipe] in serendipity
    service sai(server)[Serendipity AI] in serendipity
    service sauth(server)[Serendipity Auth] in serendipity

    sfrontend:R --> L:sauth
    sauth:R --> L:suser
    sauth:R --> L:sai
    sauth:R --> L:srecipe

    align column sai suser srecipe
    align row sfrontend sauth suser
```
