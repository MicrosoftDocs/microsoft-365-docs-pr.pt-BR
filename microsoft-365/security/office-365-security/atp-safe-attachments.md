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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre o recurso de anexos seguros no Microsoft defender para Office 365.
ms.openlocfilehash: 07e44885a3813ce625c6a853f4070d644a392ded
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659187"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Anexos seguros no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Anexos seguros no [Microsoft defender para Office 365](office-365-atp.md) fornece uma camada adicional de proteção para anexos de email que já foram verificados pela [proteção Antimalware no Exchange Online Protection (EOP)](anti-malware-protection.md). Especificamente, os anexos seguros usam um ambiente virtual para verificar anexos em mensagens de email antes de serem entregues aos destinatários (um processo conhecido como _acionamento_).

A proteção de anexos seguros para mensagens de email é controlada por políticas de anexos seguros. Não há nenhuma política de anexos seguros padrão, **portanto, para obter a proteção de anexos seguros, você precisa criar uma ou mais políticas de anexos seguros**. Para obter instruções, confira [Configurar políticas de anexos seguros no defender para Office 365](set-up-atp-safe-attachments-policies.md).

A tabela a seguir descreve os cenários de anexos seguros no Microsoft 365 e no Office 365 organizações que incluem o Microsoft defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

****

|Cenário|Resultado|
|---|---|
|A organização do Microsoft 365 E5 não tem políticas de anexos seguros configuradas.|Pat não está protegido por anexos seguros. <p> Um administrador deve criar pelo menos uma política de anexos seguros para que a proteção de anexos seguros seja ativada. Além disso, as condições da política devem incluir Pat se Pat estiver protegido por anexos seguros.|
|A organização de Lee tem uma política de anexos seguros que se aplica apenas a funcionários financeiros. Lee é membro do departamento de vendas.|Lee não é protegido por anexos seguros. <p> Os funcionários de Finanças são protegidos por anexos seguros, mas os funcionários de vendas (e outros funcionários) não.|
|Ontem, um administrador na organização de Jean criou uma política de anexos seguros que se aplica a todos os funcionários. Hoje em dia, Jean recebeu uma mensagem de email que incluía um anexo.|Jean é protegido por anexos seguros. <p> Normalmente, leva cerca de 30 minutos para que uma nova política entre em vigor.|
|A organização de Carla tem políticas de anexos seguros de longa duração para todas as pessoas na organização. Carla recebe um email com um anexo e encaminha a mensagem para destinatários externos.|O Chis é protegido por anexos seguros. <p> Se os destinatários externos também têm políticas de anexos seguros em sua organização, as mensagens encaminhadas estão sujeitas a essas políticas.|
|

