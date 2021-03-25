---
title: Anexos seguros
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Os administradores podem aprender sobre o recurso Anexos Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2f097cddce4afe2b3242ae34bbcfa242c3af601
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203332"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Anexos seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os Anexos Seguros no [Microsoft Defender para Office 365](defender-for-office-365.md) fornece uma camada adicional de proteção para anexos de email que já foram verificados pela proteção anti-malware no Exchange Online Protection [(EOP)](anti-malware-protection.md). Especificamente, Anexos Seguros usa um ambiente virtual para verificar anexos em mensagens de email antes que eles são entregues aos destinatários (um processo conhecido como _detonação_).

A proteção de Anexos Seguros para mensagens de email é controlada por políticas de Anexos Seguros. Não há nenhuma política padrão de Anexos Seguros, portanto, para obter a proteção de Anexos Seguros, você precisa criar uma ou mais políticas de **Anexos Seguros.** Para obter instruções, [consulte Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).

A tabela a seguir descreve cenários para Anexos Seguros nas organizações do Microsoft 365 e do Office 365 que incluem o Microsoft Defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

****

|Cenário|Resultado|
|---|---|
|A organização do Microsoft 365 E5 do Pat não tem políticas de Anexos Seguros configuradas.|Pat não está protegido por Anexos Seguros. <p> Um administrador deve criar pelo menos uma política de Anexos Seguros para que a proteção de Anexos Seguros seja ativa. Além disso, as condições da política devem incluir Pat se Pat deve ser protegido por Anexos Seguros.|
|A organização de Lee tem uma política de Anexos Seguros que se aplica apenas aos funcionários de finanças. Lee é membro do departamento de vendas.|Lee não está protegido por Anexos Seguros. <p> Os funcionários financeiros são protegidos por Anexos Seguros, mas os funcionários de vendas (e outros funcionários) não são.|
|Ontem, um administrador na organização de João criou uma política de Anexos Seguros que se aplica a todos os funcionários. No início de hoje, João recebeu uma mensagem de email que incluía um anexo.|O Jean é protegido por Anexos Seguros. <p> Normalmente, leva cerca de 30 minutos para que uma nova política entre em vigor.|
|A organização de Chris tem políticas de Anexos Seguros de longa data para todos na organização. Chris recebe um email que tem um anexo e encaminha a mensagem para destinatários externos.|Chis é protegido por Anexos Seguros. <p> Se os destinatários externos também têm políticas de Anexos Seguros em sua organização, as mensagens encaminhadas estão sujeitas a essas políticas.|
|

