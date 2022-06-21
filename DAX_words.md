## CONSULTAS

```ssh
EVALUATE    EVALUATE <table>
ORDER BY    [ORDER BY {<expression> [{ASC | DESC}]}[, …]  
START AT    [START AT {<value>|<parameter>} [, …]]]
DEFINE      [DEFINE {  MEASURE <tableName>[<name>] = <expression> } {  VAR <name> = <expression>}] EVALUATE <table> 
            

EVALUATE('Internet Sales') ORDER BY 'Internet Sales'[Sales Order Number] START AT "SO7000"
DEFINE MEASURE 'Internet Sales'[Internet Total Sales] = SUM('Internet Sales'[Sales Amount])

```
