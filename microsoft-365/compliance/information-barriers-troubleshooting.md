---
title: Solução de problemas de barreiras de informações
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artigo como um guia para solucionar problemas de barreiras de informações.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5aa45e3e9dea5ce413b2b0e62d825003bc24e20e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352320"
---
# <a name="troubleshooting-information-barriers"></a>Solução de problemas de barreiras de informações

[As barreiras de informação](information-barriers.md) podem ajudar sua organização a permanecer em conformidade com requisitos legais e regulamentações do setor. Por exemplo, com barreiras de informações, você pode restringir a comunicação entre grupos específicos de usuários para evitar um conflito de interesses ou outros problemas. (Para saber mais sobre como configurar as barreiras de informações, confira [definir políticas para barreiras de informação](information-barriers-policies.md).)

No caso de as pessoas funcionarem em problemas inesperados depois que as barreiras de informações estiverem vigentes, há algumas etapas que você pode executar para resolver esses problemas. Use este artigo como uma guia.

> [!IMPORTANT]
> Para executar as tarefas descritas neste artigo, você deve receber uma função apropriada, como uma das seguintes:<br/>– Administrador global do Microsoft 365 Enterprise<br/>-administrador global<br/>-Administrador de conformidade<br/>– Gerenciamento de conformidade do IB (esta é uma nova função!)<p>Para saber mais sobre os pré-requisitos para barreiras de informações, consulte [pré-requisitos (para políticas de barreira de informações)](information-barriers-policies.md#prerequisites).<p>Certifique-se de [se conectar ao PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: os usuários são impedidos de se comunicar inesperadamente com outras pessoas no Microsoft Teams 

Nesse caso, as pessoas estão relatando problemas inesperados ao se comunicar com outras pessoas no Microsoft Teams. Exemplos:
- Um usuário procura, mas não consegue encontrar, outro usuário no Microsoft Teams.
- Um usuário pode localizar, mas não pode selecionar, outro usuário no Microsoft Teams.
- Um usuário pode ver outro usuário, mas não pode enviar mensagens para esse outro usuário no Microsoft Teams.

### <a name="what-to-do"></a>O que fazer

Determinar se os usuários são afetados por uma política de barreira de informações. Dependendo de como as políticas são configuradas, as barreiras de informações podem estar funcionando conforme o esperado. Ou você pode precisar refinar as políticas da sua organização.

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com o parâmetro Identity. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>Você pode usar qualquer valor de identidade que identifique exclusivamente cada destinatário, como nome, alias, nome diferenciado (DN), DN canônica, endereço de email ou GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>Neste exemplo, estamos usando um alias (*meganb*) para o parâmetro Identity. Este cmdlet retornará informações que indicam se o usuário é afetado por uma política de barreira de informações. (Procure * ExoPolicyId: \< GUID>.)         |

    **Se os usuários não estiverem incluídos nas políticas de barreira de informações, entre em contato com o suporte**. Caso contrário, prossiga para a próxima etapa.

2. Descubra quais segmentos estão incluídos em uma política de barreira de informações. Para fazer isso, use o `Get-InformationBarrierPolicy` cmdlet com o parâmetro Identity. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>Use detalhes, como o GUID da política (ExoPolicyId) que você recebeu durante a etapa anterior, como um valor de identidade.     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>Neste exemplo, estamos obtendo informações detalhadas sobre a política de barreira de informações que tem o ExoPolicyId *b42c3d0f-49E9-4506-a0a5-bf2853b5df6f*.         |

    Depois de executar o cmdlet, nos resultados, procure os valores **AssignedSegment**, **SegmentsAllowed**e **SegmentsBlocked** .

    Por exemplo, depois de executar o `Get-InformationBarrierPolicy` cmdlet, vimos o seguinte em nossa lista de resultados:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    Nesse caso, podemos ver que uma política de barreira de informações afeta as pessoas que estão nos segmentos de vendas e de pesquisa. Nesse caso, as pessoas em vendas são impedidas de se comunicar com pessoas em pesquisa. 
    
    Se isso parecer correto, as barreiras de informação estão funcionando conforme o esperado. Caso contrário, vá para a próxima etapa.

4. Certifique-se de que seus segmentos estejam definidos corretamente. Para fazer isso, use o `Get-OrganizationSegment` cmdlet e revise a lista de resultados. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>Use este cmdlet com um parâmetro Identity.     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>Neste exemplo, estamos obtendo informações sobre o segmento que tem GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.         |

    Revise os detalhes do segmento. Se necessário, [edite um segmento](information-barriers-edit-segments-policies.md#edit-a-segment)e, em seguida, use o `Start-InformationBarrierPoliciesApplication` cmdlet novamente.

    **Se você ainda estiver tendo problemas com a política de barreira de informações, entre em contato com o suporte**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: as comunicações são permitidas entre usuários que devem ser bloqueados no Microsoft Teams

Nesse caso, embora as barreiras de informação sejam definidas, ativas e aplicadas, as pessoas que devem ser impedidas de se comunicar umas com as outras estão, de qualquer forma, com o uso de chat e chamadas entre si no Microsoft Teams.

### <a name="what-to-do"></a>O que fazer

Verifique se os usuários em questão estão incluídos em uma política de barreira de informações. 

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de identidade.

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>Você pode usar qualquer valor que identifique exclusivamente cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan*e *alexw* para *Alex*.          |

    
    > [!TIP]
    > Você também pode usar esse cmdlet para um único usuário:`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. Revise as descobertas. O cmdlet **Get-InformationBarrierRecipientStatus** retorna informações sobre os usuários, como valores de atributo e quaisquer políticas de barreira de informação aplicadas. 

    Revise os resultados e siga as próximas etapas, conforme descrito na tabela a seguir:
    
    |Resultados  |O que fazer em seguida  |
    |---------|---------|
    |Nenhum segmento está listado para os usuários selecionados     |Siga um destes procedimentos:<br/>– Atribua usuários a um segmento existente editando seus perfis de usuário no Azure Active Directory. (Consulte [Configurar Propriedades da conta de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).)<br/>-Definir um segmento usando um [atributo com suporte para barreiras de informação](information-barriers-attributes.md). Em seguida, [defina uma nova política](information-barriers-policies.md#part-2-define-information-barrier-policies) ou [edite uma política existente](information-barriers-edit-segments-policies.md#edit-a-policy) para incluir esse segmento.  |
    |Os segmentos estão listados, mas nenhuma política de barreira de informações é atribuída a esses segmentos     |Siga um destes procedimentos:<br/>- [Definir uma nova política de barreira de informações](information-barriers-policies.md#part-2-define-information-barrier-policies) para cada segmento em questão<br/>- [Editar uma política de barreira de informações existente](information-barriers-edit-segments-policies.md#edit-a-policy) para atribuí-la ao segmento correto         |
    |Os segmentos são listados e cada um é incluído em uma política de barreira de informações     |– Execute o `Get-InformationBarrierPolicy` cmdlet para verificar se as políticas de barreira de informações estão ativas<br/>– Execute o `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar que as políticas foram aplicadas<br/>– Execute o `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas as políticas de barreira de informações ativas          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: preciso remover um único usuário de uma política de barreira de informações

Nesse caso, as políticas de barreira de informações estão em vigor e um ou mais usuários são impedidos de se comunicar inesperadamente com outras pessoas no Microsoft Teams. Em vez de remover totalmente as políticas de barreira de informações, você pode remover um ou mais usuários individuais das políticas de barreira de informações. 

### <a name="what-to-do"></a>O que fazer

As políticas de barreira de informações são atribuídas aos segmentos de usuários. Os segmentos são definidos usando determinados [atributos nos perfis de conta de usuário](information-barriers-attributes.md). Se você precisar remover uma política de um único usuário, considere editar o perfil do usuário no Azure Active Directory de modo que o usuário não esteja mais incluído em um segmento afetado por barreiras de informação.

1. Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de identidade. Este cmdlet retorna informações sobre usuários, como valores de atributos e quaisquer políticas de barreira de informação aplicadas.

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>Você pode usar qualquer valor que identifique exclusivamente cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan*e *alexw* para *Alex*.          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>Você pode usar qualquer valor que identifique exclusivamente o usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>Neste exemplo, vamos nos referir a uma única conta no Office 365: *jeanp*. |

2. Revise os resultados para ver se as políticas de barreira de informações são atribuídas e a quais segmentos o (s) usuário (s) pertence. 

3. Para remover um usuário de um segmento afetado por barreiras de informação, [atualize as informações de perfil do usuário no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Aguarde cerca de 30 minutos para que o FwdSync ocorra. Ou execute o `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas as políticas de barreira de informações ativas.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: o processo do aplicativo de barreira de informações está demorando muito

Depois de executar o cmdlet **Start-InformationBarrierPoliciesApplication** , o processo está demorando muito tempo para terminar.

### <a name="what-to-do"></a>O que fazer

Tenha em mente que quando você executa o cmdlet aplicativo de política, as políticas de barreira de informações são aplicadas (ou removidas), usuário por usuário para todas as contas da sua organização. Se você tiver muitos usuários, levará algum tempo para ser processado. (Como uma diretriz geral, leva cerca de uma hora para processar as contas de usuário 5.000.)

1. Use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para verificar o status do aplicativo de política mais recente.

    |Para exibir o aplicativo de política mais recente  |Para exibir o status de todos os aplicativos de política  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    Isso exibirá informações sobre se o aplicativo de política foi concluído, falhou ou está em andamento.

2. Dependendo dos resultados da etapa anterior, execute uma das seguintes etapas:
  
    |Status  |Próxima etapa  |
    |---------|---------|
    |**Não iniciado**     |Se tiver sido mais de 45 minutos desde que o cmdlet **Start-InformationBarrierPoliciesApplication** foi executado, revise o log de auditoria para ver se há algum erro nas definições de política ou outro motivo pelo qual o aplicativo não foi iniciado. |
    |**Falhou**     |Se o aplicativo falhou, revise o log de auditoria. Além disso, revise seus segmentos e políticas. Há usuários atribuídos a mais de um segmento? Há segmentos atribuídos a mais de um poliicy? Se necessário, [edite segmentos](information-barriers-edit-segments-policies.md#edit-a-segment) e/ou [edite políticas](information-barriers-edit-segments-policies.md#edit-a-policy)e, em seguida, execute o cmdlet **Start-InformationBarrierPoliciesApplication** novamente.  |
    |**Em andamento**     |Se o aplicativo ainda estiver em andamento, permita que mais tempo seja concluído. Se houver vários dias, reúna seus logs de auditoria e entre em contato com o suporte. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: as políticas de barreira de informações não estão sendo aplicadas

Nesse caso, você definiu segmentos, definiu políticas de barreira de informações e tentou aplicar essas políticas. No entanto, ao executar o `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, você pode ver que o aplicativo de política falhou.

### <a name="what-to-do"></a>O que fazer

Certifique-se de que sua organização não tenha [diretivas de catálogo de endereços do Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) no local. Essas políticas impedirão que as políticas de barreira de informações sejam aplicadas.

1. Conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps). 

2. Execute o cmdlet [Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy?view=exchange-ps) e revise os resultados.

    |Resultados  |Próxima etapa  |
    |---------|---------|
    |As políticas do catálogo de endereços do Exchange estão listadas     |[Remover políticas de catálogo de endereços](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |Não há políticas de catálogo de endereços |Revise seus logs de auditoria para descobrir por que o aplicativo de política está falhando |

3. [Exibir o status de contas de usuário, segmentos, políticas ou aplicativos de política](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: política de barreira de informações não aplicada a todos os usuários designados

Depois de definir os segmentos, definir as políticas de barreira de informações e tentar aplicar essas políticas, você poderá achar que a política está se aplicando a alguns destinatários, mas não a outros.
Ao executar o `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, procure o texto de saída como este.

> Ladrões`<application guid>`
>
> Total de destinatários: 81527
>
> Destinatários com falha: 2
>
> Categoria de falha: nenhum
>
> Status: concluir

### <a name="what-to-do"></a>O que fazer

1. Pesquisar no log de auditoria para `<application guid>` . Você pode copiar esse código do PowerShell e modificá-lo para suas variáveis.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Verifique a saída detalhada do log de auditoria para os valores dos `"UserId"` campos e `"ErrorDetails"` . Isso fornecerá o motivo da falha. Você pode copiar esse código do PowerShell e modificá-lo para suas variáveis.

```powershell
   $DetailedLogs[1] |fl
```
 Por exemplo:

> "UserId": Usuário1
> 
>"ErrorDetails": "status: IBPolicyConflict. Erro: o segmento IB "Segment ID1" e o segmento IB "Segment ID2" tem conflito e não pode ser atribuído ao destinatário. 

3. Normalmente, você verá que um usuário foi incluído em mais de um segmento. Você pode corrigir isso atualizando o `-UserGroupFilter` valor em `OrganizationSegments` .

4. Reaplique as políticas de barreira de informações usando estes procedimentos [políticas de barreiras de informação](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="related-topics"></a>Tópicos relacionados

[Definir políticas para barreiras de informações no Microsoft Teams](information-barriers-policies.md)

[Barreiras de informações](information-barriers.md)