A verificação de Anexos Seguros ocorre na mesma região onde os dados do Microsoft 365 residem. Para obter mais informações sobre a geografia do datacenter, consulte [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Os recursos a seguir estão localizados nas configurações globais das políticas de Anexos Seguros no Centro de Conformidade & Segurança. No entanto, essas configurações estão habilitadas ou desabilitadas globalmente e não exigem políticas de Anexos Seguros:
>
> - [Anexos seguros para SharePoint, OneDrive e Microsoft Teams.](mdo-for-spo-odb-and-teams.md)
>
> - [Documentos Seguros no Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Configurações de política de Anexos Seguros

Esta seção descreve as configurações em políticas de Anexos Seguros:

- **Resposta de malware desconhecido anexos seguros**: essa configuração controla a ação de verificação de malware anexos seguros em mensagens de email. As opções disponíveis são descritas na tabela a seguir:

  ****

  |Opção|Efeito|Use quando quiser:|
  |---|---|---|
  |**Off**|Os anexos não são verificados por malware por Anexos Seguros. As mensagens ainda são verificados por malware pela [proteção anti-malware no EOP](anti-malware-protection.md).|Desativar a verificação para destinatários selecionados. <p> Impedir atrasos desnecessários no roteamento de emails internos. <p> **Essa opção não é recomendada para a maioria dos usuários. Você só deve usar essa opção para desativar a verificação de Anexos Seguros para destinatários que recebem apenas mensagens de destinatários confiáveis.**|
  |**Monitor**|Entrega mensagens com anexos e rastreia o que acontece com malware detectado. <p> A entrega de mensagens seguras pode ser adiada devido à verificação de Anexos Seguros.|Veja onde o malware detectado vai para sua organização.|
  |**Bloquear**|Impede que mensagens com anexos de malware detectados seja entregue. <p> As mensagens são [colocadas em quarentena,](manage-quarantined-messages-and-files.md) onde apenas os administradores (não usuários finais) podem revisar, liberar ou excluir as mensagens. <p> Bloqueia automaticamente instâncias futuras das mensagens e anexos. <p> A entrega de mensagens seguras pode ser adiada devido à verificação de Anexos Seguros.|Protege sua organização contra ataques repetidos usando os mesmos anexos de malware. <p> Esse é o valor padrão e o valor recomendado em Políticas de segurança predefinidas padrão [e estritas.](preset-security-policies.md)|
  |**Substituir**|Remove anexos de malware detectados. <p> Notifica os destinatários de que os anexos foram removidos. <p>  As mensagens são [colocadas em quarentena,](manage-quarantined-messages-and-files.md) onde apenas os administradores (não usuários finais) podem revisar, liberar ou excluir as mensagens. <p> A entrega de mensagens seguras pode ser adiada devido à verificação de Anexos Seguros.|Aumente a visibilidade aos destinatários de que os anexos foram removidos devido a malware detectado.|
  |**Entrega Dinâmica**|Entrega mensagens imediatamente, mas substitui anexos por espaço reservados até que a verificação de Anexos Seguros seja concluída. <p> Para obter detalhes, consulte a seção Entrega Dinâmica em Políticas [de Anexos](#dynamic-delivery-in-safe-attachments-policies) Seguros mais adiante neste artigo.|Evite atrasos de mensagens ao proteger destinatários de arquivos mal-intencionados. <p> Permitir que os destinatários visualizem anexos no modo seguro enquanto a verificação está ocorrendo.|
  |

- Anexo de redirecionamento na **detecção:** Habilitar o redirecionamento e  enviar o anexo para o seguinte endereço de **email**: para ações **bloquear,** **monitorar** ou substituir, envie mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação.

  A recomendação para configurações de política padrão e estrita é habilitar o redirecionamento. Para obter mais informações, consulte [Configurações de Anexos Seguros.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Aplique a seleção acima se a verificação de malware para **anexos** for concluída ou ocorrer um erro : a ação especificada por **Anexos** Seguros resposta de malware desconhecida é tomada em mensagens mesmo quando a verificação de Anexos Seguros não pode ser concluída. Sempre selecione essa opção se você selecionar **Habilitar redirecionamento**. Caso contrário, as mensagens podem ser perdidas.

- **Filtros de** destinatário : Você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:

  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade**: se você criar várias políticas, poderá especificar a ordem em que elas são aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega Dinâmica em políticas de Anexos Seguros

> [!NOTE]
> A Entrega Dinâmica funciona apenas para caixas de correio do Exchange Online.

A ação entrega dinâmica em políticas de Anexos Seguros procura eliminar quaisquer atrasos de entrega de email que possam ser causados pela verificação de Anexos Seguros. O corpo da mensagem de email é entregue ao destinatário com um espaço reservado para cada anexo. O espaço reservado permanece até que o anexo seja considerado seguro e, em seguida, o anexo fica disponível para abrir ou baixar.

Se um anexo for considerado mal-intencionado, a mensagem será colocada em quarentena. Somente os administradores (não usuários finais) podem revisar, liberar ou excluir mensagens que foram colocadas em quarentena pela verificação de Anexos Seguros. Para obter mais informações, consulte [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

A maioria dos PDFs e documentos do Office pode ser visualizada no modo seguro enquanto a verificação de Anexos Seguros está em andamento. Se um anexo não for compatível com o visualizador de Entrega Dinâmica, os destinatários verão um espaço reservado para o anexo até que a verificação de Anexos Seguros seja concluída.

Se você estiver usando um dispositivo móvel e PDFs não estiver renderizar no visualizador de Entrega Dinâmica em seu dispositivo móvel, tente abrir a mensagem no Outlook na Web (anteriormente conhecido como Outlook Web App) usando seu navegador móvel.

Aqui estão algumas considerações sobre Entrega Dinâmica e mensagens encaminhadas:

- Se o destinatário encaminhado estiver protegido por uma política de Anexos Seguros que usa a opção Entrega Dinâmica, o destinatário verá o espaço reservado, com a capacidade de visualizar arquivos compatíveis.

- Se o destinatário encaminhado não estiver protegido por uma política de Anexos Seguros, a mensagem e os anexos serão entregues sem qualquer verificação de anexos seguros ou espaço reservados para anexos.

Há cenários em que a Entrega Dinâmica não pode substituir anexos em mensagens. Esses cenários incluem:

- Mensagens em pastas públicas.

- Mensagens que são roteadas para fora e, em seguida, de volta para a caixa de correio de um usuário usando regras personalizadas.

- Mensagens movidas (automaticamente ou manualmente) de caixas de correio de nuvem para outros locais, incluindo pastas de arquivo morto.

- Mensagens excluídas.

- A pasta de pesquisa de caixa de correio do usuário está em estado de erro.

- Organizações do Exchange Online em que o Exclamador está habilitado. Para resolver isso, consulte [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) mensagens criptografadas.

- Você configurou a ação Entrega Dinâmica em uma política de Anexos Seguros, mas o destinatário não dá suporte à Entrega Dinâmica (por exemplo, o destinatário é uma caixa de correio em uma organização local do Exchange). No entanto, os Links Seguros no [Microsoft Defender para Office 365](set-up-safe-links-policies.md) podem examinar anexos de arquivo do Office que contêm URLs (dependendo de como as configurações [globais](configure-global-settings-for-safe-links.md) para Links Seguros estão configuradas).

## <a name="submitting-files-for-malware-analysis"></a>Enviando arquivos para análise de malware

- Se você receber um arquivo que deseja enviar à Microsoft para análise, consulte Enviar malware e não malware à [Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Se você receber uma mensagem de email (com ou sem um anexo) que deseja enviar à Microsoft para análise, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).
