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
description: Os administradores podem aprender sobre o recurso Cofre anexos no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 127d862d235abc4cd81f62679b97077c7a80bd70
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054386"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Cofre Anexos no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cofre Os anexos no [Microsoft Defender para Office 365](defender-for-office-365.md) fornece uma camada adicional de proteção para anexos de email que já foram verificados pela proteção anti-malware no Proteção do Exchange Online [(EOP)](anti-malware-protection.md). Especificamente, Cofre attachments usa um ambiente virtual para verificar anexos em mensagens de email antes que eles são entregues aos destinatários (um processo conhecido como _detonação_).

Cofre A proteção de anexos para mensagens de email é controlada por Cofre políticas de anexos. Não há nenhuma política de Cofre De anexos padrão, portanto, para obter a proteção de **anexos Cofre,** você precisa criar uma ou mais políticas de Cofre Anexos. Para obter instruções, [consulte Set up Cofre Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).

A tabela a seguir descreve cenários para Cofre Anexos no Microsoft 365 e Office 365 que incluem o Microsoft Defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

<br>

****

|Cenário|Resultado|
|---|---|
|A organização Microsoft 365 E5 pat não tem nenhuma Cofre De anexos configuradas.|Pat não é protegido por Cofre Anexos. <p> Um administrador deve criar pelo menos uma Cofre de anexos para que Cofre proteção de anexos seja ativa. Além disso, as condições da política devem incluir Pat se Pat deve ser protegido por Cofre Anexos.|
|A organização de Lee tem uma Cofre de anexos que se aplica apenas aos funcionários de finanças. Lee é membro do departamento de vendas.|Lee não está protegido por Cofre Anexos. <p> Os funcionários financeiros são protegidos por Cofre anexos, mas os funcionários de vendas (e outros funcionários) não são.|
|Ontem, um administrador na organização de João criou uma política Cofre Anexos que se aplica a todos os funcionários. No início de hoje, João recebeu uma mensagem de email que incluía um anexo.|O Jean é protegido por Cofre Anexos. <p> Normalmente, leva cerca de 30 minutos para que uma nova política entre em vigor.|
|A organização de Chris tem políticas de anexos de Cofre de longa data para todos na organização. Chris recebe um email que tem um anexo e encaminha a mensagem para destinatários externos.|Chis é protegido por Cofre Anexos. <p> Se os destinatários externos também Cofre políticas de Anexos em sua organização, as mensagens encaminhadas estão sujeitas a essas políticas.|
|

