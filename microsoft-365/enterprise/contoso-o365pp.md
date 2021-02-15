---
title: Implantação do Microsoft 365 Apps for enterprise para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa o Microsoft Endpoint Configuration Manager para implantar o Microsoft 365 Apps para Grandes Empresas.
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754336"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implantação do Microsoft 365 Apps for enterprise para Contoso

A Contoso atualizou seus computadores para o Windows 10 Enterprise e o Microsoft 365 Apps para empresas para permitir uma colaboração mais eficaz, melhor segurança e uma experiência de área de trabalho mais moderna. Depois que eles avaliaram suas necessidades comerciais e de infraestrutura, a Contoso identificou esses principais requisitos para a implantação:

- Todos os PCs devem executar o Microsoft 365 Apps para empresas.
- A implantação deve usar ferramentas de gerenciamento e infraestrutura existentes quando possível.
- A implantação deve dar suporte a vários idiomas e arquiteturas existentes nos dispositivos dos usuários.
- Os PCs devem se manter atualizados e seguros com custos administrativos mínimos de IT e impacto mínimo para os usuários.

## <a name="deployment-tools"></a>Ferramentas de implantação

Com base em seus requisitos, a Contoso optou por implantar o Windows 10 Enterprise e o Microsoft 365 Apps para empresas por meio do Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalação, atualizações e configurações. Ele também tem recursos integrados para tornar mais fácil e eficiente implantar e gerenciar o Office, incluindo:

- Cache par, que pode ajudar com capacidade de rede limitada ao implantar em dispositivos em locais remotos.
- O painel Gerenciamento de Clientes do Office, que facilita a implantação do Office e o monitoramento de atualizações e dá aos administradores acesso aos recursos mais recentes de implantação e gerenciamento.
- Implantação inteligente de pacote de idiomas, incluindo a implantação automática do mesmo idioma que o sistema operacional.
- Um método totalmente suportado e fácil de usar para remover versões existentes do Office de um cliente durante a implantação.

Além do Configuration Manager, a Contoso usou o [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)para os complementos do Office e o VBA , uma ferramenta gratuita da Microsoft, para avaliar problemas de compatibilidade com suas macros e complementos do Office.

## <a name="managing-deployment-and-updates"></a>Gerenciando implantação e atualizações

O Microsoft 365 Apps para empresas tem um novo modelo de lançamento: Office como serviço. O modelo de serviço facilita a se manter atualizado com os novos recursos. Mas geralmente exige que os departamentos de IT alterem a forma como implantam e testam novas versões. Para minimizar os problemas de compatibilidade e garantir que seus computadores permaneçam atualizados, a Contoso implantou o Windows e o Office em duas etapas:

- Primeiro, eles implantaram o Microsoft 365 Apps para empresas em um pequeno conjunto de dispositivos representativos em toda a organização. Esse grupo piloto foi usado para testar aplicativos, complementos e hardware com o Microsoft 365 Apps para empresas.
- Quatro meses depois disso, após resolver todos os problemas graves com aplicativos, suplementos e hardware no grupo piloto, a Contoso implantou o Microsoft 365 Apps for enterprise no restante dos dispositivos da organização (o grupo amplo).

Em vez de gerenciar as atualizações do Office usando o Configuration Manager, a Contoso habilitaram as atualizações automáticas da nuvem. As atualizações baseadas em nuvem reduzem a sobrecarga administrativa, garantindo que os dispositivos se mantenha atualizados.

A Contoso seguiu a mesma abordagem em dois estágios para atualizações de recursos usada para implantar o Office: os dispositivos no grupo piloto receberam atualizações de recursos quatro meses antes dos dispositivos no restante da organização (o grupo amplo). Para habilitar isso no Office, a Contoso usou dois [canais de atualização](https://docs.microsoft.com/DeployOffice/overview-update-channels) recomendados:

- Canal Empresarial Semestral (Visualização) para atualizações do grupo piloto
- Semi-Annual Canal Empresarial para atualizações para o grupo amplo

Como o Canal Empresarial Semestral (Visualização) lança uma versão do Microsoft 365 Apps para Grandes Empresas quatro meses antes do Canal Empresarial Semestral, a Contoso tem tempo para validar as atualizações sem precisar gerenciá-las.

## <a name="deployment-process"></a>Processo de implantação

Para concluir a implantação do Office, a Contoso implementou o seguinte processo, que inclui as práticas recomendadas da Microsoft:

1. Antes da implantação, a Contoso usou o Readiness Toolkit para o office add-in e o VBA para testar seus aplicativos e Os Complementos do Office para avaliar sua compatibilidade com o Microsoft 365 Apps para empresas.
1. No Configuration Manager, eles habilitaram o cache par em seus dispositivos cliente, o que ajuda na capacidade limitada da rede ao implantar em dispositivos cliente em locais remotos. 
1. A Contoso definiu dois grupos de implantação como coleções de dispositivos no Configuration Manager: um grupo piloto e um grupo amplo. O grupo piloto, que incluía um pequeno conjunto de dispositivos representativos em toda a organização, foi usado para testes adicionais de aplicativos, complementos e hardware com o Windows 10 Enterprise e o Microsoft 365 Apps para empresas.
1. Eles criaram pacotes de implantação para o Office usando o painel de Gerenciamento de Cliente do Office e o assistente do Instalador do Office 365, que fazem parte do console do Configuration Manager. Eles construiram dois pacotes do Microsoft 365 Apps para empresas, um para o grupo piloto no canal empresarial do Semi-Annual (visualização) e outro para o grupo amplo no canal Semi-Annual Enterprise.
2. Cada pacote do Office incluía pacotes de idiomas em inglês, francês e alemão. Se um dispositivo exigia um idioma que não estava incluído no pacote do Office, esse pacote de idiomas era baixado automaticamente da CDN (Rede de Distribuição de Conteúdo) do Office.
3. Eles usaram o recurso interno no pacote do Office para remover automaticamente todas as versões existentes do MSI do Office antes de instalar o Microsoft 365 Apps for enterprise.
4. No Configuration Manager, eles implantaram os pacotes do Windows e do Office em pontos de distribuição em sua rede. Em seguida, eles fizeram as sequências de tarefas de implantação do Configuration Manager para implantar o pacote piloto do Microsoft 365 Apps para empresas no grupo piloto.
5. Depois de resolver problemas de compatibilidade com o grupo piloto, a Contoso implantou as sequências de tarefas para implantar o pacote microsoft 365 Apps para empresas no grupo amplo.

Como a Contoso decidiu atualizar os dispositivos automaticamente a partir da nuvem, não havia necessidade de gerenciar o processo no Gerenciador de Configurações.  Seus dispositivos são atualizados automaticamente diretamente da nuvem com base no canal de atualização definido na implantação inicial.

Aqui está a arquitetura de implantação de atualizações contínuas e de instalação do Microsoft 365 Apps para empresas da Contoso.

![A infraestrutura de implantação da Contoso para o Microsoft 365 Apps para empresas](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso está usando o [Microsoft Intune](contoso-mdm.md) no Microsoft 365 para empresas para gerenciar seus dispositivos e aplicativos executados em toda a organização.

## <a name="see-also"></a>Confira também

[Microsoft 365 Apps para empresas](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
