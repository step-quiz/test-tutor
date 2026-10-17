# test-tutor

Eina per redactar la **bateria de respostes d'alumnes** (casos de prova) que fa servir un tutor
automàtic. Cada cas és una resposta inventada d'un alumne a un pas de l'exercici, etiquetada amb
el que el tutor hauria de fer davant d'aquella resposta.

La bateria actual és la **IC-002** (interval de confiança per a una proporció): reforç previ
`PRE` (VARP) i passos `1`, `2` i `3`.

## Com funciona

Tot és un sol fitxer, `index.html` (HTML + CSS + JS, sense dependències ni compilació).
Només carrega la tipografia Source Serif 4 de Google Fonts.

- **Pestanya «Casos»**: una graella pas × categoria mostra quantes fitxes hi ha omplertes. Per a
  cada fitxa s'escriu la resposta de l'alumne i se'n marca: etiquetes, nota de l'autor, acció
  preferida, codi de diagnòstic i parella mínima. Una fitxa es pot moure a una altra cel·la.
- **Pestanya «Trajectòries»**: seqüències de torns (diàlegs de diversos missatges).
- **Categories** (`CATS`): `CORR` (correcte), `INFO` (entén però escriu malament), `KEY` (terme
  sense idea), `TYP` (lloro), `GAP` (perdut) i `PREM` (s'avança al pas següent). Les etiquetes
  disponibles depenen de la categoria (`TAG_BASE`) i, per a alguns casos, del pas (`TAG_STEP`).

## Dades

- La feina es desa automàticament al `localStorage` del navegador (clau `bateria-ic002`).
  No s'envia enlloc: si canvies de navegador o d'ordinador, cal fer servir la còpia de seguretat.
- **Exporta** ofereix:
  - `casos_IC002.csv` (o copiar-lo al porta-retalls), amb les columnes `id, pas, categoria,
    input_alumne, expected_advance, expected_action, expected_diagnostic, tags, parella,
    notes_autor`. Només hi surten les fitxes omplertes.
  - `trajectories_IC002.json`.
  - `bateria_copia.json`: còpia de seguretat completa, que es recupera amb **Carrega còpia**.
  - **Comença de zero**: esborra el que hi ha al navegador i torna a la bateria inicial.

## Publicació

Pàgina estàtica: n'hi ha prou de servir `index.html`; també funciona obrint-lo directament
amb el navegador.
