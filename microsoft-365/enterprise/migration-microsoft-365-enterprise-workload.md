---
title: Migração para o Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Percorra o processo de migração de versões do Microsoft Office, servidores do Office e Windows para o Microsoft 365 Enterprise em toda a organização.
ms.openlocfilehash: f82e65cdff674884466fe70a299250c92f356186
ms.sourcegitcommit: 86dba00cd786ac8ea761cdfcd85dfbd33e64d088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297871"
---
# <a name="migration-to-microsoft-365-enterprise"></a>Migração para o Microsoft 365 Enterprise

A maioria das organizações empresariais tem um ambiente heterogêneo com várias versões de sistemas operacionais, software cliente e software de servidor. O Microsoft 365 Enterprise inclui as versões mais seguras desses componentes principais de sua infraestrutura de TI com recursos de produtividade projetados para aproveitar as vantagens das tecnologias de nuvem.

Para maximizar o valor comercial do conjunto integrado de produtos do Microsoft 365 Enterprise, comece a planejar e implementar uma estratégia para migrar versões de:

- Cliente do Office instalado em seus computadores para o Office 365 ProPlus
- Servidores do Office instalados em seus servidores para seus serviços equivalentes no Office 365
- Windows 7 e Windows 8.1 em dispositivos Windows 10 Enterprise

