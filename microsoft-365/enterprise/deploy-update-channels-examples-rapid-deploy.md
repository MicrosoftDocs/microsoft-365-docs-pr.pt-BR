---
title: Exemplo de implantação abrangente das versões mais recentes
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Como uma organização que implanta a versão mais recente usa canais para aplicativos do Windows 10 e do Microsoft 365.
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686161"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>Exemplo de implantação abrangente das versões mais recentes

Esse exemplo de configuração de canal se destina a uma organização que usa a implantação rápida das versões mais recentes para atender a essas prioridades de negócios:

- Garanta a continuidade de negócios com os aplicativos e serviços da Microsoft.
- Maximize o acesso a dispositivos, serviços e dados com os recursos e correções mais recentes da Microsoft.
- Maximize a produtividade dos usuários com os recursos mais recentes da Microsoft.

Essas metas se traduzem na tarefa de TI de encontrar o equilíbrio entre a implantação de produção rápida e a verificação antecipada, com um subconjunto de usuários e dispositivos para validar funcionalmente antes da implantação abrangente.

Nosso exemplo de organização tem 5.000 funcionários em edifícios em todo o mundo na Europa, África, Ásia e nas Américas. 70% dos funcionários usam o Microsoft 365 E3 e o restante da organização usa o Microsoft 365 E5.

>[!Note]
>Este exemplo foi projetado para mostrar como você pode usar os estágios e os grupos de implantação, que podem funcionar para organizações de vários tipos e tamanhos.
>

A infraestrutura de TI desta organização: 

- É amplamente homogêneo com Windows, aplicativos da Microsoft 365 e serviços da nuvem da Microsoft que abrangem 60% da base instalada. Alguns sistemas herdados permanecem após um esforço intensivo de vários anos para simplificar a infraestrutura de TI.
- É mantido por uma equipe com alta experiência e com tarefas para manter os usuários e os dispositivos produtivos e seguros seguindo as versões líderes da Microsoft.

## <a name="deployment-and-update-stages"></a>Estágios de implantação e atualização

Com base nas metas de implantação rápida da versão mais recente, este exemplo de organização usa um processo de implantação de duas etapas.

1. **Use uma implantação de visualização ou piloto:** Validar e iterar com os pioneiros, a equipe de TI, usuários com configurações representativas e funcionários em treinamento. 

   Os pioneiros, a equipe de TI, os usuários com configurações representativas podem validar a funcionalidade com outros aplicativos e dispositivos antes que os novos recursos sejam lançados para o restante da organização.

   Os gerentes de mudança têm uma visualização antecipada dos novos recursos antes da implementação generalizada e podem planejar a troca de mensagens.

   A equipe de treinamento pode planejar novos cursos internos ou atualizar cursos existentes para os novos recursos antes de uma implantação abrangente.

2. **Implantação da produção:** implantação para todos os usuários restantes por região, departamento ou outro método de implantação.

## <a name="deployment-configuration-for-windows-10"></a>Configuração de implantação do Windows 10

O objetivo final é executar a implantação geral da atualização mais recente no Canal Semestral após a validação das modificações do lançamento do canal de visualização por um grupo de representantes e dispositivos. 

