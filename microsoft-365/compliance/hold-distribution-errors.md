---
title: Resolver erros de retenção da descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Solucionar erros relacionados a rescisões legais aplicadas a custodiantes e fontes de dados não custodiais na Descoberta Principal.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860382"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>Resolver erros de retenção da descoberta eletrônica

Este artigo discute problemas comuns que podem ocorrer com resites de Descoberta e como resolvê-los. O artigo também inclui práticas recomendadas para ajudá-lo a mitigar ou evitar esses problemas.

## <a name="recommended-practices"></a>Práticas recomendadas

Para reduzir o número de erros relacionados a ressarções de Descoberta e, recomendamos as seguintes práticas:

- Se uma distribuição de espera ainda estiver pendente, com um status de ou , aguarde até que a distribuição de espera seja concluída antes de fazer `On (Pending)` `Off (Pending)` outras atualizações.

- Mesclar suas atualizações a uma parada de Descoberta Automática em uma única solicitação em massa, em vez de atualizar a política de espera repetidamente para cada transação. Por exemplo, para adicionar várias caixas de correio de usuário a uma política de bloqueio existente usando o cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) execute o comando (ou adicione como um bloco de código a um script) para que ele seja executado apenas uma vez para adicionar vários usuários.

  **Correto**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Incorreto**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   No exemplo incorreto anterior, o cmdlet é executado cinco vezes separadamente para concluir a tarefa. Para obter mais informações sobre as práticas recomendadas para adicionar usuários a uma política de espera, consulte a [seção Mais](#more-information) informações.

- Antes de entrar em contato com o Suporte da Microsoft sobre problemas de responsabilidade de Descoberta eDiscovery, siga as etapas na seção [Erro/problema:](#errorissue-holds-dont-sync) Retém não sincronizar para tentar novamente a distribuição de espera. Esse processo geralmente resolve problemas temporários, incluindo erros internos do servidor.

## <a name="errorissue-holds-dont-sync"></a>Erro/problema: retém não sincronizar

Se você vir uma das seguintes mensagens de erro ao colocar os custodiantes e fontes de dados em espera, use as etapas de resolução para solucionar o problema.

> Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.

> A política não pode ser implantada na fonte de conteúdo devido a um problema Office 365 datacenter temporário. A política atual não é aplicada a qualquer conteúdo na origem, portanto, não há impacto da implantação bloqueada. Para corrigir esse problema, tente reimplantar a política.

> Não foi possível executar as alterações solicitadas na política devido a um erro de servidor interno transitório. Tente novamente em 30 minutos.

### <a name="resolution"></a>Resolução

1. Conexão ao [Centro de Conformidade & Segurança](/powershell/exchange/connect-to-scc-powershell) do PowerShell e execute o seguinte comando para uma ressarção de Descoberta Digital:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Examine o valor no parâmetro *DistributionDetail.* Procure erros como o seguinte:

   > Erro: Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.

3. Tente executar o **comando Set-CaseHoldPolicy -RetryDistribution** na política de espera em questão; por exemplo:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>Mais informações

- As diretrizes sobre a atualização de políticas de bloqueio para vários usuários na seção "Práticas recomendadas" resulta do fato de que o sistema bloqueia atualizações simultâneas para uma política de bloqueio. Isso significa que, quando uma política de espera atualizada é aplicada a novos locais de conteúdo e a política de espera está em um estado pendente, locais de conteúdo adicionais não podem ser adicionados à política de espera. Aqui estão algumas coisas a ter em mente para ajudá-lo a atenuar esse problema:
  
  - Sempre que uma espera atualizada é atualizada, ela entra imediatamente em um estado pendente. O status de estado pendente significa que a ressarção está sendo aplicada a locais de conteúdo.
  
  - Se você tiver um script que executa um loop e adiciona locais à política um a um (semelhante ao exemplo incorreto mostrado na seção "Práticas Recomendadas"), o primeiro local de conteúdo (por exemplo, uma caixa de correio de usuário) iniciará o processo de sincronização que dispara o estado pendente. Isso significa que os outros usuários adicionados à política em loops subsequentes resultam em um erro.
  
  - Se sua organização estiver usando um script que executa um loop para atualizar os locais de conteúdo de uma política de espera, você deve atualizar o script para que ele atualize os locais em uma única operação em massa (conforme mostrado no exemplo correto na seção "Práticas Recomendadas").
