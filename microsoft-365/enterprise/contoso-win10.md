---
title: Implantação do Windows 10 Enterprise para a Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.
ms.openlocfilehash: a63a973bed4bf62ebf7c2534d4c55a4e3b8ef60c
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370468"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Implantação do Windows 10 Enterprise para a Contoso

**Resumo:** entenda como a Contoso usou o System Center Configuration Manager para implantar atualizações in-loco para o Windows 10 Enterprise.

Antes da ampla implantação do Microsoft 365 Enterprise, a Contoso tinha computadores e dispositivos compatíveis com o Windows que executavam uma combinação de Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). A Contoso queria atualizar seus computadores para o Windows 10 Enterprise para aproveitar a segurança aprimorada e reduzir a sobrecarga da TI em implantações automatizadas de atualizações. 

Depois de avaliar suas necessidades de infraestrutura e comerciais, a Contoso identificou esses principais requisitos para a implantação:

- O maior número possível de PCs e dispositivos que devem executar o Windows 10 Enterprise
- A implantação das atualizações in-loco aproveita a infraestrutura existente do System Center Configuration Manager
- O controle de quais versões do Windows 10 Enterprise implantar e atualizar são feitas por meio de anéis
- Os PCs e dispositivos devem estar atualizados com custos administrativos mínimos de TI e com impacto mínimo para os usuários finais

A data atual é definida como a versão suportada do Windows 10 Enterprise que atende às necessidades comerciais da Contoso, o que pode ser diferente de ter todos os PCs compatíveis com o Windows que executa a versão mais recente do Windows 10 Enterprise.

## <a name="deployment-tools"></a>Ferramentas de implantação

Antes e durante as atualizações in-loco do Windows 10 Enterprise, a Contoso usou as seguintes soluções do Windows Analytics:

- Upgrade Readiness  

  Coleta dados do sistema, aplicativo e driver para análise e, em seguida, identifica problemas de compatibilidade que podem bloquear uma atualização e correções sugeridas de problemas conhecidos da Microsoft.

- Conformidade de atualização  

  Mostra o estado dos dispositivos com relação às atualizações do Windows para que você possa garantir que eles estejam nas atualizações mais recentes conforme apropriado.

- Integridade do dispositivo  

  Identifica os dispositivos que falham com frequência e, portanto, talvez precisem ser recriados ou substituídos, e os drivers de dispositivo que estejam falhando, com sugestões de versões alternativas desses drivers, podem reduzir o número de falhas. Fornece notificação de configurações incorretas de proteção de informações do Windows que enviam avisos para os usuários finais.
 
A Contoso possui uma infraestrutura existente do System Center Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalações, atualizações e configurações. Ele também possui recursos internos para facilitar e efetivar a implantação e o gerenciamento do Windows 10 Enterprise.

## <a name="planning-process"></a>Processo de planejamento

Antes da implantação, a Contoso definiu os seguintes anéis:

- Três anéis para validação e preparação da implantação 
  - Um para compilações de visualização 
  - Um para compilações da nova versão
  - Um para compilações anteriores 
- Um anel para a implantação geral do Windows 10 Enterprise com base nos dados dos anéis de validação

A Contoso também usou a solução Upgrade Readiness do Windows Analytics para determinar o conjunto de aplicativos instalados e sua compatibilidade com o Windows 10 Enterprise.

## <a name="deployment-process"></a>Processo de implantação

Para concluir a implantação da atualização in-loco do Windows 10 Enterprise, a Contoso implementou o seguinte processo, que inclui recomendações de práticas recomendadas da Microsoft:

1. Habilitou o cache par para o Configuration Manager.
2. Criou pacotes personalizados do Windows com base em imagens do Centro de Atendimento de Licenciamento por Volume.
3. Utilizou o Configuration Manager para implantar os pacotes do Windows em pontos de distribuição em toda a rede e em compilações implantadas para os três anéis de armazenamento temporário de validação e implantação.
4. Realizou uma avaliação de sucesso para PCs e dispositivos nos três anéis de teste de validação e implantação usando as soluções de Integridade do dispositivos e Conformidade de atualização do Windows Analytics.
5. Com base nas informações do Windows Analytics, a Contoso determinou qual versão do Windows 10 Enterprise será implantada no anel de implantação geral.
6. Executou as sequências das tarefas de implantação do Configuration Manager para implantar o pacote do Windows escolhido no anel de implantação geral.
7. Os computadores e dispositivos monitorados na implantação geral usam as soluções de integridade dos dispositivos e conformidade de atualização fornecidas para solucionar problemas.

Veja a atualização in-loco e a arquitetura de implantação de atualizações contínuas.

![Infraestrutura de implantação do Windows 10 Enterprise da Contoso](./media/contoso-win10/contoso-win10-fig1.png)

Esta infraestrutura é formada pelo:

- System Center Configuration Manager que:
  - Obtém imagens para pacotes do Windows 10 Enterprise a partir do Centro de Licenciamento por Volume da Microsoft na Rede da Microsoft.
  - É o ponto de administração central para pacotes de implantação.
- Pontos de distribuição regionais que normalmente estão localizados nos escritórios secundários da Contoso.
- Os dispositivos e computadores Windows em vários locais que recebem e instalam os pacotes de implantação para atualizações in-loco ou atualizações contínuas com base na associação do anel.

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-o365pp.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Office 365 ProPlus atualizado em toda a organização. 

## <a name="see-also"></a>Confira também

[Windows 10 Enterprise para Microsoft 365 Enterprise](windows10-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
