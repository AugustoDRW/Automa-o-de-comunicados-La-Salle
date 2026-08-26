O fluxo passou por algumas alterações no decorrer dos meses de trabalho, atualmente ele funciona da seguinte forma:
verificação de caixa de entrada de email, a cada 1 minuto:
email novo encaminhado para um bloco condicional que dita se é uma resposta ou não, se for uma resposta ele somente marca o email como lido, sem fazer qualquer processamento adicional, polpando tokens e tempo de processamento
impedindo também ocasionar bugs como recriar um comunicado diversas vezes.
após essa condição o email é encaminhado para outro bloco condicional, desta vez um bloco de switch case, que procura as palavras chaves informadas pelo cliente, no caso desta versão atual, somente o bloco de comunicados está
implementado e funcionando, e o bloco de solicitações de compras ainda está sendo implementado.
O switch case busca as palavras chaves "bilhete, bilhetes, comunicado, comunicados, card e cards", palavras chaves utilizadas nas solicitações, e então direciona para um bloco de agente de IA movido por uma LLM de modelo
mistral-medium, que gera um comunicado em um formato passado pelo System Message, e então atualiza um documento compartilhado entre os responsáveis por enviar os comunicados já com o bilhete criado.
E por fim, marca a mensagem original como lida, e envia uma mensagem para os responsáveis comunicando o novo card para ser enviado. 