Cofre A verificação de anexos ocorre na mesma região onde seus Microsoft 365 de dados residem. Para obter mais informações sobre a geografia do datacenter, consulte [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Os recursos a seguir estão localizados nas configurações globais das políticas Cofre Anexos no portal Microsoft 365 Defender. No entanto, essas configurações estão habilitadas ou desabilitadas globalmente e não exigem políticas Cofre Anexos:
>
> - [Cofre anexos para SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Documentos Seguros no Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Cofre Configurações de política de anexos

Esta seção descreve as configurações nas políticas Cofre Anexos:

- Cofre resposta de malware desconhecido **anexos**: essa configuração controla a ação para Cofre verificação de malware attachments em mensagens de email. As opções disponíveis são descritas na tabela a seguir:

  <br>

  ****

  |Opção|Efeito|Use quando quiser:|
  |---|---|---|
  |**Desabilitado**|Os anexos não são verificados por malware por Cofre Anexos. As mensagens ainda são verificados por malware pela [proteção anti-malware no EOP](anti-malware-protection.md).|Desativar a verificação para destinatários selecionados. <p> Impedir atrasos desnecessários no roteamento de emails internos. <p> **Essa opção não é recomendada para a maioria dos usuários. Você só deve usar essa opção para desativar Cofre verificação de anexos para destinatários que recebem apenas mensagens de destinatários confiáveis.**|
  |**Monitorar**|Entrega mensagens com anexos e rastreia o que acontece com malware detectado. <p> A entrega de mensagens seguras pode ser adiada devido Cofre verificação de Anexos.|Veja onde o malware detectado vai para sua organização.|
  |**Bloquear**|Impede que mensagens com anexos de malware detectados seja entregue. <p> As mensagens são [colocadas em quarentena,](manage-quarantined-messages-and-files.md) onde apenas os administradores (não usuários) podem revisar, liberar ou excluir as mensagens. <p> Bloqueia automaticamente instâncias futuras das mensagens e anexos. <p> A entrega de mensagens seguras pode ser adiada devido Cofre verificação de Anexos.|Protege sua organização contra ataques repetidos usando os mesmos anexos de malware. <p> Esse é o valor padrão e o valor recomendado em Políticas de segurança predefinidas padrão [e estritas.](preset-security-policies.md)|
  |**Replace**|Remove anexos de malware detectados. <p> Notifica os destinatários de que os anexos foram removidos. <p>  As mensagens são [colocadas em quarentena,](manage-quarantined-messages-and-files.md) onde apenas os administradores (não usuários) podem revisar, liberar ou excluir as mensagens. <p> A entrega de mensagens seguras pode ser adiada devido Cofre verificação de Anexos.|Aumente a visibilidade aos destinatários de que os anexos foram removidos devido a malware detectado.|
  |**Entrega Dinâmica**|Entrega mensagens imediatamente, mas substitui anexos por espaço reservados até que Cofre verificação de anexos seja concluída. <p> Para obter detalhes, consulte a [seção Entrega Dinâmica Cofre Políticas de Anexos](#dynamic-delivery-in-safe-attachments-policies) posteriormente neste artigo.|Evite atrasos de mensagens ao proteger destinatários de arquivos mal-intencionados. <p> Permitir que os destinatários visualizem anexos no modo seguro enquanto a verificação está ocorrendo.|
  |

- Anexo de redirecionamento na **detecção:** Habilitar o redirecionamento e  enviar o anexo para o seguinte endereço de **email**: para ações **bloquear,** **monitorar** ou substituir, envie mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação.

  A recomendação para configurações de política padrão e estrita é habilitar o redirecionamento. Para obter mais informações, [consulte Cofre Configurações de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Aplicar a seleção acima se a verificação de malware para **anexos** for concluída ou ocorrer um erro : a ação especificada pelo **Cofre Anexos** resposta de malware desconhecido é tomada em mensagens mesmo quando Cofre verificação de anexos não pode ser concluída. Sempre selecione essa opção se você selecionar **Habilitar redirecionamento**. Caso contrário, as mensagens podem ser perdidas.

- **Filtros de** destinatário : Você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:
  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade**: se você criar várias políticas, poderá especificar a ordem em que elas são aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega Dinâmica em Cofre De anexos

> [!NOTE]
> A Entrega Dinâmica funciona apenas para Exchange Online caixas de correio.

A ação entrega dinâmica em Cofre de anexos procura eliminar quaisquer atrasos de entrega de email que possam ser causados pela verificação Cofre Anexos. O corpo da mensagem de email é entregue ao destinatário com um espaço reservado para cada anexo. O espaço reservado permanece até que o anexo seja considerado seguro e, em seguida, o anexo fica disponível para abrir ou baixar.

Se um anexo for considerado mal-intencionado, a mensagem será colocada em quarentena. Somente os administradores (não usuários) podem revisar, liberar ou excluir mensagens que foram colocadas em quarentena Cofre verificação de anexos. Para obter mais informações, consulte [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

A maioria dos PDFs e Office documentos podem ser visualizados no modo seguro enquanto Cofre verificação de anexos está em andamento. Se um anexo não for compatível com o visualizador de Entrega Dinâmica, os destinatários verão um espaço reservado para o anexo até que Cofre verificação de anexos seja concluída.

Se você estiver usando um dispositivo móvel e PDFs não estiver renderizar no visualizador de Entrega Dinâmica em seu dispositivo móvel, tente abrir a mensagem no Outlook na Web (anteriormente conhecido como Outlook Web App) usando seu navegador móvel.

Aqui estão algumas considerações sobre Entrega Dinâmica e mensagens encaminhadas:

- Se o destinatário encaminhado estiver protegido por uma política de anexos Cofre que usa a opção Entrega Dinâmica, o destinatário verá o espaço reservado, com a capacidade de visualizar arquivos compatíveis.
- Se o destinatário encaminhado não estiver protegido por uma política de anexos Cofre, a mensagem e os anexos serão entregues sem qualquer Cofre de verificação de anexos ou verificação de anexos.

Há cenários em que a Entrega Dinâmica não pode substituir anexos em mensagens. Esses cenários incluem:

- Mensagens em pastas públicas.
- Mensagens que são roteadas para fora e, em seguida, de volta para a caixa de correio de um usuário usando regras personalizadas.
- Mensagens movidas (automaticamente ou manualmente) de caixas de correio de nuvem para outros locais, incluindo pastas de arquivo morto.
- As regras de caixa de entrada movem a mensagem da Caixa de Entrada para uma pasta diferente.
- Mensagens excluídas.
- A pasta de pesquisa de caixa de correio do usuário está em estado de erro.
- Exchange Online organizações onde o Exclamador está habilitado. Para resolver esse problema, consulte [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) mensagens criptografadas.
- Você configurou a ação Entrega Dinâmica em uma política de Cofre Anexos, mas o destinatário não dá suporte à Entrega Dinâmica (por exemplo, o destinatário é uma caixa de correio em uma organização Exchange local). No entanto, Cofre links no [Microsoft Defender para Office 365](set-up-safe-links-policies.md) é capaz de verificar anexos de arquivo Office que contêm URLs (dependendo de como as configurações globais para links Cofre [estão](configure-global-settings-for-safe-links.md) configuradas).

## <a name="submitting-files-for-malware-analysis"></a>Enviando arquivos para análise de malware

- Se você receber um arquivo que deseja enviar à Microsoft para análise, consulte Enviar malware e não malware à [Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
- Se você receber uma mensagem de email (com ou sem um anexo) que deseja enviar à Microsoft para análise, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).