>[!Note]
>O Windows 7 atinge o fim do suporte no dia 14 de janeiro de 2020. Para saber mais, clique [aqui](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

Realizar todas essas migrações ao longo do tempo aproxima a organização do [local de trabalho moderno](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), um ambiente seguro e integrado que desbloqueia o trabalho em equipe e a criatividade em sua organização, tudo possibilitado e habilitado pelo Microsoft 365 Enterprise. 

Para saber sobre migração de usuários e dados para específicas cargas de trabalho do Office 365:

- Caixas de correio do usuário do Exchange Server para o Exchange Online, consulte a [carga de trabalho do Exchange Online](exchangeonline-workload.md).
- Dados do SharePoint, do SharePoint Server para o SharePoint Online, consulte a [carga de trabalho do SharePoint Online](sharepoint-online-onedrive-workload.md).
- Skype for Business Online para Microsoft Teams, consulte a [carga de trabalho do Microsoft Teams](teams-workload.md).

## <a name="migration-for-microsoft-office-client-products"></a>Migração para produtos cliente do Microsoft Office

Em muitas organizações grandes e pequenas, você pode usar uma combinação de versões mais antigas dos produtos clientes do Office, como Word, Excel e PowerPoint. Essas versões mais antigas:

- Podem ser [atualizadas](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) com as atualizações de segurança mais recentes e correções de suporte, mas o processo às vezes é manual e pode não ser dimensionado na sua organização.
- Não estão otimizadas para aproveitar as tecnologias de nuvem da Microsoft e ajudar você a transformar seus negócios digitalmente.
 
O Microsoft 365 Enterprise inclui o Office 365 ProPlus, uma versão dos produtos cliente do Office que está disponível com uma licença do Microsoft 365 Enterprise e é instalada e atualizada a partir da nuvem da Microsoft. Confira [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) para obter mais informações.

### <a name="office-2007"></a>Office 2007

Para versões do Office na versão Office 2007, o fim do suporte já passou. Confira [Roteiro de fim do suporte do Office 2007](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) para obter mais informações.

Em vez de atualizar seus computadores que executam o Office 2007 com o Office 2010, o Office 2013 ou o Office 2016, considere:

1. Como adquirir e atribuir uma licença do Microsoft 365 aos usuários.
2. Como desinstalar o Office 2007 em seus computadores.
3. Como instalar o Office 365 ProPlus, individualmente ou em conjunto com uma distribuição de TI. Para mais informações, confira [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md).

O Office 365 ProPlus instala atualizações automaticamente e pode aproveitar os serviços baseados em nuvem no Office 365 para aumentar a segurança e a produtividade.

### <a name="office-2010"></a>Office 2010

Para versões do Office na versão Office 2010, o fim do suporte será 13 de outubro de 2020. Para saber mais, confira [Roteiro de fim do suporte do Office 2010](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).

Em vez de atualizar seus computadores que executam o Office 2010 com o Office 2013 ou o Office 2016 (cujas atualizações devem ser feitas manualmente), considere: 

1. Como adquirir e atribuir uma licença do Microsoft 365 aos usuários.
2. Como desinstalar o Office 2010 em seus computadores.
3. Como instalar o Office 365 ProPlus, individualmente ou em conjunto com uma distribuição de TI. Para mais informações, confira [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md).

O Office 365 ProPlus instala atualizações automaticamente e pode aproveitar os serviços baseados em nuvem no Office 365 para aumentar a segurança e a produtividade.

### <a name="office-2013-and-office-2016"></a>Office 2013 e Office 2016

O roteiro de fim do suporte para as versões do Office 2013 e Office 2016 do Office ainda não foi determinado. No entanto, como no Office 2010, você ainda deve [instalar as atualizações](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), que podem não ser bem dimensionadas dependendo do tamanho da sua organização. Em vez de continuar atualizando seus computadores com as atualizações mais recentes do Office 2013 ou do Office 2016 ou atualizar seus computadores do Office 2013 para o Office 2016, considere:

1. Como adquirir e atribuir uma licença do Microsoft 365 aos usuários.
2. Como desinstalar o Office 2013 ou o Office 2016 em seus computadores.
3. Como instalar o Office 365 ProPlus, individualmente ou em conjunto com uma distribuição de TI. Para mais informações, confira [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md).

O Office 365 ProPlus instala atualizações automaticamente e pode aproveitar os serviços baseados em nuvem no Office 365 para aumentar a segurança e a produtividade.

## <a name="migration-for-microsoft-office-server-products"></a>Migração para produtos de servidor do Microsoft Office

Em muitas organizações grandes e pequenas, você pode usar uma combinação de versões mais antigas dos produtos clientes do Office Server, como Exchange Server e SharePoint Server. Essas versões mais antigas:

- Devem ser atualizadas com as últimas atualizações de segurança e correções de suporte. Em alguns casos, essas atualizações são liberadas mensalmente.
- Não estão otimizadas para aproveitar as tecnologias de nuvem da Microsoft e ajudar você a transformar seus negócios digitalmente.
- Não incluem novos aplicativos de produtividade, como o Microsoft Teams.
- Não incluem os recursos de segurança mais recentes, como a Proteção Avançada contra Ameaças do Exchange.

O Microsoft 365 Enterprise inclui o Office 365, que inclui versões baseadas em nuvem de serviços de servidor do Office que usam algumas das mesmas ferramentas que as versões locais do software do servidor do Office, como navegadores da Web e o cliente Outlook. Esses serviços são continuamente atualizados sem envolver a TI, poupando o tempo necessário para manter e atualizar os servidores locais. Esses serviços também possuem aprimoramentos que não estão presentes no software de servidor do Office. 

### <a name="office-server-2007"></a>Office Server 2007

Para produtos de servidor na versão Office 2007, o fim do suporte já passou. Confira os artigos a seguir para saber mais:

- [Roteiro de fim do suporte do Exchange 2007](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [Roteiro de fim do suporte do SharePoint Server 2007](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Roteiro de fim do suporte do Project Server 2007](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Roteiro de fim do suporte do Office Communications Server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [Roteiro de fim do suporte do PerformancePoint Server 2007](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

Em vez de atualizar seus produtos de servidor na versão Office 2007 com produtos de servidor nas versões Office 2010, Office 2013 ou Office 2016, considere:

1. Migrar os dados em seus servidores do Office 2007 para o Office 365. Para ajudar com isso, contrate um parceiro da Microsoft.
2. Implantar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando não houver mais a necessidade de servidores locais executando produtos de servidor do Office 2007, desative-os.

### <a name="office-server-2010"></a>Office Server 2010

Para produtos de servidor na versão Office 2010, o fim do suporte foi determinado para o seguinte:

- [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

Em vez de atualizar esses produtos de servidor na versão Office 2010 com produtos de servidor nas versões Office 2013 ou Office 2016, considere:

1. Migrar os dados em seus servidores do Office 2010 para o Office 365. Para ajudar com isso, confira [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou contrate um parceiro da Microsoft.
2. Implantar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando não houver mais a necessidade de servidores locais executando produtos de servidor do Office 2010, desative-os.

### <a name="office-server-2013"></a>Office Server 2013

Para produtos de servidor na versão Office 2013, o fim do suporte não foi determinado. Em vez de atualizar seus produtos de servidor na versão Office 2013 com produtos de servidor na versão Office 2016, considere:

1. Migrar os dados em seus servidores do Office 2013 para o Office 365. Para ajudar com isso, confira [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou contrate um parceiro da Microsoft.
2. Implantar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando não houver mais a necessidade de servidores locais executando produtos de servidor do Office 2013, desative-os.

### <a name="office-server-2016"></a>Office Server 2016

Para produtos de servidor na versão Office 2016, o fim do suporte não foi determinado. Para aproveitar o serviço baseado na nuvem e os aprimoramentos para transformar digitalmente seus negócios, considere:

1. Migrar os dados em seus servidores do Office 2016 para o Office 365. Para ajudar com isso, confira [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou contrate um parceiro da Microsoft.
2. Implantar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando não houver mais a necessidade de servidores locais executando produtos de servidor do Office 2016, desative-os.

## <a name="migration-for-microsoft-windows"></a>Migração para o Microsoft Windows

Para migrar seus dispositivos que executam o Windows 7 ou o Windows 8.1, você pode executar uma [atualização in-loco](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade). 

Para outros métodos, confira [Cenários de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Você também pode [Planejar a implantação do Windows 10](https://aka.ms/planforwin10deployment) por conta própria.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Veja como os especialistas em TI da Microsoft migraram a empresa para o Microsoft 365 Enterprise com estes recursos: 

- [Implantar e atualizar o Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [A Microsoft migra 150 mil caixas de correio para o Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint para a nuvem: saiba como a Microsoft realizou a própria migração](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Implantar o Windows 10 na Microsoft como uma atualização in-loco](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implantação do Windows 10: dicas e truques da TI da Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)

## <a name="transition-your-entire-organization"></a>Transição para toda a organização

Para ter uma ideia melhor de como migrar toda a organização para o Microsoft 365 Enterprise, baixe o [pôster de transição](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transitionorgtom365.pdf).

![](./media/deploy-microsoft-365-enterprise/TransitionOrgToM365.png)

Esse pôster de duas páginas é uma maneira rápida de fazer o inventário da infraestrutura existente e obter diretrizes para migrar para o produto ou serviço correspondente no Microsoft 365 Enterprise. Ele inclui os produtos neste artigo e outros elementos de infraestrutura e segurança, como gerenciamento de dispositivo, identidade, proteção contra ameaças e informações sobre elas.

Você pode imprimir esse pôster em formato de carta, oficial ou de tabloide (11 x 17).

## <a name="result"></a>Resultado

A organização migrou versões anteriores do Microsoft Office, de servidores do Office e do Windows para o Microsoft 365 Enterprise.
