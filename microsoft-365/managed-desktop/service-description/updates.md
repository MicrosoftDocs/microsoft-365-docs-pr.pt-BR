---
title: Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft
description: Manter a Área de Trabalho Gerenciada da Microsoft atualizada é um equilíbrio de velocidade e estabilidade.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5961ac4eb16928754849f5f32ecd06d4d2e4650d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917711"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

A Área de Trabalho Gerenciada da Microsoft conecta todos os dispositivos a uma infraestrutura moderna baseada em nuvem. Manter os aplicativos Windows, Office, drivers, firmware e Microsoft Store para Empresas atualizados é um equilíbrio de velocidade e estabilidade. Os grupos de implantação serão usados para garantir que as atualizações e políticas do sistema operacional sejam implantadas de maneira segura. Para obter mais informações, consulte o vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

As atualizações lançadas pela Microsoft são cumulativas e são categorizadas como atualizações de qualidade ou recursos.
Para obter mais informações, consulte [Windows Update for Business: Tipos de atualização](/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Atualizar grupos

A Área de Trabalho Gerenciada da Microsoft usa quatro grupos do Azure AD para gerenciar atualizações:

- **Teste**: usado para validar alterações de política da Área de Trabalho Gerenciada da Microsoft, atualizações do sistema operacional, atualizações de recursos e outras alterações empurradas para o locatário. Não deve haver nenhum usuário colocado no grupo de teste. O grupo de teste está isento de quaisquer contratos de nível de serviço estabelecidos e suporte ao usuário. Esse grupo está disponível para uso para validar a compatibilidade de aplicativos com novas alterações de política ou sistema operacional.  
- **Primeiro:** contém dispositivos e dispositivos que podem estar sujeitos a atualizações de pré-lançamento. Os dispositivos nesse grupo podem ter paralisações se houver cenários que não foram abordados durante o teste no anel de teste.
- **Fast**: prioriza a velocidade sobre a estabilidade. Útil para detectar problemas de qualidade antes que eles sejam oferecidos ao grupo Broad. Esse grupo serve como uma próxima camada de validação, mas normalmente é mais estável do que os grupos Test e First. 
- **Broad**: Último grupo a ter atualizações de recursos e qualidade disponíveis. Esse grupo contém a maioria dos usuários no locatário e, portanto, favorece a estabilidade sobre a velocidade na implantação. Os testes de aplicativos devem ser feitos aqui, pois o ambiente é mais estável. 

### <a name="moving-devices-between-update-groups"></a>Mover dispositivos entre grupos de atualização
Você pode querer que alguns dispositivos recebam atualizações por último e outros que você deseja primeiro. Para mover esses dispositivos para o grupo de atualizações apropriado, [envie](../working-with-managed-desktop/admin-support.md?view=o365-worldwide) uma solicitação de suporte ao administrador e moveremos os dispositivos para você. 

> [!NOTE]
> Se você precisar mover um usuário para um grupo de atualização diferente, envie uma solicitação de suporte. Não mova os dispositivos entre os grupos de atualização por conta própria. Há sérias consequências se um dispositivo for movido incorretamente. O dispositivo pode ser atualizado inesperadamente e as políticas podem conflitar, alterando a configuração do dispositivo.

Para obter mais informações sobre funções e responsabilidades dentro desses grupos de implantação, consulte Funções e [responsabilidades](../intro/roles-and-responsibilities.md) da Área de Trabalho Gerenciada da Microsoft

### <a name="using-microsoft-managed-desktop-update-groups"></a>Usando grupos de atualização da Área de Trabalho Gerenciada da Microsoft 
Há partes do serviço que você gerencia, como a implantação de aplicativos, onde pode ser necessário direcionar todos os dispositivos gerenciados. Nessas instâncias, faz sentido usar grupos de atualização para alcançar esses usuários com a compreensão de que você não pode adicionar, remover ou alterar a associação desses grupos. 

## <a name="how-update-deployment-works"></a>Como funciona a implantação de atualização:
1. A Área de Trabalho Gerenciada da Microsoft implanta um novo recurso ou atualização de qualidade de acordo com o cronograma especificado na tabela a seguir.
2. Durante a implantação, a Área de Trabalho Gerenciada da Microsoft monitora sinais de falha ou interrupção com base nos dados de diagnóstico e no sistema de suporte do usuário. Se algum for detectado, pausamos imediatamente a implantação para todos os grupos atuais e futuros.
    - Exemplo: se um problema for descoberto ao implantar uma atualização de qualidade no primeiro grupo, atualize as implantações para First, Fast e Broad serão pausadas até que o problema seja resolvido.
    - Você pode relatar problemas de compatibilidade arquivando um tíquete no portal de Administração da Área de Trabalho Gerenciada da Microsoft.
    - Atualizações de recursos e qualidade são pausadas independentemente. A pausa está em vigor por 35 dias por padrão, mas pode ser reduzida ou estendida, dependendo da correção do problema.
3. Depois que os grupos não são pausados, a implantação é retomada de acordo com o cronograma na tabela.

Esse processo de implantação se aplica a atualizações de recursos e qualidade, embora a linha do tempo varie para cada um.




<table>
    <tr><th colspan="5">Atualizar configurações de implantação</th></tr>
    <tr><th>Tipo de atualização</th><th>Testar</th><th>Primeiro</th><th>Rápida</th><th>Amplas</th></tr>
    <tr><td>Atualizações de qualidade para o sistema operacional</td><td>0 dias</td><td>0 dias</td><td>0 dias</td><td>3 dias</td></tr>
    <tr><td>Atualizações de recursos para o sistema operacional</td><td>0 dias</td><td>30 dias</td><td>60 dias</td><td>90 dias</td></tr>
    <tr><td>Drivers/firmware</td><td colspan="4">Segue o cronograma de atualizações de qualidade</td></tr>
    <tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada verificação</td></tr>
    <tr><td>Microsoft 365 Apps para empresas</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Saiba Mais</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Saiba Mais</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Saiba Mais</a></td></tr>
</table>

>[!NOTE]
>Esses períodos de adiamento foram intencionalmente projetados para garantir padrões de alta segurança e desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos da Área de Trabalho Gerenciada da Microsoft e no escopo variável e no impacto das atualizações, a Área de Trabalho Gerenciada da Microsoft reserva flexibilidade para modificar o comprimento dos períodos de adiamento acima para todos e todos os grupos de implantação de forma ad hoc.
>
>A Área de Trabalho Gerenciada da Microsoft realiza uma avaliação independente de cada versão de recursos do Windows para avaliar sua necessidade e utilidade para seus locatários gerenciados. Consequentemente, a Área de Trabalho Gerenciada da Microsoft pode ou não implantar todas as atualizações de recursos do Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

A Área de Trabalho Gerenciada da Microsoft não dá suporte a dispositivos que fazem parte do programa Windows Insider. O programa Windows Insider é usado para validar o software do Windows de pré-lançamento e destina-se a dispositivos que não são críticos de missão. Embora seja uma iniciativa importante da Microsoft, ela não se destina à implantação ampla em ambientes de produção. 

Todos os dispositivos encontrados com builds do Windows Insider podem ser colocados no grupo teste e estarão isentos dos contratos de nível de serviço de atualização e do suporte do usuário da Área de Trabalho Gerenciada da Microsoft.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

Usamos [a Otimização de Entrega](/windows/deployment/update/waas-delivery-optimization) para todas as atualizações do sistema operacional e do driver. Isso minimiza o tamanho do download do serviço Windows Update buscando atualizações de pares dentro da rede corporativa.