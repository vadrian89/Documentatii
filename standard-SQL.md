# Standardul folosit in SQL va fi trecut aici. #
Forma va fi: \<element\>: \<sintaxa\>    

Schema: nume_proiect  
Tabela: (2 - 4 caractere din schema)\_(ma|tr|hs)\_nume_tabela
-   ma -> tabele master
-   tr -> tabele tranzactionale
-   hs -> tabele istoric (history)  

Nume Coloana: (2 - 4 caractere din nume tabela)\_nume_coloana
Secventa: sq_nume_coloana
Constraint: nume_coloana_(fk|nn|uq)
-   fk -> cheie straina (foreign key)
-   nn -> nenul (not null)
-   nn -> unic (unique)

Exemplu:  

```SQL
Nume proiect: gest_app
Schema: gest_app
Tabela: ga_ma_tabela_master
Coloana: tm_o_valoare
-   tm -> tabela master 
Secventa: sq_cheie_primare
Constraint: fk_cheie_straina
```

