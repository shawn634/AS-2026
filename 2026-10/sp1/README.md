SP1 Kroužky
6

Formátování tabulky je úplně na hovno udělaný. U cen je tam někde napsaný KČ a někde ne, u dnů je po, út, st..... a někde tam je pondělí a čtvrtek, u zaplaceno někde je ano/ne a někde není vůbec nic. Těchto věcí je tam mnoho.

ty tři tabulky rozdělí to první tabulku a k tomu správně


```mermaid
erDiagram
    ZAKAZNIK ||--o{ OBJEDNAVKA : "zadává"
    OBJEDNAVKA ||--|{ POLOZKA : "obsahuje"
    PRODUKT ||--o{ POLOZKA : "je v"

    ZAKAZNIK {
        int id PK
        string jmeno
        string prijmeni
        string mesto
        string email
    }
    OBJEDNAVKA {
        int cislo PK
        date datum
        int id_zakaznika FK
    }
    PRODUKT {
        int id PK
        string nazev
    }
    POLOZKA {
        int id_objednavky FK
    }
```


```sql
SELECT nazev, cena
FROM krouzky
WHERE cena > 500;
```