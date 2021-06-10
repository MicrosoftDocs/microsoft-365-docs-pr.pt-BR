---
title: Gerenciar o processo de lançamento gradual para atualizações do Microsoft Defender
description: Saiba mais sobre o processo de atualização gradual e controles
keywords: atualizar, atualizar processo, controles, versão
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861997"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Gerenciar o processo de lançamento gradual para atualizações do Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)


É importante garantir que os componentes do cliente estão atualizados para oferecer recursos críticos de proteção e evitar ataques.

Os recursos são fornecidos por meio de vários componentes: 

- [Resposta & Detecção de Ponto de Extremidade](overview-endpoint-detection-response.md) 
- [Proteção de última geração com](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) proteção entregue na [nuvem](cloud-protection-microsoft-defender-antivirus.md) 
- [Redução de superfície de ataque](overview-attack-surface-reduction.md)

As atualizações são lançadas mensalmente usando um processo de versão gradual. Esse processo ajuda a habilitar a detecção de falha antecipada para capturar o impacto à medida que ocorre e a resolver rapidamente antes de uma adoção maior. 

> [!NOTE]
> Para obter mais informações sobre como controlar atualizações de definição diárias, consulte Agendar atualizações de definição Microsoft Defender Antivírus [- Windows segurança | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). As atualizações de definição garantem que a proteção de próxima geração possa se defender contra novas ameaças, mesmo se a proteção entregue na nuvem não estiver disponível para o ponto de extremidade.

## <a name="microsoft-gradual-rollout-model"></a>Modelo de lançamento gradual da Microsoft

O seguinte modelo de lançamento gradual é seguido:

1. A primeira versão sai para assinantes do canal Beta.
2. Após validação, comentários e correções, iniciamos o processo de distribuição gradual de maneira acelerada e primeiro visualizamos os assinantes do canal.
3. Em seguida, prosseguiremos para liberar a atualização para o restante da população global, dimensionando de 10 a 100%.

Nossos engenheiros monitoram continuamente o impacto e escalonam quaisquer problemas para criar uma correção conforme necessário.

## <a name="how-to-customize-your-internal-deployment-process"></a>Como personalizar seu processo de implantação interna

Se os seus máquinas estão recebendo atualizações do Defender do Windows Update, o processo de lançamento gradual pode resultar em alguns de seus máquinas recebendo atualizações do Defender antes de outras. A seção a seguir explica como definir uma estratégia que permitirá que as atualizações automáticas fluam de forma diferente para grupos específicos de dispositivos, aproveitando a configuração do canal de atualização.

> [!NOTE]
> Ao planejar sua própria versão gradual, certifique-se de sempre ter uma seleção de dispositivos inscritos nos canais de visualização e em estágios. Isso fornecerá à sua organização e à Microsoft a oportunidade de evitar ou encontrar e corrigir problemas específicos do seu ambiente.

Para máquinas que recebem atualizações por meio, por exemplo, Windows Server Update Services (WSUS) ou Microsoft Endpoint Configuration Manager (MECM), mais opções estão disponíveis para todas as atualizações Windows, incluindo opções para o Microsoft Defender para Ponto de Extremidade.

