    Prezado Gerente, espero que esteja bem.
Analisei os banco de dados do sistema transacional e a tabela analítica da area de negocio. Comparando o ultimo log do banco de dados, com a tabela analitica pelo id_pedido. Recriando a tabela pedidos_destinos teriamos 153 produtos, logo foi encontrado erro em 24% dos pedidos.
Esses são os pedidos que ocorreram divergencia entre o banco de dados e a tabela utilizada pelo comercial:

10001	10003	10020	10028	10031	10045	10061	10064	10069	10072	10077	10080	10091	10098	10099	10100	10106	10109	10115	10116	10117	10118	10119	10135	10140	10141	10144

Muitos desses casos encontra-se com o status e/ou valor da compra divergente. Os valores da tabela estão superiores ou iguais aos valores do banco. Consequentemente, acumularam um valor de R$953,46 a mais na tabela. 
Ex.: 10050	10149	10022	10105	10107	10032	10079	10127	10054	10093

Outros casos nem constam na tabela analitica. Por não constarem, geram uma falta de R$47273,44. 
Ex.: 10028	10061	10069	10072	10077	10080	10091	10099	10100	10106	10109	10115	10116	10117	10118	10135	10144

Há também casos que só ocorrem na tabela analitica, eles apresentam id_pedido repetido, logo não pude por no csv do relatorio. Necessitando um csv a parte. Estava com todo o resto divergente, id_cliente, valores e status. 
Ex.: 10001	10003	10020	10031	10045	10064	10098	10119	10140	10141

Grupo A - Status e/ou valor divergente: 10 pedidos — R$ 953,46 a mais
Grupo B - Pedidos ausentes na tabela analítica: 17 pedidos — R$ 47.273,44 faltando
Grupo C - Novos IDs da tabela analitica, que não consta no log do banco de dados: 10 pedidos — R$ 12.277,97 excedentes.
Diferença líquida: R$ 34.042,01



att Luiz Renato dos Santos Monteiro
