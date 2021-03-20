---
title: Roteiro de software de cliente e servidor para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Use este roteiro para configurar o software de cliente e servidor para o Microsoft 365.
ms.openlocfilehash: ee101b3ba148f1075939d56904dc9d2ecf14e1b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905195"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Roteiro de software de cliente e servidor para o Microsoft 365

A maioria das organizações corporativas tem um ambiente heterogêneo que inclui várias versões de sistemas operacionais, software cliente e software de servidor. O Microsoft 365 para Enterprise inclui as versões mais seguras dos principais componentes da infraestrutura de TI. Ele também inclui recursos de produtividade projetados para tirar proveito das tecnologias de nuvem.

Para maximizar o valor comercial do pacote integrado de produtos do Microsoft 365 for Enterprise, comece a planejar e implementar uma estratégia para migrar versões de:

- O cliente do Office instalado em seus computadores para o Microsoft 365 Apps para empresas.
- Os servidores do Office instalados em seus servidores para seus serviços equivalentes no Microsoft 365.
- Windows 7 e Windows 8.1 em seus dispositivos para o Windows 10 Enterprise.

>[!Note]
>O suporte para o Windows 7 terminou em *14 de janeiro de 2020*. Para obter mais informações, consulte os detalhes do fim [do suporte.](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)
>

À medida que você realiza essas migrações ao longo do tempo, sua organização se aproxima da visão do [local de trabalho moderno.](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/) Esse ambiente seguro e integrado pode ajudá-lo a desbloquear o trabalho em equipe e a criatividade em sua organização. O Microsoft 365 para Enterprise habilita e capacita você ao longo do caminho.

## <a name="migration-for-office-client-products"></a>Migração para produtos cliente do Office

Organizações grandes e pequenas geralmente usam uma combinação de versões mais antigas de produtos cliente do Office, como Word, Excel e PowerPoint. Estas versões mais antigas:

- Pode ser [atualizado com](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) as atualizações de segurança mais recentes e correções de suporte. Mas o processo às vezes é manual e pode não ser dimensionado em toda a sua organização.
- Não são otimizados para usar as tecnologias de nuvem da Microsoft que ajudam você a transformar digitalmente sua empresa.
- Não forneça os recursos mais recentes.

O Microsoft 365 para Empresas inclui o Microsoft 365 Apps para empresas. Esta versão dos produtos cliente do Office está disponível com uma licença do Microsoft 365 para Enterprise. Ele é instalado e atualizado a partir da nuvem da Microsoft. O Aplicativos do Microsoft 365 para empresas inclui atualizações de segurança e os recursos mais recentes. Para obter mais informações, consulte [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).

### <a name="office-2007"></a>Office 2007

Para versões do Office na versão do Office 2007, o fim do suporte já passou. Para obter mais informações, consulte Roteiro de fim de suporte do [Office 2007](/deployoffice/office-2007-end-support-roadmap).

Em vez de atualizar seus computadores que executem o Office 2007 para Office 2010, Office 2013 ou Office 2016, considere seguir as seguintes etapas:

1. Obter e atribuir uma licença do Microsoft 365 para seus usuários.
2. Desinstale o Office 2007 em seus computadores.
3. Instale o Microsoft 365 Apps para empresas, individualmente ou durante uma implantação de IT. Para obter mais informações, consulte [Guia de implantação para Aplicativos do Microsoft 365.](/deployoffice/deployment-guide-microsoft-365-apps)

O Microsoft 365 Apps para empresas instala atualizações automaticamente. Ele pode aproveitar os serviços baseados em nuvem para aumentar a segurança e a produtividade.

### <a name="office-2010"></a>Office 2010

Para versões do Office no lançamento do Office 2010, o suporte terminou em 13 de outubro de *2020*. Para obter mais informações, consulte Roteiro de fim de suporte do [Office 2010.](/deployoffice/office-2010-end-support-roadmap)

Você pode considerar atualizar seus computadores que executem o Office 2010 para o Office 2013 ou o Office 2016. No entanto, ambas as versões devem ser atualizadas manualmente. Portanto, considere seguir as etapas a seguir:

1. Obter e atribuir uma licença do Microsoft 365 para seus usuários.
2. Desinstale o Office 2010 em seus computadores.
3. Instale o Microsoft 365 Apps para empresas, individualmente ou durante uma implantação de IT. Para obter mais informações, consulte [Guia de implantação para Aplicativos do Microsoft 365.](/deployoffice/deployment-guide-microsoft-365-apps)