Confira [Implantação do Windows 10](https://docs.microsoft.com/windows/deployment/)para maiores informações sobre a implantação dos métodos e estratégias do Windows 10.

| Etapa | Canal | Grupo de implantação |
|:-------|:-------|:-----|
| Piloto |  **Lançamento da Versão prévia**  <ul><li>Propósito: a implantação de atualizações de recursos para a equipe de TI e os pioneiros a fazer a validação de dispositivos e configurações representativos (idiomas, aplicativos de terceiros). </li><li> Estado: totalmente compatível e com suporte para clientes comerciais e não conta com os acordos de suporte. </li></ul> | **Win10ReleasePreviewChannel** (nome do exemplo) <br><br> Os membros são grupos contendo: <ul><li> Fãs do Windows entre departamentos e locais </li><li> Funcionários que precisam de validação </li><li> Os administradores de TI e a equipe de implantação de TI </li><li> Gerentes de mudança </li><li> Equipe de treinamento interna </li></ul> |
| Produção |  **Canal Semestral**  <ul><li>Propósito: implantação abrangente das atualizações de recursos mais recentes para o restante da organização. </li><li> Estado: totalmente compatível e com suporte. </li></ul> | **Win10SemiAnnualChannel** (nome do exemplo) <br><br> Os membros são todos os usuários que não estão no grupo Win10ReleasePreviewChannel. |
||||

Esta organização usa a melhor prática de implantação do lançamento do conteúdo do canal de visualização da versão da mesma forma que as versões de canal semestrais, como o Windows Update ou Windows Server Update Services, e que aplicam as mesmas políticas para as atualizações de canal.

Processo de atualização contínua:

1. As alterações no canal de visualização de versão são implantadas no grupo de implantação Win10ReleasePreviewChannel (nome de exemplo).
2. Os membros do grupo Win10ReleasePreviewChannel confirmam que as alterações do canal de visualização de versão estão funcionando para a equipe de implantação de TI, que pode fornecer comentários à Microsoft e aguardar o próximo lançamento do canal de visualização para obter uma validação adicional.
3. As alterações de recursos de canal semestral são implantadas no grupo de implantação do Win10SemiAnnualChannel. 

>[!Note]
>Enquanto o canal semestral é o canal separador recomendado, o departamento de TI deve utilizar as ferramentas de gerenciamento dele e determinar quando implantar a versão mais recente do canal semestral dentro da organização e, em seguida, distribuí-la em ondas.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Configuração de implantação para aplicativos do Microsoft 365

A meta geral é executar uma implantação abrangente da versão mais recente do canal atual após a validação das mudanças do canal atual (visualização) por um grupo de usuários representativos.

Confira [implantação dos aplicativos da Microsoft 365](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) para obter mais informações sobre os métodos e estratégias de implantação dos aplicativos da Microsoft 365.

| Etapa | Canal | Grupo de implantação |
|:-------|:-------|:-----|
| Piloto |  **Canal Atual (Visualização)** <ul><li> Propósito: {conceda a um grupo de usuários representativos sobre os novos recursos dos aplicativos da Microsoft 365} a implantação de atualizações de recursos assim que elas forem testadas com os usuários do canal atual (Preview) e estarão prontas para produção. </li><li> Estado: totalmente compatível e com suporte.</li><li> Com que frequência: atualiza 2-3 vezes por mês. </li></ul> | **AppsCurrentChannelPreview** (nome do exemplo) <br><br> Os membros são grupos contendo: <ul><li> Fãs dos aplicativos do Office entre departamentos e locais </li><li> Funcionários que precisam de validação </li><li> Os administradores de TI e a equipe de implantação de TI </li><li> Gerentes de mudança </li><li> Equipe de treinamento interna </li></ul>|
| Produção | **Canal Atual** <ul><li> Propósito: implantação abrangente das atualizações de recursos mais recentes para o restante da organização. </li><li> Estado: totalmente compatível e com suporte. </li></ul> |  **AppsCurrentChannel** (nome do exemplo) <br><br> Os membros são todos os usuários que não estão no grupo AppsCurrentChannelPreview. |
|||

Processo de atualização contínua:

1. As alterações no canal atual (visualização) são implantadas no grupo de implantação do AppsCurrentChannelPreview.
2. Os membros do grupo AppsCurrentChannelPreview confirmam que as alterações no canal atual (visualização) estão funcionando para a equipe de implantação de ti, que pode fornecer comentários à Microsoft e aguardar a próxima versão do canal atual (visualização) para obter uma validação adicional.
3. As alterações no canal atual (visualização) são implantadas no grupo de implantação do AppsCurrentChannel. 

## <a name="visual-summary"></a>Resumo Visual

Estes são os produtos, seus canais e os grupos de implantação usados por este exemplo de organização. 

![Implantação abrangente das versões mais recentes](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>Confira também

[Exemplo de configurações de canal de implantação e atualização](deploy-update-channels-examples.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
