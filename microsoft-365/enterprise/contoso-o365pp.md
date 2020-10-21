---
title: Implantação do Microsoft 365 Apps for enterprise para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa o Microsoft Endpoint Configuration Manager para implantar o Microsoft 365 Apps para Grandes Empresas.
ms.openlocfilehash: 63993a27f23843fd2d75ef9bf08ae064ec46dc77
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637158"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implantação do Microsoft 365 Apps for enterprise para Contoso

A contoso atualizou seus computadores para o Windows 10 Enterprise e o Microsoft 365 aplicativos para Enterprise para permitir uma colaboração mais eficaz, maior segurança e uma experiência de área de trabalho mais moderna. Depois de avaliar suas necessidades de infraestrutura e negócios, a contoso identificou esses requisitos importantes para a implantação:

- Todos os computadores devem executar o Microsoft 365 aplicativos para empresas.
- A implantação deve usar as ferramentas de gerenciamento e a infraestrutura existentes, quando possível.
- A implantação deve suportar vários idiomas e arquiteturas existentes nos dispositivos dos usuários.
- Os computadores devem estar atualizados e seguros com custos administrativos mínimos de ti e impacto mínimo para os usuários.

## <a name="deployment-tools"></a>Ferramentas de implantação

Com base em seus requisitos, a contoso optou por implantar o Windows 10 Enterprise e o Microsoft 365 aplicativos para empresas através do Configuration Manager (Branch atual). O Gerenciador de configurações é dimensionado para grandes ambientes e oferece um amplo controle sobre instalação, atualizações e configurações. Ele também tem recursos internos para tornar mais fácil e mais eficiente implantar e gerenciar o Office, incluindo:

- Cache par, que pode ajudar com a capacidade de rede limitada ao implantar para dispositivos em locais remotos.
- O painel de gerenciamento de cliente do Office, que facilita a implantação de atualizações do Office e do monitor e oferece aos administradores acesso aos recursos de implantação e gerenciamento mais recentes.
- Implantação de pacotes de idiomas inteligentes, incluindo a implantação automática do mesmo idioma do sistema operacional.
- Um método totalmente compatível e fácil de usar de remover versões existentes do Office de um cliente durante a implantação.

Além do Configuration Manager, a contoso usou o [Readiness Toolkit para suplemento do Office e o VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), uma ferramenta gratuita da Microsoft, para avaliar problemas de compatibilidade com suas macros e suplementos do Office.

## <a name="managing-deployment-and-updates"></a>Gerenciando a implantação e atualizações

O Microsoft 365 Apps for Enterprise tem um novo modelo de versão: Office como um serviço. O modelo de serviço facilita a permanência dos novos recursos. Mas geralmente exige que os departamentos de ti alterem como implantar e testar novas versões. Para minimizar os problemas de compatibilidade e garantir que seus computadores permaneçam atualizados, a contoso implantou o Windows e o Office em dois estágios:

- Primeiro, implantamos o Microsoft 365 Apps for Enterprise para um pequeno conjunto de dispositivos representativos em toda a organização. Este grupo piloto foi usado para testar aplicativos, suplementos e hardware com o Microsoft 365 aplicativos para empresas.
- Quatro meses depois disso, após resolver todos os problemas graves com aplicativos, suplementos e hardware no grupo piloto, a Contoso implantou o Microsoft 365 Apps for enterprise no restante dos dispositivos da organização (o grupo amplo).

Em vez de gerenciar atualizações para o Office usando o Gerenciador de configurações, a contoso habilitou as atualizações automáticas da nuvem. As atualizações baseadas em nuvem reduzem a sobrecarga administrativa e garantem que os dispositivos permaneçam atualizados.

A contoso seguiu a mesma abordagem de dois estágios para atualizações de recursos, como elas usavam para implantar o Office: os dispositivos no grupo piloto recebeu atualizações quatro meses antes de dispositivos no restante da organização (o amplo grupo). Para habilitar isso no Office, a Contoso usou dois [canais de atualização](https://docs.microsoft.com/DeployOffice/overview-update-channels) recomendados:

- Canal Empresarial Semestral (Visualização) para atualizações do grupo piloto
- Semi-Annual canal empresarial para atualizações para o grupo amplo

Como o Canal Empresarial Semestral (Visualização) lança uma versão do Microsoft 365 Apps para Grandes Empresas quatro meses antes do Canal Empresarial Semestral, a Contoso tem tempo para validar as atualizações sem precisar gerenciá-las.

## <a name="deployment-process"></a>Processo de implantação

Para concluir a implantação do Office, a Contoso implementou o seguinte processo, que inclui as práticas recomendadas da Microsoft:

1. Antes da implantação, a contoso usou o Readiness Toolkit para suplemento do Office e o VBA para testar seus aplicativos e suplementos do Office para avaliar a compatibilidade com os aplicativos do Microsoft 365 para empresas.
1. No Gerenciador de configurações, eles habilitaram o cache de par em seus dispositivos clientes, o que ajuda com a capacidade de rede limitada ao implantar em dispositivos cliente em locais remotos. 
1. A contoso definiu dois grupos de implantação como coleções de dispositivos no Gerenciador de configurações: um grupo piloto e um grupo amplo. O grupo piloto, que inclui um pequeno conjunto de dispositivos representativos em toda a organização, foi usado para testes adicionais de aplicativos, suplementos e hardware com o Windows 10 Enterprise e o Microsoft 365 aplicativos para empresas.
1. Eles criaram pacotes de implantação para o Office usando o painel de gerenciamento de cliente do Office e o assistente de instalação do Office 365, que fazem parte do console do Gerenciador de configurações. Eles criaram dois aplicativos Microsoft 365 para pacotes corporativos, um para o grupo piloto no canal de negócios do Semi-Annual (visualização) e um para o grupo amplo no canal do Semi-Annual Enterprise.
2. Cada pacote do Office incluiu pacotes de idiomas em inglês, francês e alemão. Se um dispositivo precisar de um idioma que não foi incluído no pacote do Office, esse pacote de idiomas foi baixado automaticamente da CDN (rede de distribuição de conteúdo) do Office.
3. Eles usaram o recurso interno no pacote do Office para remover automaticamente todas as versões existentes do MSI do Office antes de instalar o Microsoft 365 Apps for enterprise.
4. No Gerenciador de configurações, ele implantou os pacotes do Windows e do Office para pontos de distribuição em sua rede. Em seguida, eles executaram as sequências de tarefas de implantação do Configuration Manager para implantar o pacote piloto do Microsoft 365 aplicativos para Enterprise no grupo piloto.
5. Depois de solucionar os problemas de compatibilidade com o grupo piloto, a contoso executou as sequências de tarefas para implantar o pacote Microsoft 365 Apps for Enterprise para o grupo amplo.

Como a Contoso decidiu atualizar os dispositivos automaticamente a partir da nuvem, não havia necessidade de gerenciar o processo no Gerenciador de Configurações.  Seus dispositivos são atualizados automaticamente a partir da nuvem com base no canal de atualização que foi definido na implantação inicial.

Aqui está a contoso Microsoft 365 aplicativos para instalação corporativa e arquitetura de implantação de atualizações contínuas.

![A infraestrutura de implantação da Contoso para o Microsoft 365 aplicativos para empresas](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-mdm.md) como a Contoso está usando o Microsoft Intune no Microsoft 365 for Enterprise para gerenciar seus dispositivos e os aplicativos que eles executam em toda a organização.

## <a name="see-also"></a>Confira também

[Microsoft 365 Apps para empresas](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