- Leia mais sobre como usar uma solução como WSUS, MECM para gerenciar a distribuição e a aplicação de atualizações em Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base - Windows segurança [| Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Atualizar canais para atualizações mensais

Você pode atribuir um computador a um canal de atualização para definir a cadência em que um computador recebe atualizações mensais do mecanismo e da plataforma.

Para obter mais informações sobre como configurar atualizações, consulte [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).

Os seguintes canais de atualização estão disponíveis:

| Nome do canal  | Descrição  | Aplicativo  |
|-|-|-|
| Canal Beta - Pré-lançamento  | Testar atualizações antes de outras pessoas  | Os dispositivos definidos para esse canal serão os primeiros a receber novas atualizações mensais. Selecione Canal Beta para participar da identificação e relatórios de problemas para a Microsoft. Dispositivos no programa Windows Insider são inscritos neste canal por padrão. Somente para uso em ambientes de teste.  |
| Canal Atual (Visualização)  | Obter atualizações do Canal Atual **anteriormente durante** a versão gradual  | Os dispositivos definidos para esse canal receberão atualizações mais cedo durante o ciclo gradual de lançamento. Sugerido para ambientes de pré-produção/validação.  |
| Canal Atual (Em estágios)  | Obter atualizações do Canal Atual posteriormente durante a versão gradual  | Os dispositivos receberão atualizações posteriormente durante o ciclo gradual de lançamento. Sugerida a aplicação a uma pequena parte representativa da sua população de dispositivos (~10%).  |
| Canal Atual (Amplo) | Obter atualizações no final da versão gradual  | Os dispositivos serão oferecidos atualizações somente após a conclusão do ciclo gradual de lançamento. Sugerida a aplicação a um amplo conjunto de dispositivos em sua população de produção (~10-100%).  |
| (padrão)  |   | Se você desabilitar ou não configurar essa política, o dispositivo permanecerá no Canal Atual (Padrão): mantenha-se atualizado automaticamente durante o ciclo gradual de lançamento. Adequado para a maioria dos dispositivos.  |

### <a name="update-channels-for-daily-definition-updates"></a>Atualizar canais para atualizações diárias de definição

Você pode atribuir um computador a um canal de atualização para definir a cadência em que um computador recebe atualizações de definição diárias.
  
| Nome do canal  | Descrição  | Aplicativo  |
|-|-|-|
| Canal Atual (Em estágios)  | Obter atualizações do Canal Atual posteriormente durante a versão gradual  | Os dispositivos receberão atualizações posteriormente durante o ciclo gradual de lançamento. Sugerida a aplicação a uma pequena parte representativa da sua população de dispositivos (~10%).  |
| Canal Atual (Amplo) | Obter atualizações no final da versão gradual  | Os dispositivos receberão atualizações após o ciclo gradual de lançamento. O melhor para máquinas de datacenter que recebem apenas atualizações limitadas. Observação: essa configuração se aplica a todas as atualizações do Defender.  |
| (padrão)  |   | Se você desabilitar ou não configurar essa política, o dispositivo permanecerá no Canal Atual (Padrão): mantenha-se atualizado automaticamente durante o ciclo gradual de lançamento. Adequado para a maioria dos dispositivos  |

> [!NOTE]
> Caso você queira forçar uma atualização para a assinatura mais recente em vez de aproveitar o atraso de tempo, você precisará remover essa política primeiro.

## <a name="update-guidance"></a>Diretrizes de atualização

Na maioria dos casos, a configuração recomendada ao usar o Windows Update é permitir que os pontos de extremidade recebam e apliquem atualizações mensais do Defender à medida que chegam. Isso fornece o melhor equilíbrio entre a proteção e o possível impacto associado às alterações que eles podem introduzir.

Para ambientes em que há a necessidade de uma distribuição gradual mais controlada de atualizações automáticas do Defender, considere uma abordagem com grupos de implantação:

1. Participe do programa Windows Insider ou atribua um grupo de dispositivos ao Canal Beta.
2. Designe um grupo piloto que opta pelo Canal de Visualização, normalmente ambientes de validação, para receber novas atualizações mais cedo.
3. Designe um grupo de máquinas que recebem atualizações posteriormente durante a distribuição gradual do canal Em estágios. Normalmente, isso seria um representante de ~10% da população.
4. Designe um grupo de máquinas que recebem atualizações após a conclusão do ciclo de lançamento gradual. Normalmente, são sistemas de produção importantes.

Para o restante dos dispositivos, a configuração padrão é receber novas atualizações à medida que elas chegam durante o processo de lançamento gradual da Microsoft e nenhuma outra configuração é necessária. 

Adotando este modelo:
- Permite que você teste as versões antecipadas antes que elas cheguem a um ambiente de produção 
- Verifique se o ambiente de produção ainda recebe atualizações regulares e garanta proteção contra ameaças críticas.

## <a name="management-tools"></a>Ferramenta de gerenciamento
Para criar seu próprio processo de lançamento gradual personalizado para atualizações mensais, você pode usar as seguintes ferramentas:

- Política de grupo
- Microsoft Endpoint Manager
- PowerShell

Para obter detalhes sobre como usar essas ferramentas, consulte [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).
