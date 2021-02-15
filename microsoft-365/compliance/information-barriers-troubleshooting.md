---
title: Solução de problemas de barreiras de informações
description: Use este artigo como um guia para solucionar problemas de barreiras de informações.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126558"
---
# <a name="troubleshooting-information-barriers"></a>Solução de problemas de barreiras de informações

[As barreiras de informações](information-barriers.md) podem ajudar sua organização a permanecer em conformidade com os requisitos legais e os regulamentos do setor. Por exemplo, com barreiras de informações, você pode restringir a comunicação entre grupos específicos de usuários para evitar um conflito de interesses ou outros problemas. (Para saber mais sobre como configurar barreiras de informações, consulte [Definir políticas para barreiras de informações.)](information-barriers-policies.md)

Caso as pessoas se deem com problemas inesperados depois que as barreiras de informações estão em vigor, há algumas etapas que você pode seguir para resolver esses problemas. Use este artigo como guia.

> [!IMPORTANT]
> Para executar as tarefas descritas neste artigo, você deve ter uma função apropriada, como uma das seguintes:<br/>– Administrador Global do Microsoft 365 Enterprise<br/>- administrador global<br/>- Administrador de Conformidade<br/>– Gerenciamento de Conformidade do IB (esta é uma nova função!)<p>Para saber mais sobre os pré-requisitos para barreiras de informações, consulte [Pré-requisitos (para](information-barriers-policies.md#prerequisites)políticas de barreira de informações).<p>Certifique-se [de se conectar ao PowerShell do Centro](/powershell/exchange/connect-to-scc-powershell)de Conformidade & segurança.

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: os usuários são impedidos inesperadamente de se comunicar com outras pessoas no Microsoft Teams 

Nesse caso, as pessoas estão relatando problemas inesperados na comunicação com outras pessoas no Microsoft Teams. Alguns exemplos:

- Um usuário procura, mas não consegue encontrar outro usuário no Microsoft Teams.
- Um usuário pode encontrar, mas não pode selecionar, outro usuário no Microsoft Teams.
- Um usuário pode ver outro usuário, mas não pode enviar mensagens para esse outro usuário no Microsoft Teams.

### <a name="what-to-do"></a>O que fazer

Determinar se os usuários são afetados por uma política de barreira de informações. Dependendo de como as políticas são configuradas, as barreiras de informações podem estar funcionando conforme o esperado. Ou talvez seja preciso refinar as políticas da sua organização.

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com o parâmetro Identity. 

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> É possível usar qualquer valor de identidade que identifique cada destinatário com exclusividade, como Nome, Alias, Nome Diferenciado (DN), DN Canônico, Endereço de Email ou GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> Neste exemplo, estamos usando um alias (*meganb*) para o parâmetro Identity. Este cmdlet retornará informações que indicam se o usuário é afetado por uma política de barreira de informações. (Procure *ExoPolicyId: \<GUID> .) |

    **Se os usuários não estão incluídos nas políticas de barreira de informações, contate o suporte.** Caso contrário, prossiga para a próxima etapa.

2. Descubra quais segmentos estão incluídos em uma política de barreira de informações. Para fazer isso, use o `Get-InformationBarrierPolicy` cmdlet com o parâmetro Identity. 

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Use detalhes, como o GUID da política (ExoPolicyId) recebido durante a etapa anterior, como um valor de identidade. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> Neste exemplo, estamos recebendo informações detalhadas sobre a política de barreira de informações que tem ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Depois de executar o cmdlet, nos resultados, procure os valores **AssignedSegment**, **SegmentsAllowed** e **SegmentsBlocked.**

    Por exemplo, depois de executar `Get-InformationBarrierPolicy` o cmdlet, vimos o seguinte em nossa lista de resultados:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    Nesse caso, podemos ver que uma política de barreira de informações afeta as pessoas que estão nos segmentos vendas e pesquisa. Nesse caso, as pessoas em Vendas são impedidas de se comunicar com pessoas na Pesquisa.

    Se isso parecer correto, as barreiras de informações estão funcionando conforme o esperado. Caso contrário, vá para a próxima etapa.

3. Certifique-se de que seus segmentos estão definidos corretamente. Para fazer isso, use o `Get-OrganizationSegment` cmdlet e revise a lista de resultados.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Use este cmdlet com um parâmetro Identity. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> Neste exemplo, estamos recebendo informações sobre o segmento que tem GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd.* |

    Revise os detalhes do segmento. Se necessário, [edite um segmento](information-barriers-edit-segments-policies.md#edit-a-segment)e, em seguida, re-use o `Start-InformationBarrierPoliciesApplication` cmdlet.

    **Se você ainda estiver tendo problemas com sua política de barreira de informações, entre em contato com o suporte.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: as comunicações são permitidas entre usuários que devem ser bloqueados no Microsoft Teams

Nesse caso, embora as barreiras de informações sejam definidas, ativas e aplicadas, as pessoas que devem ser impedidas de se comunicar entre si podem conversar e ligar umas com as outras no Microsoft Teams.

### <a name="what-to-do"></a>O que fazer

Verifique se os usuários em questão estão incluídos em uma política de barreira de informações. 

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de Identidade.

    |**Sintaxe** _|_ *Example**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> É possível usar qualquer valor que identifique com exclusividade cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan* e *alexw* para *Alex*. |

    > [!TIP]
    > Você também pode usar esse cmdlet para um único usuário: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Revise as descobertas. O cmdlet **Get-InformationBarrierRecipientStatus** retorna informações sobre usuários, como valores de atributos e quaisquer políticas de barreira de informações aplicadas.

    Revise os resultados e, em seguida, dê as próximas etapas, conforme descrito na tabela a seguir:

    |**Resultados**|**O que fazer em seguida**|
    |:----------|:------------------|
    | Nenhum segmento está listado para o(s) usuário(s) selecionado(s) | Siga um destes procedimentos:<br/>- Atribua usuários a um segmento existente editando seus perfis de usuário no Azure Active Directory. (Consulte [Configurar propriedades de conta de usuário com o Office 365 PowerShell.)](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- Definir um segmento usando um [atributo com suporte para barreiras de informações.](information-barriers-attributes.md) Em seguida, [defina uma nova política](information-barriers-policies.md#part-2-define-information-barrier-policies) [ou edite uma política existente](information-barriers-edit-segments-policies.md#edit-a-policy) para incluir esse segmento. |
    | Os segmentos são listados, mas nenhuma política de barreira de informações é atribuída a esses segmentos | Siga um destes procedimentos:<br/>- [Definir uma nova política de barreira de](information-barriers-policies.md#part-2-define-information-barrier-policies) informações para cada segmento em questão <br/>- [Editar uma política de barreira de informações existente](information-barriers-edit-segments-policies.md#edit-a-policy) para atribuí-la ao segmento correto |
    | Os segmentos são listados e cada um está incluído em uma política de barreira de informações | - Execute o `Get-InformationBarrierPolicy` cmdlet para verificar se as políticas de barreira de informações estão ativas<br/>- Execute o `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar se as políticas estão aplicadas<br/>- Execute o `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas as políticas de barreira de informações ativas |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: preciso remover um único usuário de uma política de barreira de informações

Nesse caso, as políticas de barreira de informações estão em vigor e um ou mais usuários são impedidos inesperadamente de se comunicar com outras pessoas no Microsoft Teams. Em vez de remover completamente as políticas de barreira de informações, você pode remover um ou mais usuários individuais das políticas de barreira de informações.

### <a name="what-to-do"></a>O que fazer

As políticas de barreira de informações são atribuídas a segmentos de usuários. Os segmentos são definidos usando [determinados atributos em perfis de conta de usuário.](information-barriers-attributes.md) Se você tiver que remover uma política de um único usuário, considere editar o perfil desse usuário no Azure Active Directory de forma que o usuário não seja mais incluído em um segmento afetado pelas barreiras de informações.

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de Identidade. Este cmdlet retorna informações sobre usuários, como valores de atributos e quaisquer políticas de barreira de informações aplicadas.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> É possível usar qualquer valor que identifique com exclusividade cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan* e *alexw* para *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> É possível usar qualquer valor que identifique o usuário com exclusividade, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> Neste exemplo, nos referimos a uma única conta no Office 365: *set.* |

2. Revise os resultados para ver se as políticas de barreira de informações estão atribuídas e a quais segmentos os usuários pertencem.

3. Para remover um usuário de um segmento afetado pelas barreiras de informações, atualize as informações de perfil do usuário [no Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Aguarde cerca de 30 minutos para que o FwdSync ocorra. Ou execute o `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas as políticas de barreira de informações ativas.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: o processo do aplicativo de barreira de informações está demorando muito

Depois de executar o cmdlet **Start-InformationBarrierPoliciesApplication,** o processo está demorando muito para terminar.

### <a name="what-to-do"></a>O que fazer

Lembre-se de que, ao executar o cmdlet de aplicativo de política, as políticas de barreira de informações estão sendo aplicadas (ou removidas), usuário por usuário, para todas as contas em sua organização. Se você tiver muitos usuários, demorará um pouco para processar. (Como diretriz geral, leva cerca de uma hora para processar 5.000 contas de usuário.)

1. Use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para verificar o status do aplicativo de política mais recente.

    |**Para exibir o aplicativo de política mais recente**|**Para exibir o status de todos os aplicativos de política**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Isso exibirá informações sobre se o aplicativo de política foi concluído, se falhou ou está em andamento.

2. Dependendo dos resultados da etapa anterior, tome uma das seguintes etapas:
  
    |**Status**|**Próxima etapa**|
    |:---------|:------------|
    | **Não iniciado** | Se tiver sido mais de 45 minutos desde que o cmdlet **Start-InformationBarrierPoliciesApplication** foi executado, revise seu log de auditoria para ver se há erros nas definições de política ou algum outro motivo pelo qual o aplicativo não foi iniciado. |
    | **Falhou** | Se o aplicativo tiver falhado, revise o log de auditoria. Revise também seus segmentos e políticas. Algum usuário está atribuído a mais de um segmento? Há segmentos atribuídos a mais de uma poliicia? Se necessário, [edite segmentos](information-barriers-edit-segments-policies.md#edit-a-segment) e/ou [edite](information-barriers-edit-segments-policies.md#edit-a-policy)políticas e execute o cmdlet **Start-InformationBarrierPoliciesApplication** novamente. |
    | **Em andamento** | Se o aplicativo ainda estiver em andamento, deixe mais tempo para ser concluído. Se já faz vários dias, reúna seus logs de auditoria e contate o suporte. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: as políticas de barreira de informações não estão sendo aplicadas

Nesse caso, você definiu segmentos, definiu políticas de barreira de informações e tentou aplicar essas políticas. No entanto, ao executar o `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, você pode ver que o aplicativo de política falhou.

### <a name="what-to-do"></a>O que fazer

Certifique-se de que sua organização não tenha políticas [de agenda do Exchange](/exchange/address-books/address-book-policies/address-book-policies) em uso. Essas políticas impedirão a aplicação de políticas de barreira de informações.

1. Conecte-se [ao PowerShell do Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o cmdlet [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) e revise os resultados.

    |**Resultados**|**Próxima etapa**|
    |:----------|:------------|
    | As políticas de agenda do Exchange estão listadas | [Remover políticas de lista de endereços](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Não há políticas de agendas existentes |Revise seus logs de auditoria para descobrir por que o aplicativo de política está falhando |

3. [Exibir o status de contas de usuário, segmentos, políticas ou aplicativo de política.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: política de barreira de informações não aplicada a todos os usuários designados

Depois de definir segmentos, definir políticas de barreira de informações e tentar aplicar essas políticas, você poderá descobrir que a política está se aplicando a alguns destinatários, mas não a outros.
Ao executar o cmdlet, procure texto assim na `Get-InformationBarrierPoliciesApplicationStatus` saída.

> Identidade: `<application guid>`
>
> Total de destinatários: 81527
>
> Destinatários com Falha: 2
>
> Categoria de Falha: Nenhum
>
> Status: Complete

### <a name="what-to-do"></a>O que fazer

1. Pesquise no log de auditoria `<application guid>` para . Você pode copiar esse código do PowerShell e modificar para suas variáveis.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Verifique a saída detalhada do log de auditoria para os valores `"UserId"` dos campos e dos `"ErrorDetails"` campos. Isso lhe dará o motivo da falha. Você pode copiar esse código do PowerShell e modificar para suas variáveis.

```powershell
   $DetailedLogs[1] |fl
```

Por exemplo:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Erro: O segmento IB "segment id1" e o segmento IB "segment id2" têm conflito e não podem ser atribuídos ao destinatário.

3. Normalmente, você encontrará que um usuário foi incluído em mais de um segmento. Você pode corrigir isso atualizando o `-UserGroupFilter` valor em `OrganizationSegments` .

4. Reaplicação de políticas de barreira de informações usando estes procedimentos [políticas de Barreiras de Informações.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Recursos

- [Definir políticas para barreiras de informações no Microsoft Teams](information-barriers-policies.md)
- [Barreiras de informações](information-barriers.md)
