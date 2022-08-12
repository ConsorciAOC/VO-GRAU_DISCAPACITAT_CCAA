# VO - GRAU_DISCAPACITAT_CCAA


## INDEX

- [1. Introducció](#1)
- [2. Transmissions de dades disponibles](#2)
- [3. Missatgeria del servei](#3)
   * [3.1 Consulta del grau de discapacitat (GRAU_DISCAPACITAT_CCAA)](#3.1)
        * [3.1.1 Petició	dades genèriques](#3.1.1)
		* [3.1.2 Petició	dades específiques](#3.1.2)
		* [3.1.3 Resposta dades específiques](#3.1.3)
-  [4. Joc de proves](#4)        


# 1	Introducció <a name="1"></a>
Aquest document detalla la missatgeria associada al servei de consulta de Grau de Discapacitat de la resta de CCAA de l'Estat.

Per poder realitzar la integració cal conèixer prèviament la següent documentació: 

- [Document de Missatgeria Genèrica de la PCI del Consorci AOC.][PCI]
 
[PCI]:https://github.com/ConsorciAOC/PCI

# 2	Transmissions de dades disponibles <a name="2"></a>
Les dades disponibles a través del servei són les que es presenten a continuació:

EMISSOR: Comunitats autònomes de la resta de l'Estat

| **PRODUCTE** | **MODALITAT** | **DESCRIPCIO** |
|---|---|---|
| GRAU\_DISCAPACITAT\_CCAA | GRAU\_DISCAPACITAT\_CCAA | Consulta del grau de discapacitat. |

Les modalitats disposen de versió imprimible del resultat de la consulta en format PDF. Per més detalls adreceu-vos Extensions de missatgeria del document de missatgeria genèrica.

# 3	Missatgeria del servei <a name="3"></a>
A continuació es detalla la missatgeria corresponent al bloc de dades específiques de les modalitats de consum del producte.

>L'emissor de les dades requereix que s'informin les dades del funcionari que realitza la consulta. Així, cal informar els següents camps de l'element _Funcionario_ del bloc de dades genèriques:
>_/Peticion/Funcionario/NombreCompletoFuncionario,
>/Peticion/Funcionario/NifFuncionario,
>//SolicitudTransmision/DatosGenericos/Solicitante/Funcionario/NombreCompletoFuncionario i
>//SolicitudTransmision/DatosGenericos/Solicitante/Funcionario/NifFuncionario_

## 3.1	Consulta del grau de discapacitat (GRAU_DISCAPACITAT_CCAA) <a name="3.1"></a>
### 3.1.1	Petició	dades genèriques <a name="3.1.1"></a>

| Element | Descripció |
| --- | --- |
| //DatosGenericos/Titular/TipoDocumentacion | Tipus de documentació (NIF, DNI, NIE, Passaport). |
| //DatosGenericos/Titular/Documentacion | Documentació. |
| //DatosGenericos/Titular/Nombre | Nom del titular. |
| //DatosGenericos/Titular/Apellido1 | Primer cognom del titular. |
| //DatosGenericos/Titular/Apellido2 | Segon cognom del titular (obligatori si en té). |

## 3.1.2	Petició	dades específiques <a name="3.1.2"></a>

![Dades específiques](https://github.com/ConsorciAOC/VO-GRAU_DISCAPACITAT_CCAA/blob/main/images/3%201%202%20Petici%C3%B3%20dades%20espec%C3%ADfiques.png)

| Element | Descripció |
| --- | --- |
| /peticioConsultaDadesDiscapacitat/ccaa | Codi de comunitat autònoma: 01	- ANDALUCÍA, 02	- ARAGÓN, 03	- PRINCIPADO DE ASTURIAS, 04	- ISLAS BALEARES, 05	- CANARIAS ,06	- CANTABRIA, 07	- CASTILLA y LEÓN, 08	- CASTILLA-LA MANCHA, 09	- CATALUNYA, 10	- COMUNIDAD VALENCIANA, 11	- EXTREMADURA, 12	- GALICIA, 13	- MADRID, 14	- REGIÓN DE MURCIA, 15	- NAVARRA, 16	- PAÍS VASCO, 17	- LA RIOJA, 18	- CIUDAD DE CEUTA i 19	- CIUDAD DE MELILLA |
| /peticioConsultaDadesDiscapacitat/codiProvincia | Codi INE de província. |
| /peticioConsultaDadesDiscapacitat/dataConsulta | Data sobre la que	es	realitzarà	la	consulta (DD/MM/AAAA).|
| /peticioConsultaDadesDiscapacitat/dataNaixement | Data de naixement del titular consultat(DD/MM/AAAA). |
| /peticioConsultaDadesDiscapacitat/expedient | Número d'expedient del certificat de discapacitat. |
| /peticioConsultaDadesDiscapacitat/consentimentTipusDiscapacitat | Indica si el titular  ha donat el consentiment per consultar les dades (_S_/_N_). |

## 3.1.3	Resposta	dades específiques <a name="3.1.3"></a>

![Resposta dades específiques](https://github.com/ConsorciAOC/VO-GRAU_DISCAPACITAT_CCAA/blob/main/images/3%201%203%20Resposta%20dades%20espec%C3%ADfiques.png)

| _Element_ | _Descripció_ |
| --- | --- |
| respostaConsultaDadesDiscapacitat/peticioConsultaDadesDiscapacitat | Bloc de dades corresponent a la petició que genera la resposta. |
| respostaConsultaDadesDiscapacitat/resposta | Bloc de dades corresponent a la resposta. |
| //resposta/certificat | Bloc de dades corresponent al certificat de discapacitat del titular consultat. |
| //certificat/ccaa | Codidecomunitatautònoma. |
| //certificat/codiProvincia | Codi de comunitat autònoma. |
| //certificat/expedient | Número d'expedient del certificat de discapacitat. |
| //certificat/mobilitat/puntuacio | Dades relatives a dificultat de mobilitat del ciutadà. Indica la puntuació (valors d'1 a 15) |
| //certificat/mobilitat/factor | Dades relatives a dificultat de mobilitat del ciutadà. Factor que provoca les dificultats de mobilitat: A: usuari confinat en cadira de rodes, B: dependent de bastons i C: pot deambular però presenta conductes agressives o molestes de difícil control, a causa de les greus deficiències intel·lectuals que dificulten la utilització de mitjans normalitzats de transport. |
| //certificat/dependencia | Indica si té reconegut o no el barem de dependència (_S_/_N_).|
| //certificat/acompanyantTPublic | Indica si necessita d'acompanyant en un transport públic (_S_/_N_). |
| //certificat/grauDiscapacitat | Especifica el	grau	de	discapacitat	del	beneficiari (percentatge). |
| //certificat/tipusDiscapacitat | Tipus de discapacitat del titular sempre que la dada consentimentTipusDiscapacitat = S en la petició: FISICA, PSIQUICA i SENSORIAL. |
| //certificat/dataEfectes | Data des de la que el certificat de discapacitat és vàlid (DD/MM/AAAA). |
| //certificat/dataRevisio | Data en la que el certificat de discapacitat serà revisat (DD/MM/AAAA). |
| //certificat/validesaPermanent | Indica si el reconeixement del certificat de discapacitat es definitiu o no (_S_/_N_). |
| respostaConsultaDadesDiscapacidad/resultat/codiResultat | 0: existeix el certificat de discapacitat, 1: no hi ha enregistrat un titular amb les dades indicades, 2: no existeix el certificat de discapacitat, 3: la persona no està associada al número d'expedient de certificat indicat, 4:	format d'expedient de discapacitat incorrecte, 5: amb les dades facilitades existeix més d'un titular d'un certificat de discapacitat, 6: el titular consultat està en un procés de revisió del seu grau de discapacitat, 8: consulta per data no disponible, cal realitzar consulta a data actual, 9: consulta per expedient no disponible i 0502: error realitzant la consulta. |
| respostaConsultaDadesDiscapacidad/resultat/descripcio | Descripció del resultat. |


## 4 Joc de proves <a name="4"></a>

L'emissor final publica els següent [joc de proves a l'entorn de pre-producció][proves]
 
[proves]: https://administracionelectronica.gob.es/ctt/svd/descargas#.YvOZNXbP2Ul
 
![image](https://user-images.githubusercontent.com/32306731/137281698-9dfc2044-94f7-487f-a7d6-9a4e0707feb3.png) En cas de tindre problemes per accedir als jocs de proves, si us plau, obre un tiquet a través del [formulari][form]
 
[form]:https://www.aoc.cat/portal-suport/peticio-integradors/idservei/integracio/