A verificação de anexos seguros ocorre na mesma região onde seus dados do Microsoft 365 residem. Para obter mais informações sobre a geografia do datacenter, confira [onde estão seus dados?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Os seguintes recursos estão localizados nas configurações globais são de políticas de anexos seguros no centro de conformidade & segurança, mas essas configurações são habilitadas ou desabilitadas globalmente e não exigem políticas de anexos seguros:
>
> - [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).
>
> - [Documentos Seguros no Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Configurações de política de anexos seguros

Esta seção descreve as configurações em políticas de anexos confiáveis:

- **Anexos seguros resposta desconhecida de malware**: essa configuração controla a ação para verificação de malware de anexos seguros em mensagens de email. As opções disponíveis são descritas na tabela a seguir:

  ****

  |Opção|Efeito|Use quando quiser:|
  |---|---|---|
  |**Desabilitado**|Os anexos não são verificados em busca de malware por anexos seguros. As mensagens ainda são verificadas em busca de malware por [proteção Antimalware no EOP](anti-malware-protection.md).|Desligar a verificação para destinatários selecionados. <p> Evitar atrasos desnecessários no roteamento de email interno. <p> **Essa opção não é recomendada para a maioria dos usuários. Você só deve usar essa opção para desativar a verificação de anexos seguros para destinatários que recebem apenas mensagens de remetentes confiáveis.**|
  |**Monitorar**|Entrega mensagens com anexos e rastreia o que acontece com o malware detectado. <p> A entrega de mensagens seguras pode ser atrasada devido à verificação de anexos seguros.|Veja onde o malware detectado entra em sua organização.|
  |**Bloquear**|Impede que mensagens com anexos de malware detectados sejam entregues. <p> As mensagens são [colocadas em quarentena](manage-quarantined-messages-and-files.md) onde somente os administradores (não os usuários finais) podem revisar, liberar ou excluir as mensagens. <p> Bloqueia automaticamente instâncias futuras das mensagens e dos anexos. <p> A entrega de mensagens seguras pode ser atrasada devido à verificação de anexos seguros.|Protege sua organização contra ataques repetidos usando os mesmos anexos de malware. <p> Esse é o valor padrão e o valor recomendado em políticas de segurança padrão e estritas [predefinidas](preset-security-policies.md).|
  |**Replace**|Remove anexos detectados de malware. <p> Notifica os destinatários de que os anexos foram removidos. <p>  As mensagens são [colocadas em quarentena](manage-quarantined-messages-and-files.md) onde somente os administradores (não os usuários finais) podem revisar, liberar ou excluir as mensagens. <p> A entrega de mensagens seguras pode ser atrasada devido à verificação de anexos seguros.|Aumente a visibilidade dos destinatários que os anexos foram removidos devido à detecção de malware.|
  |**Entrega dinâmica**|Entrega mensagens imediatamente, mas substitui anexos por espaços reservados até que a verificação de anexos seguros seja concluída. <p> Para obter detalhes, consulte a seção [entrega dinâmica em políticas de anexos seguros](#dynamic-delivery-in-safe-attachments-policies) , mais adiante neste artigo.|Evitar atrasos de mensagem ao proteger destinatários de arquivos mal-intencionados. <p> Permite que os destinatários visualizem anexos no modo de segurança enquanto a verificação está ocorrendo.|
  |

- **Redirecionar o anexo na detecção: habilitar o redirecionamento** e **enviar o anexo para o seguinte endereço de email**: para **Bloquear**, **monitorar** ou **substituir** ações, envie mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação.

  A recomendação para as configurações de política padrão e estrita é habilitar o redirecionamento. Para obter mais informações, consulte [configurações de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- **Aplicar a seleção acima se a verificação de malware para anexos expirar ou ocorrer erro**: a ação especificada por **anexos seguros a resposta desconhecida** é tomada em mensagens, mesmo quando a verificação de anexos seguros não pode ser concluída. Sempre Selecione esta opção se você selecionar **habilitar redirecionamento**. Caso contrário, as mensagens poderão ser perdidas.

- **Filtros de destinatário**: você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:

  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou uma exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade**: se você criar várias políticas, poderá especificar a ordem em que elas serão aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Entrega dinâmica em políticas de anexos seguros

> [!NOTE]
> A entrega dinâmica funciona apenas para caixas de correio do Exchange Online.

A ação de entrega dinâmica em políticas de anexos seguros busca eliminar os atrasos de entrega de email que podem ser causados por verificação de anexos seguros. O corpo da mensagem de email é entregue ao destinatário com um espaço reservado para cada anexo. O espaço reservado permanece até que o anexo seja considerado seguro e, em seguida, o anexo fica disponível para ser aberto ou baixado.

Se um anexo for mal-intencionado, a mensagem será colocada em quarentena. Somente administradores (não usuários finais) podem revisar, liberar ou excluir mensagens que foram colocadas em quarentena por anexos seguros. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador](manage-quarantined-messages-and-files.md).

A maioria dos documentos PDFs e do Office pode ser visualizada no modo de segurança enquanto a verificação de anexos seguros está em andamento. Se um anexo não for compatível com o modo de exibição de entrega dinâmica, os destinatários verão um espaço reservado para o anexo até que a verificação de anexos seguros seja concluída.

Se você estiver usando um dispositivo móvel e os PDFs não são renderizados no modo de entrega dinâmico do seu dispositivo móvel, tente abrir a mensagem no Outlook na Web (anteriormente conhecido como Outlook Web App) usando seu navegador móvel.

Aqui estão algumas considerações para entrega dinâmica e mensagens encaminhadas:

- Se o destinatário encaminhado estiver protegido por uma política de anexos seguros que usa a opção de entrega dinâmica, o destinatário verá o espaço reservado, com a capacidade de visualizar arquivos compatíveis.

- Se o destinatário encaminhado não estiver protegido por uma política de anexos seguros, a mensagem e os anexos serão entregues sem nenhum marcador de verificação de anexos seguros ou de anexo.

Há situações em que a entrega dinâmica não é capaz de substituir anexos em mensagens. Esses cenários incluem:

- Mensagens em pastas públicas.

- Mensagens que são encaminhadas de e, em seguida, de volta para a caixa de correio de um usuário usando regras personalizadas.

- Mensagens que são movidas (automática ou manualmente) de caixas de correio na nuvem para outros locais, incluindo pastas de arquivos mortos.

- Mensagens excluídas.

- A pasta de pesquisa da caixa de correio do usuário está em um estado de erro.

- Organizações do Exchange Online onde o exclaimr está habilitado. Para resolver isso, confira [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) mensagens criptografadas.

- Você configurou a ação de entrega dinâmica em uma política de anexos seguros, mas o destinatário não dá suporte à entrega dinâmica (por exemplo, o destinatário é uma caixa de correio em uma organização local do Exchange). No entanto, os [links seguros no Microsoft defender para Office 365](set-up-atp-safe-links-policies.md) podem verificar anexos de arquivo do Office que contêm URLs (dependendo de como as [configurações globais de links seguros](configure-global-settings-for-safe-links.md) são configuradas).

## <a name="submitting-files-for-malware-analysis"></a>Enviando arquivos para análise de malware

- Se você receber um arquivo que deseja enviar para a Microsoft para análise, confira [Enviar malware e não malware para a Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Se você receber uma mensagem de email (com ou sem um anexo) que deseja enviar para a Microsoft para análise, confira [mensagens de relatório e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).