O Microsoft 365 Apps para empresas instala automaticamente atualizações de segurança e novas atualizações de recursos. Ele pode aproveitar os serviços baseados em nuvem no Microsoft 365 para aumentar a segurança e a produtividade.

### <a name="office-2013-and-office-2016"></a>Office 2013 e Office 2016

Consulte o [roteiro de fim de suporte para Office 2013](/lifecycle/products/microsoft-office-2013). O fim do suporte para o Office 2016 ainda não foi determinado. Nessas versões, como o Office 2010, você ainda deve [instalar atualizações de segurança](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5). Essa tarefa pode não ser dimensionar bem, dependendo do tamanho da sua organização.

Em vez de manter seus computadores atualizados com as atualizações de segurança mais recentes para o Office 2013 ou o Office 2016, ou atualizar seus computadores do Office 2013 para o Office 2016, considere as seguintes etapas:

1. Obter e atribuir uma licença do Microsoft 365 para seus usuários.
2. Desinstale o Office 2013 ou o Office 2016 em seus computadores.
3. Instale o Microsoft 365 Apps para empresas, individualmente ou durante uma implantação de IT. Para obter mais informações, consulte [Guia de implantação para Aplicativos do Microsoft 365.](/deployoffice/deployment-guide-microsoft-365-apps)

O Microsoft 365 Apps for enterprise instala atualizações de segurança e novas atualizações de recursos automaticamente. Ele pode aproveitar os serviços baseados em nuvem no Microsoft 365 para aumentar a segurança e a produtividade.

## <a name="migration-for-office-server-products"></a>Migração para produtos de servidor do Office

As organizações grandes e pequenas geralmente usam uma combinação de versões mais antigas dos produtos do servidor do Office, como o Exchange Server e o SharePoint Server. Estas versões mais antigas:

- Deve ser atualizado com as atualizações de segurança mais recentes e correções de suporte. Em alguns casos, essas atualizações são lançadas mensalmente.
- Não são otimizados para usar as tecnologias de nuvem da Microsoft que ajudam você a transformar digitalmente sua empresa.
- Não inclua novos aplicativos de produtividade, como o Microsoft Teams.
- Não inclua os recursos de segurança mais recentes, como o Exchange e o Defender para Office 365.

O Microsoft 365 para Enterprise inclui versões baseadas em nuvem de serviços de servidor do Office que usam algumas das mesmas ferramentas que as versões locais do software do servidor do Office, como navegadores da Web e o cliente do Outlook. Esses serviços são atualizados automaticamente para segurança. Assim, sua equipe de IT economiza o tempo necessário para manter e atualizar servidores locais. Esses serviços também oferecem novos aprimoramentos de recursos que não estão presentes no software do servidor do Office.

Use os seguintes recursos para obter informações sobre como migrar usuários e dados para cargas de trabalho específicas do Microsoft 365:

