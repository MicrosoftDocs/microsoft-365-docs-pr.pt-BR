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
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907669"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implantação do Microsoft 365 Apps for enterprise para Contoso

A Contoso atualizou seus computadores para Windows 10 Enterprise e Microsoft 365 Apps para Grandes Empresas para habilitar uma colaboração mais eficaz, melhor segurança e uma experiência de área de trabalho mais moderna. Depois de avaliar suas necessidades de infraestrutura e negócios, a Contoso identificou esses requisitos principais para a implantação:

- Todos os PCs devem ser executados Microsoft 365 Apps para Grandes Empresas.
- A implantação deve usar ferramentas de gerenciamento e infraestrutura existentes quando possível.
- A implantação deve dar suporte a vários idiomas e arquiteturas existentes nos dispositivos dos usuários.
- Os PCs devem se manter atualizados e seguros com custos administrativos de IT mínimos e impacto mínimo para os usuários.

## <a name="deployment-tools"></a>Ferramentas de implantação

Com base em seus requisitos, a Contoso optou por implantar Windows 10 Enterprise e Microsoft 365 Apps para Grandes Empresas por meio do Configuration Manager (Branch Atual). O Configuration Manager é dimensionado para ambientes grandes e fornece controle extensivo sobre instalação, atualizações e configurações. Ele também possui recursos internos para tornar mais fácil e eficiente a implantação e o gerenciamento do Office, incluindo:

- Cache par, que pode ajudar com capacidade de rede limitada ao implantar em dispositivos em locais remotos.
- O Office de Gerenciamento de Cliente, o que facilita a implantação de Office e o monitoramento de atualizações e oferece aos administradores acesso aos recursos mais recentes de implantação e gerenciamento.
- Implantação de pacote de idiomas inteligente, incluindo a implantação automática do mesmo idioma que o sistema operacional.
- Um método totalmente suportado e fácil de usar para remover versões existentes de Office de um cliente durante a implantação.

Além do Configuration Manager, a Contoso usou o Toolkit de Preparação para os Office e o VBA , uma ferramenta gratuita da Microsoft, para avaliar problemas de compatibilidade com suas macros e complementos do [Office.](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)

## <a name="managing-deployment-and-updates"></a>Gerenciamento de implantação e atualizações

Microsoft 365 Apps para Grandes Empresas tem um novo modelo de versão: Office como um serviço. O modelo de serviço torna mais fácil manter-se atualizado com os novos recursos. Mas geralmente exige que os departamentos de IT alterem a forma como implantam e testam novas versões. Para minimizar problemas de compatibilidade e garantir que seus computadores fiquem atualizados, a Contoso implantou Windows e Office em dois estágios:

- Primeiro, eles implantaram Microsoft 365 Apps para Grandes Empresas em um pequeno conjunto de dispositivos representativos em toda a organização. Esse grupo piloto foi usado para testar aplicativos, complementos e hardware com Microsoft 365 Apps para Grandes Empresas.
- Quatro meses depois disso, após resolver todos os problemas graves com aplicativos, suplementos e hardware no grupo piloto, a Contoso implantou o Microsoft 365 Apps for enterprise no restante dos dispositivos da organização (o grupo amplo).

Em vez de gerenciar atualizações para Office usando o Configuration Manager, a Contoso habilita as atualizações automáticas da nuvem. As atualizações baseadas em nuvem reduzem a sobrecarga administrativa enquanto garantem que os dispositivos permaneçam atualizados.

A Contoso seguiu a mesma abordagem de dois estágios para atualizações de recursos usadas para implantar o Office: os dispositivos no grupo piloto receberam atualizações de recursos quatro meses antes dos dispositivos no restante da organização (o grupo amplo). Para habilitar isso no Office, a Contoso usou dois [canais de atualização](/DeployOffice/overview-update-channels) recomendados:

- Canal Empresarial Semestral (Visualização) para atualizações do grupo piloto
- Semi-Annual Enterprise Canal para atualizações para o grupo amplo

Como o Canal Empresarial Semestral (Visualização) lança uma versão do Microsoft 365 Apps para Grandes Empresas quatro meses antes do Canal Empresarial Semestral, a Contoso tem tempo para validar as atualizações sem precisar gerenciá-las.

## <a name="deployment-process"></a>Processo de implantação

Para concluir a implantação do Office, a Contoso implementou o seguinte processo, que inclui as práticas recomendadas da Microsoft:

1. Antes da implantação, a Contoso usava o Toolkit de preparação para o Office e o VBA para testar seus aplicativos e Office de Office para avaliar sua compatibilidade com o Microsoft 365 Apps para Grandes Empresas.
1. No Configuration Manager, eles habilitaram o cache de pares em seus dispositivos cliente, o que ajuda com a capacidade de rede limitada ao implantar em dispositivos cliente em locais remotos. 
1. A Contoso definiu dois grupos de implantação como coleções de dispositivos no Configuration Manager: um grupo piloto e um grupo amplo. O grupo piloto, que incluía um pequeno conjunto de dispositivos representativos em toda a organização, foi usado para testes adicionais de aplicativos, complementos e hardware com Windows 10 Enterprise e Microsoft 365 Apps para Grandes Empresas.
1. Eles criaram pacotes de implantação para Office usando o painel de Gerenciamento de Cliente Office e o assistente Office 365 Instalador, que fazem parte do console do Configuration Manager. Eles construiram dois Microsoft 365 Apps para Grandes Empresas, um para o grupo piloto no canal Semi-Annual Enterprise (Visualização) e um para o grupo amplo no canal Semi-Annual Enterprise.
2. Cada Office inclui pacotes de idioma inglês, francês e alemão. Se um dispositivo exigia um idioma que não estava incluído no pacote Office, esse pacote de idiomas foi baixado automaticamente do Office Rede de Distribuição de Conteúdo (CDN).
3. Eles usaram o recurso interno no pacote do Office para remover automaticamente todas as versões existentes do MSI do Office antes de instalar o Microsoft 365 Apps for enterprise.
4. No Configuration Manager, eles implantaram os pacotes Windows e Office em pontos de distribuição em sua rede. Em seguida, eles fizeram as sequências de tarefas de implantação do Configuration Manager para implantar o pacote Microsoft 365 Apps para Grandes Empresas piloto no grupo piloto.
5. Depois de resolver problemas de compatibilidade com o grupo piloto, a Contoso correu as sequências de tarefas para implantar o pacote Microsoft 365 Apps para Grandes Empresas para o grupo amplo.

Como a Contoso decidiu atualizar os dispositivos automaticamente a partir da nuvem, não havia necessidade de gerenciar o processo no Gerenciador de Configurações.  Seus dispositivos são atualizados automaticamente diretamente da nuvem com base no canal de atualização definido na implantação inicial.

Aqui está a arquitetura de implantação de Microsoft 365 Apps para Grandes Empresas de instalação e atualizações contínuas da Contoso.

![A infraestrutura de implantação da Contoso para Microsoft 365 Apps para Grandes Empresas](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso está [usando Microsoft Intune](contoso-mdm.md) no Microsoft 365 para a empresa gerenciar seus dispositivos e os aplicativos executados em toda a organização.

## <a name="see-also"></a>Confira também

[Microsoft 365 Apps para empresas](/deployoffice/deployment-guide-microsoft-365-apps)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)