---
title: 'Etapa 2: Diretório e preparação de rede'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Aprenda a avaliar a preparação de diretórios e da rede no ambiente.
ms.openlocfilehash: e690e99110e647ffc06c9ff7d40b789d8670e571
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864698"
---
# <a name="step-2-directory-and-network-readiness"></a>Etapa 2: Diretório e preparação de rede

Assegure-se de que seu diretório e sua rede estejam configurados e prontos para oferecer suporte à troca para o Windows 10 e o Office 365 ProPlus. Isso exigirá que os serviços do Azure Active Directory estejam estabelecidos para os usuários e que a rede deve ter a capacidade de lidar com o tráfego normal e a movimentação de grandes quantidades de dados em potencial quando os PCs são atualizados e arquivos, configurações e aplicativos do usuário são restaurados.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Etapa 2: Diretório e preparação de rede</strong></p>
<p>Os serviços conectados à nuvem do Office 365 ProPlus e as novas opções de implantação como o Windows Autopilot requerem o Azure Active Directory. Sua rede e conectividade também são áreas importantes para planejar ao mudar imagens, aplicativos, drivers e arquivos relacionados do Windows para seus PCs. Saiba como as novas ferramentas e opções de implantação reduzem e simplificam o tráfego de rede.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Preparação de rede e diretório é a segunda etapa no processo de implantação recomendado que se concentra no Azure Active Directory e na otimização da rede. Para ver o processo completo de implantação, acesse [Centro de implantação do Computador Moderno](https://aka.ms/HowToShift).
>

A preparação de rede e diretório é fundamental para assegurar uma implantação descomplicada do sistema operacional e da área de trabalho. Como em qualquer implantação automatizada, é importante assegurar que seus compartilhamentos de arquivos possam ser acessados, e sua rede precisará ser capaz de comportar a transferência de arquivos grandes, para possivelmente centenas ou até mesmo milhares de PCs por vez.

Com sua migração para o Windows 10 e o Office 365 ProPlus, você agora também precisará assegurar que a identidade baseada em nuvem seja configurada com o Azure Active Directory. Isso é fundamental não apenas para ativar o Office 365 ProPlus, mas também permite que você aproveite soluções de provisionamento modernas como o Windows Autopilot.

Neste artigo, exploraremos as ferramentas e as opções para preparar seus serviços de diretório, e as permissões de usuário e dispositivos, prontas para implantação no Windows 10 e no Office 365 ProPlus.

## <a name="adding-azure-active-directory"></a>Adição do Azure Active Directory

Se sua organização usa o Office 365, o Exchange Online, o Microsoft Intune ou outros serviços do Microsoft Online, a boa notícia é que você já está usando o Azure Active Directory. Caso esteja, será necessário apenas assegurar que os usuários de destino para a implantação da área de trabalho estejam no seu Azure Active Directory e que as licenças tenham sido atribuídas.

Caso não esteja usando o Azure Active Directory no momento, há [diversos recursos](https://docs.microsoft.com/pt-BR/azure/active-directory/) para ajudar a configurá-lo. Você também pode se qualificar para assistência personalizada pelo Microsoft FastTrack, como parte da sua licença do Office 365. Saiba mais sobre o [Microsoft Fastrack](https://fasttrack.microsoft.com).

Depois que o Azure Active Directory estiver configurado, os usuários poderão entrar e ativar os aplicativos do Office 365 ProPlus, e você poderá usar a implantação do Microsoft Intune ou do Windows Autopilot para implantação automatizada de aplicativos e políticas.

## <a name="network-readiness"></a>Preparação de rede

Você deve considerar os requisitos de largura de banda ao planejar suas implantações. Há três componentes principais em uma implantação que terão efeito na sua rede: geração de imagem de computador; atualizações de software; personalização de usuário. Entre eles, isso pode significar um excesso de 20 GB por PC para a migração inicial e, frequentemente, 1 GB ou mais por mês por PC para ficar atualizado.

Vamos começar explorando os requisitos de cada um desses três componentes principais:

### <a name="pc-imaging"></a>Geração de imagens de computador

O gráfico abaixo ajuda a planejar com base no tamanho da imagem. Nas imagens do Windows sem personalização, você deve planejar normalmente 3 GB por PC, ainda que, para as imagens personalizadas com aplicativos, você possa precisar disponibilizar 6 GB ou mais. Também poderá ser necessário considerar pacotes de drivers; isso pode representar algumas centenas de megabytes por PC, às vezes até 1 GB.

### <a name="software-updates"></a>Atualizações de software

Você precisará planejar a largura de banda de atualizações de software. O Windows 10 e o Office 365 ProPlus usam um novo modelo de manutenção que distribui atualizações mensais e semestrais. Caso seja novo nesse modelo, saiba mais sobre [como ele funciona](https://docs.microsoft.com/pt-BR/windows/deployment/update/waas-overview).

O novo modelo de manutenção inclui atualizações de recursos semestrais para o Windows, atualizações de canal semestrais para o Office e atualizações de qualidade mensais. As atualizações de recursos normalmente têm entre 2 e 4 GB, e as atualizações de canal semestrais do Office têm entre 300 e 400 MB por atualização. Então há as atualizações mensais de qualidade. Elas podem ter entre algumas centenas de megabytes e mais de um gigabyte. Isso acontece porque as atualizações mensais são cumulativas, então o tamanho delas aumenta durante o ciclo de vida da manutenção de cada versão do Windows 10. Dito isso, confira as ferramentas que podem reduzir a quantidade de dados que precisam passar pela rede para implementar atualizações. Abordaremos isso em mais detalhes abaixo.

### <a name="user-personalization"></a>Personalização do usuário

O terceiro componente a considerar é a personalização do usuário. Aqui você precisa planejar a largura de banda da rede para acomodar a restauração dos arquivos do usuário, das configurações e dos aplicativos como parte do processo de atualização do PC ou de substituição. Juntos, esses itens frequentemente excedem 20 GB por PC. Para alguns usuários, isso pode passar dos 100 GB.

## <a name="limiting-bandwidth"></a>**Limitar a largura de banda**

Uma maneira de limitar o impacto do tráfego relacionado a documentos na rede é controlar usando a configuração BITS (Background Intelligent Transfer Service, serviço de transferência inteligente em segundo plano) nos clientes. O BITS usa uma ABR (Adaptive Bit Rate, taxa de bits adaptativa) para ajustar a largura de banda disponível para fins de implantação. Isso pode ser configurado nos clientes usando a Política de Grupo.

[Sobre o BITS](https://docs.microsoft.com/pt-BR/windows/desktop/bits/about-bits)

Se usar o System Center Configuration Manager, também poderá configurar os pontos de distribuição prontos para BITS ou habilitar o multicast com WDS.

A limitação de tráfego específico significa que o tráfego de rede normal será menos afetado pelos PCs baixando atualizações e aplicativos. Mas separar um determinado percentual de largura de banda para essas tarefas ajuda que a produtividade não seja afetada pela implantação do Windows ou do Office, e o processo continua em execução conforme necessário. Isso pode piorar o tempo de inatividade relacionado à implantação, impedindo o acesso de usuários aos PCs durante a execução da implantação.

Felizmente, há novas ferramentas para facilitar o gerenciamento do efeito na rede de uma grande implantação de área de trabalho, incluindo LEDBAT para otimizar a largura de banda disponível e as opções ponto a ponto (P2P) para mover o tráfego de implantação para longe do centro da rede e para fora do perímetro

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>**Busca de largura de banda**

O LEDBAT (Low Extra Delay Background Transport, baixo atraso extra de transporte em plano de fundo), com suporte no Windows Server 2019 e no System Center Configuration Manager versão 1806, foi projetado para otimizar o tráfego de rede para os clientes do Windows.

[10 principais recursos de rede no Windows Server 2019: \#9 LEDBAT – Transporte em segundo plano com latência otimizada](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Ao contrário do controle tradicional, o LEDBAT pode usar toda a largura de banda disponível como tarefa em segundo plano, liberando largura de banda instantaneamente quando solicitado por outro tráfego. Diferentemente do BITS, não há atraso, tudo é automatizado, sem a necessidade de ajuste ou programação manual, e tudo é configurado no servidor. Isso possibilita grandes ganhos de desempenho em potencial.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>**Opções ponto a ponto**

As opções de ponto a ponto estão sendo cada vez mais usadas em migrações do Windows 10, para geração de imagens de computador, atualizações de software e personalização de usuário. Elas também são importantes para facilitar as atualizações entre compilações depois da implantação inicial do Windows 10. Aqui vamos ver diversos exemplos para ajudar a mover o tráfego relacionado ao Windows 10 e ao Office para longe do centro da rede, reduzindo a necessidade de abordagens de controle clássicas e permitindo que os PCs encontrem os arquivos de atualização necessários em pontos na rede local em vez de baixá-los de um ponto de distribuição ou da Internet.

O **BranchCache** ajuda a baixar o conteúdo em ambientes distribuídos sem saturar a rede. São duas opções: modo de cache hospedado, que permite usar os servidores locais para armazenar conteúdo em cache, e modo de cache distribuído (um modo com suporte no System Center Configuration Manager), que permite aos clientes compartilhar o conteúdo já baixado entre eles.

**Cache de mesmo nível** Os clientes com suporte no System Center Configuration Manager também podem usar o cache de mesmo nível. Isso permite que os PCs disponíveis com segurança na rede hospedem a fonte de distribuição de conteúdo. Não convém habilitar essa opção em todos os PCs, apenas os com conexões confiáveis com a rede como hosts (por exemplo, área de trabalho, minitorre ou PCs de torre). O cache de mesmo nível pode até mesmo funcionar para tarefas de implantação em execução nas fases do Windows PE durante a configuração.

Observação: BranchCache e cache de mesmo nível são complementares e podem funcionar juntos no mesmo ambiente.

[BranchCache versus Cache Par](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Otimização de distribuição** A otimização de distribuição é outra tecnologia ponto a ponto de armazenamento em cache, oferecendo controles baseados na rede para implantações do Windows. A otimização de distribuição do Windows 10 para atualizar aplicativos UWP internos, também para instalar aplicativos pela Microsoft Store e para atualizações de software usando Atualizações Expressas. Está disponível desde as primeiras versões do Windows 10, ainda que tenha sido integrada apenas recentemente ao System Center Configuration Manager. Desde o Windows 10 versão 1803, novas opções de configuração significam que você agora pode definir limites de largura de banda de forma independente para atualizações em segundo plano e trabalhos em primeiro plano, como a instalação de aplicativos da Store.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Considerações adicionais do Office 365 ProPlus**

Confira três itens que reduzirão a carga de rede devido a implantações do Office 365 ProPlus.

**Compactação delta binária** O Office 365 ProPlus usa a compactação delta binária para reduzir a largura de banda consumida pelas atualizações de software ao atualizar da versão mais recente do Office 365 ProPlus para a nova versão. Ao obter apenas as alterações de nível binário da versão anterior, o impacto do crescimento mensal de atualizações cumulativas é minimizado. Isso tem o potencial para economizar diversas centenas de dados, por PC, a cada mês. Para usar esse recurso, não é possível pular versões. Se fizer isso, a atualização cumulativa completa deverá ser baixada.

[Baixar as atualizações do Office 365](https://docs.microsoft.com/pt-BR/deployoffice/overview-of-the-update-process-for-office-365-proplus#download-the-updates-for-office-365-proplus)

**Arquivos de dados do Outlook** O Outlook frequentemente é configurado para armazenar toda a caixa de correio do usuário localmente para uso offline. Em qualquer implantação do Windows, exceto na atualização no local, isso requer que os arquivos de dados do Outlook dos usuário se recriem depois da atualização. Isso é um processo automatizado, mas com os limites das caixas de correio do Outlook normalmente configurados para até 100 GB, refazer o cache da caixa de correio inteira localmente para todos os usuário significa muita transferência de dados. Para reduzir a carga da rede, considere o uso da Política de Grupo para reduzir a configuração "Emails a manter offline". No Outlook no Office 365 ProPlus ou no Outlook 2016, o valor padrão está definido para 12 meses. Considere configurar o cache offline para durar entre 1 e 6 meses. A alteração dessa configuração não afeta o tamanho da caixa de correio online, e a caixa de correio inteira ainda poderá ser pesquisada pelo Outlook quando estiver online.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**Arquivos do OneDrive sob demanda para movimentação de pastas conhecidas** O OneDrive é uma excelente forma de sincronizar e proteger os arquivos dos usuários dos PCs e de outros dispositivos na nuvem. Com a movimentação de pastas conhecidas, você pode aplicar a sincronização de arquivos das pastas Área de Trabalho, Documentos e Imagens para o OneDrive, disponibilizando esses arquivos ao entrar em um novo dispositivo ou em um PC com uma nova imagem. Devido ao tamanho e ao número de arquivos mantidos nos locais Área de Trabalho, Documentos e Imagens, você deverá planejar as políticas habilitando e aplicando o OneDrive em seus PCs. Uma opção é usar os controles de Rede de Política de Grupo para controlar a largura de banda usada pelo serviço de sincronização do OneDrive.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Movimentação de pastas conhecidas da instalação](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[Arquivos do OneDrive sob demanda](https://www.microsoft.com/pt-BR/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Caso ainda não tenha implementado o OneDrive, a migração do Windows 7 para o Windows 10 é uma excelente oportunidade de habilitar o OneDrive, e ele se integra de forma descomplicada ao Office 365 ProPlus. Considere iniciar a implementação enquanto estiver trabalhando na preparação do dispositivo e de aplicativos. Isso dará uma frente para a sincronização de arquivos antes que você comece a mover as imagens do Windows e implantar aplicativos pela rede.

## <a name="next-step"></a>Próxima etapa 

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[Etapa 3: Entrega de aplicativos do Office e LOB](https://aka.ms/mdd3)

## <a name="previous-step"></a>Etapa anterior:

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[Etapa 1: Preparação de dispositivos e aplicativos](https://aka.ms/mdd1)

## <a name="feedback"></a>Comentários

Adoraríamos ouvir suas ideias. Escolha uma forma:

Comentários sobre o produto. Entre para fazer comentários sobre a documentação

Nosso novo sistema de comentários foi criado com base nos problemas do GitHub. Leia sobre essa alteração no post do blog.