- [Mover caixas de correio de caixas de correio locais Exchange Server para o Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrar dados do SharePoint Do SharePoint Server para o SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar o Skype for Business Online para o Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a>Produtos de servidor do Office 2007

Para produtos de servidor na versão do Office 2007, o fim do suporte já passou. Confira estes artigos para obter detalhes:

- [Roteiro de fim de suporte do Exchange 2007](exchange-2007-end-of-support.md)
- [Roteiro de fim de suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
- [Roteiro de fim de suporte do Project Server 2007](project-server-2007-end-of-support.md)
- [Roteiro de fim de suporte do Office Communications Server](/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server roteiro de fim de suporte 2007](pps-2007-end-of-support.md)

Em vez de atualizar seus produtos de servidor na versão do Office 2007 com produtos de servidor nas versões para Office 2010, Office 2013 ou Office 2016, considere seguir as seguintes etapas:

1. Migre os dados em seus servidores do Office 2007 para o Microsoft 365. Para obter mais informações ou ajuda, contratem um parceiro da Microsoft.
2. Lançar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando você não precisar mais dos servidores locais que executam produtos de servidor do Office 2007, descomissione-os.

### <a name="office-2010-server-products"></a>Produtos de servidor do Office 2010

O suporte [para Exchange Server 2010](exchange-2010-end-of-support.md) terminou em 13 de outubro de *2020*.

O fim do suporte ao [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) será em *13 de abrir de 2021*.

Em vez de atualizar esses produtos de servidor na versão do Office 2010 com produtos de servidor nas versões para Office 2013 ou Office 2016, considere as seguintes etapas:

1. Migre os dados em seus servidores do Office 2010 para o Microsoft 365. Para obter mais informações, consulte [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou hire a Microsoft partner.
2. Lançar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando você não precisar mais dos servidores locais que executam produtos de servidor do Office 2010, descomissione-os.

### <a name="office-2013-server-products"></a>Produtos de servidor do Office 2013

Para produtos de servidor na versão do Office 2013, o fim do suporte não foi determinado. Em vez de atualizar seus produtos de servidor na versão do Office 2013 com produtos de servidor na versão do Office 2016, considere seguir as seguintes etapas:

1. Migre os dados em seus servidores do Office 2013 para o Microsoft 365. Para obter mais informações, consulte [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou hire a Microsoft partner.
2. Lançar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando você não precisar mais dos servidores locais que executam produtos de servidor do Office 2013, descomissione-os.

### <a name="office-2016-server-products"></a>Produtos de servidor do Office 2016

Para produtos de servidor na versão do Office 2016, o fim do suporte não foi determinado. Para aproveitar os aprimoramentos e serviços baseados em nuvem para transformar digitalmente sua empresa, considere as seguintes etapas:

1. Migre os dados em seus servidores do Office 2016 para o Microsoft 365. Para obter mais informações, consulte [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) ou hire a Microsoft partner.
2. Lançar a nova funcionalidade e os processos de trabalho para seus usuários.
3. Quando você não precisar mais dos servidores locais que executam produtos de servidor do Office 2016, descomissione-os.

## <a name="migration-for-windows-7-and-81"></a>Migração para Windows 7 e 8.1

O suporte terminou para o Windows 7 em *14 de janeiro de 2020*. Para migrar seus dispositivos que executem o Windows 7 ou o Windows 8.1, você pode fazer uma atualização in-locar.

Para métodos adicionais, confira [Cenários de implantação do Windows 10](/windows/deployment/windows-10-deployment-scenarios). Você também pode [planejar a implantação do Windows 10](/windows/deployment/planning/) por conta própria.

## <a name="office-2010-clients-and-servers-and-windows-7"></a>Clientes e servidores do Office 2010 e Windows 7

Veja um resumo visual das opções de atualização, migração e movimentação para nuvem para clientes e servidores do Office 2010 e Windows 7:

[![Imagem mostrando as opções para o fim do suporte para clientes e servidores do Office 2010 e Windows 7.](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz de uma página é uma maneira rápida de entender os caminhos que você pode seguir para gerenciar o fim do suporte para produtos de cliente e servidor do Office 2010 e o Windows 7. Os caminhos preferenciais são suportados no Microsoft 365 para Empresas.

Você pode [baixar esse cartaz e](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) imprimi-lo em tamanho de carta, tamanho legal ou tabloide (11 x 17).

## <a name="transition-your-entire-organization"></a>Transição para toda a organização

Para obter uma imagem melhor de como mover toda a organização para os produtos e serviços no Microsoft 365 para Empresas, baixe este cartaz de transição:

[![Imagem mostrando o cartaz Transição para o Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Esse pôster de duas páginas é uma maneira rápida de fazer o inventário da infraestrutura existente. Use-o para obter orientações para mover para um produto ou serviço no Microsoft 365 para Empresas. Ele mostra produtos do Windows e do Office e outros elementos de infraestrutura e segurança, como gerenciamento de dispositivos, proteção contra identidade e ameaças e proteção de informações e conformidade.

## <a name="how-microsoft-migrated-to-microsoft-365-for-enterprise"></a>Como a Microsoft migrou para o Microsoft 365 para Empresas

Veja como os especialistas em TECNOLOGIA da Microsoft migraram a empresa para o Microsoft 365 para Empresas:

- [Implantando e atualizando aplicativos do Microsoft 365 para empresas](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [A Microsoft migra 150 mil caixas de correio para o Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint para a nuvem: saiba como a Microsoft realizou a própria migração](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Implantar o Windows 10 na Microsoft como uma atualização in-loco](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implantação do Windows 10: dicas e truques da MICROSOFT IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)