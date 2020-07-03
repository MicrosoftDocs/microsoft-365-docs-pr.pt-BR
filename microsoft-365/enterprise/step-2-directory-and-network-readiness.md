---
title: 'Etapa 2: Diretório e preparação de rede'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Aprenda a avaliar a preparação de diretórios e da rede no ambiente.
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679009"
---
# <a name="step-2-directory-and-network-readiness"></a>Etapa 2: Diretório e preparação de rede

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Etapa 2: diretório e preparação de rede</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Diretório e Preparação de Rede é a segunda etapa em nosso processo de implantação recomendado, enfocando o Azure Active Directory e a otimização da rede. Para ver o processo completo de implantação do desktop, visite o [Centro de Implantação do Computador](https://aka.ms/HowToShift).
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

Neste artigo, exploraremos as ferramentas e as opções para preparar seus serviços de diretório, e as permissões de usuário e dispositivos, prontas para implantação no Windows 10 e nos Aplicativos do Microsoft 365 para empresas.

## <a name="adding-azure-active-directory"></a>Adição do Azure Active Directory

Se sua organização usa o Office 365, o Exchange Online, o Microsoft Intune ou outros serviços do Microsoft Online, a boa notícia é que você já está usando o Azure Active Directory. Caso já esteja usando, apenas verifique se os usuários aos quais você está direcionando a implantação de desktop estão em seu Azure Active Directory e se as licenças foram atribuídas.

Se atualmente não estiver usando o Azure Active Directory, há [vários recursos](https://docs.microsoft.com/azure/active-directory/) para ajudá-lo a configurá-lo. É possível que você esteja habilitado a receber assistência personalizada por meio do Microsoft FastTrack, como parte da licença. Saiba mais sobre o Microsoft FastTrack [aqui](https://fasttrack.microsoft.com).

Depois que o Azure Active Directory estiver configurado, os usuários poderão entrar e ativar os Aplicativos do Microsoft 365 para empresas, e você poderá usar a implantação do Microsoft Intune ou do Windows Autopilot para implantação automatizada de aplicativos e políticas.

## <a name="network-readiness"></a>Preparação de rede

É necessário considerar os requisitos de largura de banda ao planejar suas implantações. Há três componentes principais em uma implantação que terão impacto na rede: geração de imagens de computador, atualizações de software e personalizações de usuário. Entre eles, isso pode significar mais de 20 GB por computador para a migração inicial e geralmente 1 GB ou mais mensal por computador para se manter atualizado.

Vamos começar explorando os requisitos de cada um desses três componentes principais:

### <a name="pc-imaging"></a>Geração de imagens de computador

Para imagens do Windows sem personalização, é preciso planejar normalmente 3GB por computador, enquanto para imagens personalizadas com aplicativos é necessário permitir 6GB ou mais. Também convém considerar pacotes de driver, que podem ser algumas centenas de MB por computador até 1 GB, algumas vezes.

### <a name="software-updates"></a>Atualizações de software

Será necessário planejar a largura de banda de rede para as atualizações de software. O Windows 10 e os Aplicativos do Microsoft 365 para empresas usam um novo modelo de serviço com atualizações mensais e semestrais. Se você estiver começando a usar esse modelo, saiba mais sobre como ele funciona [aqui](https://docs.microsoft.com/windows/deployment/update/waas-overview).

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>Personalização do usuário

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>Limitar a largura de banda

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[Sobre o BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Se você usar o Microsoft Endpoint Configuration Manager (Branch Atual), também poderá configurar os Pontos de Distribuição prontos para BITS ou habilitar o multicast com WDS.

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

Felizmente, há novas ferramentas para facilitar o gerenciamento do efeito na rede de uma grande implantação de área de trabalho, incluindo LEDBAT para otimizar a largura de banda disponível e as opções ponto a ponto (P2P) para mover o tráfego de implantação para longe do centro da rede e para fora do perímetro

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Busca de largura de banda

O Transporte em Segundo Plano com Latência Otimizada (LEDBAT), com suporte no Windows Server 2019 e no Microsoft Endpoint Configuration Manager (Branch Atual), foi projetado para otimizar o tráfego de rede para os clientes do Windows.

[10 principais recursos de rede no Windows Server 2019: \#9 LEDBAT – Transporte em segundo plano com latência otimizada](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Opções ponto a ponto

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

**Cache Par** Os clientes com suporte no Configuration Manager também podem utilizar o Cache Par. Isso permite que os computadores disponibilizados de maneira confiável na rede hospedem a origem para a distribuição de conteúdo. Não habilite isso em todos os computadores, mas apenas nos dispositivos com conexões de rede confiáveis como hosts (por exemplo, desktop, minitorre ou PCs em torre). O Cache Par pode funcionar até para tarefas de implantação em execução em fases do Windows PE durante a instalação.

Observação: BranchCache e cache de mesmo nível são complementares e podem funcionar juntos no mesmo ambiente.

[BranchCache versus Cache Par](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Otimização de Entrega** A Otimização de Entrega é outra tecnologia de cache ponto a ponto, que fornece controles baseados na rede para as implantações. A Otimização de Entrega do Windows 10 serve para atualizar aplicativos UWP internos, para instalar aplicativos da Microsoft Store e para as atualizações de software que usam atualizações expressas. Ela está disponível desde as versões mais antigas do Windows 10, mas foi recentemente integrada ao Microsoft Endpoint Configuration Manager (Branch Atual). Desde a versão 1803 do Windows 10, as novas opções de configuração permitem definir, de maneira independente, os limites de largura de banda para atualizações em segundo plano e trabalhos de primeiro plano, como a instalação de um aplicativo da loja. A Otimização de Entrega do Windows agora também dá suporte aos Aplicativos do Microsoft 365 para empresas durante as atualizações de cliente, disponíveis em todos os canais de atualização de cliente. O suporte para a Otimização de Entrega do Windows durante a instalação inicial de cliente será disponibilizada em breve.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Considerações adicionais sobre os Aplicativos do Microsoft 365 para empresas**

Além de aprimorar a Otimização de Entrega, veja a seguir três itens que ajudarão a reduzir a carga de rede em razão de implantações dos Aplicativos do Microsoft 365 para empresas.

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[Baixando atualizações dos Aplicativos do Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Arquivos de Dados do Outlook** O Outlook geralmente está configurado para armazenar localmente em cache toda a caixa de correio do usuário para uso offline. Em qualquer implantação do Windows, exceto em uma atualização in-loco, são necessários os Arquivos de dados do Outlook dos usuários para recriá-los por conta própria após a atualização. Este é um processo automatizado, mas com limites de caixas de correio do Outlook normalmente definidos em até 100 GB, um novo armazenamento local em cache de toda a caixa de correio de todos os usuários indica muita transferência de dados. Para reduzir a carga da rede, considere a possibilidade de usar a Política de Grupo para reduzir a configuração de “Email para manter offline”. Nos Aplicativos do Microsoft 365 para empresas ou Office 2016, o valor padrão do Outlook está definido como 12 meses. Para reduzir o impacto na rede, considere configurar o cache offline para ter uma duração entre 1 a 6 meses. Alterar essa configuração não afetará o tamanho da caixa de correio online, e toda a caixa de correio ainda pode ser pesquisada pelo Outlook quando estiver online.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**Arquivos sob Demanda do OneDrive e Mudança de Pastas Conhecidas** O OneDrive é uma ótima maneira de sincronizar e proteger os arquivos do usuário de computadores e de outros dispositivos na nuvem. Com a Mudança de Pastas Conhecidas, você pode impor a sincronização de arquivos da Área de trabalho do usuário, de Documentos e das Pastas de imagens para o OneDrive, tornando esses arquivos disponíveis ao entrar em um novo dispositivo ou em um computador com imagem refeita. Entretanto, lembre-se de que, devido ao tamanho absoluto e ao número de arquivos mantidos na Área de trabalho, nas pastas Documentos e Imagens, é importante planejar bem a implementação das políticas que habilitam e impõem o OneDrive em seus computadores. Uma opção é usar os controles de Rede de Política de Grupo para limitar a largura de banda usada pelo serviço de sincronização do OneDrive.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Movimentação de pastas conhecidas da instalação](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[Arquivos do OneDrive sob demanda](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Se ainda não implementou o OneDrive, a mudança do Windows 7 para o Windows 10 é a oportunidade perfeita para habilitar o OneDrive, que se integra facilmente aos Aplicativos do Microsoft 365 para empresas. Considere iniciar essa implementação enquanto estiver trabalhando na preparação dos aplicativos e dispositivos. Isso iniciará a sincronização de arquivos antes de começar a mover as imagens do Windows e a implantar os aplicativos em sua rede.

## <a name="next-step"></a>Próxima etapa 

## <a name="step-3-office-and-lob-app-delivery"></a>[Etapa 3: Entrega de aplicativos do Office e LOB](https://aka.ms/mdd3)

## <a name="previous-step"></a>Etapa anterior:

## <a name="step-1-device-and-app-readiness"></a>[Etapa 1: Preparação de dispositivos e aplicativos](https://aka.ms/mdd1)

## <a name="feedback"></a>Comentários

We'd love to hear your thoughts. Choose the type you'd like to provide:

Comentários sobre o produto. Entre para fazer comentários sobre a documentação

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
