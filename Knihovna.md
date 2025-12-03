# Knihovna
# Funkční požadavky
1. Registrace a přihlášení
2. Prohlížení seznamu knih
3. Vyhledávání knih
4. Zobrazení knihy v detailu
5. Vytvoření vypůjčení knihy
6. Zobrazení seznamu vypůjčených knih
7. Oznamení o vypůjčených knihách 
8. Přidávání a úprava knih
9. Změna knih
10. Evidence vypůjčených knih
11. Přijímání vrácených knih
12. Správa uživatelů

# Datový konceptuální model
## Uživatel
1. id_uživatele
2. jmeno
3. prijmeni
4. email
5. heslo
6. role

## Kniha
1. id_kniha
2. nazev
3. popis
4. autor
5. zanr
6. pocet_dostupnych_knih
7. celkovy_pocet_knih

## Vypujcene
1. id_vypujcky
2. id_uzivatele
3. id_knihy
4. datum_vypujceni
5. datum_vraceni
6. stav

# Charakteristika funkčností aplikace
1. Uživatelské rozhraní
- Umožňuje vidět pouze vypůjčené knihy a katalog knih 
2. Knihovník rozhranní
- Umožňuje vidět uživatele, měnit katalog, měnit knihy, mazat knihy
3. Admin rozhranní 
- Umožňuje mazat uživatle a měnit systém 
4. Výpůjčkový systém
- Umožňuje rezervaci, vypůjčení, vrácení pokud je kniha dostupná
5. Katalog knih
- Umožňuje vyhledání, zobrazení, filtrování
6. Zobrazení detailu knihy
- Umožňuje zobrazit knihu v detailu

# Popis architektury aplikace
1. Front-end
 - HTML - struktura 
 - CSS - vzhled
 - JavaScript - kontrola
2. Back-end
 - PHP - logika
 - MVC - oddělení model, view, controller
3. Data
 - MySQL DB - data

 # Třídy
 1. USER
    login(email,heslo) - Kontrola emailu a hesla v DB
    register(user) - Získání dat z formuláře, uložení do DB
    getID(id) - Získání ID uživatele
    getBorrow() - Získání půjčených knih uživatele a uložení nových    knih 
    checkAdmin() - Kontrola zda se jadná o admina
    checkLibrarian - Kontrola zda se jedná o knihovníka
2. Book
    getAll() - Získání všech knih
    getId(id) - Získání id knihy
    search(keyword) - Hledat a filtrovat
    add(data) - přidat a smazat novou knihu 
    update(id, data) - úprava knihy
    deleteBook() - ubrat knihu ze skladu pokud je půjčena
    addBook() - přidat knihu na sklad pokud je vrácena
3. Borrow
    create(userId,bookId) - Vytvoření výpůjčky
    getUser(userId) - Získání dat k uživately a půjčeným knihám
    getAll() - Získání všech výpůjček
    returned(id) - Vrácené knihy
4. Database
    connect() - Připojení k DB
    query() - Otázky
    execute() - Potvrzení