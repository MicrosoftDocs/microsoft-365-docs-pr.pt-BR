---
title: Configurar a política de spam de saída
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados.
ms.openlocfilehash: 9c8c2f7e9ff0be02f11fa66409690cbb854d8c56
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072842"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurar a política de spam de saída

A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados. Semelhante a filtragem de entrada, a filtragem de spam de saída é composta de filtragem de conexão e de conteúdo, porém, as configurações do filtro de saída não são configuráveis. Se uma mensagem de saída é considerada spam, ela é roteada através do pool de entrega de risco mais alto, que reduz a probabilidade do pool de IP de saída normal estar sendo adicionado a uma lista de bloqueio. Se um cliente continua a enviar spam de saída através do serviço, será impedido de enviar mensagens. Embora a filtragem de spam de saída não possa ser desabilitada nem modificada, você pode configurar várias configurações de spam de saída para toda a empresa por meio da política padrão de spam de saída. 
  
O vídeo a seguir mostra como configurar a política de spam de saída:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
> [!NOTE]
> Para obter os melhores resultados de filtragem, o conteúdo do vídeo acima deve ser usado com uma configuração adequada e familiaridade com os [controles de spam de saída no Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?
<a name="sectionSection0"> </a>

Tempo estimado para conclusão: 5 minutos
  
Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o tópico "entrada antispam no tópico [permissões de recurso no Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
O procedimento a seguir também pode ser realizado pelo PowerShell remoto. Use o cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) para analisar suas configurações e o cmdlet [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) para editar as configurações de política de spam de saída. Para saber como usar o Windows PowerShell para se conectar à proteção do Exchange Online, confira [conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290). Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>Utilize o EAC para editar a política de spam de saída padrão
<a name="sectionSection1"> </a>

Utilize o procedimento a seguir para editar a política de spam de saída padrão.
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>Para configurar a política de spam de saída padrão.

1. No centro de administração do Exchange (Eat), navegue até **proteger** \> **spam de saída**e, em seguida, clique duas vezes na política padrão.
    
2. Selecione a opção de menu **Preferências de saída de spam** . 
    
3. Marque as seguintes caixas de seleção referentes às mensagens de saída e, em seguida, especifique um endereço de email associado ou endereços na caixa de entrada associada (elas podem ser listas de distribuição se forem resolvidas como destinos SMTP válidos):
    
1. Envie uma cópia de todas as mensagens suspeitas de email de saída para **o(s) seguinte(s) endereço(s) de email**. Estas são as mensagens que são marcadas como spam pelo filtro (independentemente da classificação de SCL) Elas não são rejeitadas pelo filtro, mas são roteadas pelo pool de entrega de risco mais alto. Separe com ponto e vírgula os diversos endereços. Observe que os destinatários especificados receberão as mensagens como um endereço com cópia oculta (Bcc) (os campos De e Para são o remetente e o destinatário originais).
    
2. Envie uma notificação para o seguinte endereço de email quando um remetente for bloqueado por enviar **spam de saída**. Separe com ponto e vírgula os diversos endereços.
    
    Quando uma quantidade significativa de spam está sendo originada a partir de um usuário específico, este usuário é desabilitado para envio de mensagens de email. O administrador para o domínio, especificado usando esta configuração, será informado de que as mensagens de saída estão bloqueadas para este usuário. Para ver a aparência dessa notificação, confira [exemplo de notificação quando um remetente estiver bloqueado enviando spam de saída](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Para obter informações sobre como habilitar novamente, consulte [removendo um usuário, domínio ou endereço IP de uma lista de bloqueios após o envio de email de spam](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).
    
4. Clique em **salvar**. Um resumo das suas configurações de política padrão aparece no painel à direita.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="sectionSection2"> </a>

[Pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md)
  
[Perguntas frequentes sobre proteção antispam](anti-spam-protection-faq.md)
  

