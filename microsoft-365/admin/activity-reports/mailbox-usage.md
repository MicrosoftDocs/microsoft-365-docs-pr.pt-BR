---
title: Relatórios do Microsoft 365 no centro de administração - Uso da caixa de correio
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Saiba como obter o relatório de uso da Caixa de Correio para saber sobre as atividades dos usuários com uma caixa de correio de usuário.
ms.openlocfilehash: 13a2d2382799052423300f72e8af0df1ca596bb6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904559"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Relatórios do Microsoft 365 no centro de administração - Uso da caixa de correio

O  relatório de uso da Caixa de Correio fornece informações sobre os usuários com uma caixa de correio de usuário e o nível de atividade de cada um com base no email enviar, ler, criar compromisso, enviar reunião, aceitar reunião, recusar reunião e cancelar a atividade de reunião. Ele fornece também informações sobre o consumo do espaço de armazenamento de cada caixa de correio do usuário e quantas delas estão prestes a atingir as cotas de armazenamento. 
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Como obter o relatório de uso da caixa de correio

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.
2. Selecione **Exibir Mais em** Atividade de **Email.** 
3. Na lista listada de atividades de **email,** selecione Uso de **Caixa** de Correio do Exchange \> .

## <a name="interpret-the-mailbox-usage-report"></a>Interpretar o relatório de uso da caixa de correio

Para ter uma noção do **uso da caixa de correio** da organização, analise os gráficos **Caixa de correio**, **Armazenamento** e **Cota**. 
  
![Relatório de uso da caixa de correio](../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png)

|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Uso da caixa de correio** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O gráfico "Caixa de correio" mostra o número total de caixas de correio do usuário na organização e o total das que estão ativas em um determinado dia do período de relatório. Uma caixa de correio de usuário é considerada ativa se tiver um email enviar, ler, criar compromisso, enviar reunião, aceitar reunião, recusar reunião e cancelar atividades de reunião.  <br/> |
|4.  <br/> |O gráfico **Armazenamento** mostra a quantidade de armazenamento em uso na organização. O Gráfico de Armazenamento não inclui caixas de correio de arquivo morto. Para obter mais informações sobre arquivamento de expansão automática, consulte [Overview of unlimited archiving in Microsoft 365](../../compliance/unlimited-archiving.md).<br/> |
|5.  <br/> | O gráfico **Cota** mostra o número de caixas de correio do usuário em cada categoria de cota. Há quatro categorias de cota:  <br/>  Bom - Quantidade de usuários cujo armazenamento usado é inferior à cota de aviso de problema.  <br/>  Aviso - Quantidade de usuários cujo armazenamento usado é igual ou superior à cota de aviso de problema, mas é inferior à cota de proibição de envio.  <br/>  Não é possível enviar - Quantidade de usuários cujo armazenamento usado é igual ou superior à cota de proibição de envio, mas é inferior à cota de proibição de envio/recebimento.  <br/>  Não é possível enviar/receber - Quantidade de usuários cujo armazenamento usado é igual ou superior à cota de proibição de envio/recebimento.  <br/> |
|6.  <br/> | No gráfico **Caixa de correio**, o eixo Y é o número de caixas de correio do usuário.  <br/>  No gráfico **Armazenamento**, o eixo Y é a quantidade de armazenamento em uso pelas caixas de correio do usuário da organização.  <br/>  No gráfico **Cota**, o eixo Y é o número de caixas de correio do usuário para cada cota de armazenamento.  <br/>  Nos gráficos "Caixa de correio" e "Armazenamento", o eixo X é o intervalo de datas escolhido para esse relatório específico.  <br/>  O eixo X no gráfico Cota é a categoria da cota.  <br/> |
|7.  <br/> |Você pode filtrar gráficos que você vê selecionando um item na legenda.  <br/> |
|8.  <br/> | A tabela mostra o detalhamento de uso da caixa de correio no nível do usuário. Você pode adicionar mais colunas à tabela.  <br/> **Nome de usuário** é o endereço de email do usuário.  <br/> **Nome para Exibição** é o nome completo do usuário.  <br/> **Excluída** se refere à caixa de correio cujo estado atual é excluída, mas esteve ativa durante parte do período do relatório.  <br/> **Data da exclusão** é a data de exclusão da caixa de correio.  <br/> **Data de criação** é a data de criação da caixa de correio.  <br/> **Data da última atividade** se refere à data em que houve um envio de email ou atividade de leitura na caixa de correio.  <br/> **Contagem de itens** se refere ao total de itens na caixa de correio.  <br/> **Armazenamento usado (MB)** se refere ao total de armazenamento usado.  <br/> **Contagem de Itens Excluídos** refere-se ao número total de itens excluídos na caixa de correio. <br/> **Tamanho do Item Excluído (MB)** refere-se ao tamanho total de todos os itens excluídos na caixa de correio. <br/> **Cota de aviso de problema (MB)** se refere ao limite de armazenamento quando o proprietário da caixa de correio recebe um aviso informando que ele está prestes a atingir a cota de armazenamento.  <br/> **Cota de proibição de envio (MB)** se refere ao limite de armazenamento quando a caixa de correio não pode mais enviar emails.  <br/> **Cota de proibição de envio/recebimento (MB)** se refere ao limite de armazenamento quando a caixa de correio não pode mais enviar ou receber emails.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **Ocultar detalhes do usuário na** seção Relatórios de Atividades no Centro de administração do Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso da caixa de correio - escolha colunas](../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png)|
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo .csv do Excel, selecionando o link **Exportar.**  <br/> |
|||
