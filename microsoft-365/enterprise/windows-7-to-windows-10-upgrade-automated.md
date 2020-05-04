---
title: Atualizações automatizadas do Windows 7 para o Windows 10
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 07/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Atualizações automatizadas do Windows 7 para o Windows 10 para grandes organizações
ms.openlocfilehash: 575ffba84b2cd7b7cfe5267a35a9f36c75dbe306
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011546"
---
# <a name="windows-7-to-windows-10-automated-in-place-upgrades-for-large-organizations"></a>Atualizações automáticas in-loco do Windows 7 para o Windows 10 para grandes organizações

A partir de 14 de janeiro de 2020, atualizações de segurança ou suporte para PCs com Windows 7 não serão mais fornecidos. Para a mudança do Windows 7 para o Windows 10 e com várias opções para implantar, uma pergunta comum na comunidade de TI é: "Qual é a maneira mais rápida de se mover do Windows 7 para o Windows 10?" A resposta curta é executar atualizações in-loco para computadores existentes e fazendo isso você pode reduzir o foco em vários aspectos do processo de implantação da área de trabalho.

<center><img src="../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-1.png" alt="wheel" height="421" width="500" /></center>

Usando as atualizações in-loco, vários processos de implantação de área de trabalho são reduzidos drasticamente no escopo, especialmente:

  - **Empacotamento de aplicativos** e redistribuição de aplicativos de linha de negócios obrigatórios, eles são simplesmente transferidos para o ambiente do Windows 7

  - **Migração de arquivos** e configurações básicas do usuário. Estes também são transferidos da instalação anterior quando o mesmo usuário mantém o dispositivo

As tarefas acinzentadas no gráfico de roda do processo de implantação acima não são itens que você pode ignorar completamente, mas para economizar tempo, isso presume que você encaminhará a configuração de segurança, altere os processos de atualização do software após a implantação e presumiremos que o treinamento do usuário para o componente do Windows ocorreu em grande parte em casa para seus usuários, pois os computadores Windows adquiridos em particular desde 2012 não tiveram o Windows 7 pré-carregado e o lançamento do Windows 10 em 2015, a maioria dos sistemas domésticos Windows 7 também foram atualizados para o Windows 10.

## <a name="in-place-upgrade-reliability-safeguards-and-scale"></a>Segurança, proteções e confiabilidade no local

As atualizações in-loco para o Windows 10 são uma abordagem confiável para mover um dispositivo existente com Windows 7 ou posterior para o Windows 10, sem exigir a migração de arquivos ou a reinstalação do aplicativo. Após uma atualização in-loco, os arquivos, as configurações e os aplicativos disponíveis do usuário são consistentes com a respectiva instalação anterior do Windows 7. As atualizações também funcionam quando uma mudança de arquiteturas similares (de 32 bits a 32 bits ou de 64 bits a 64 bits) e para as edições do Windows (Professional para Pro ou Enterprise para Enterprise).

O processo de atualização, por padrão, faz backup da instalação anterior do Windows, como parte da atualização, para que, no caso de uma falha de atualização, ou se um dispositivo ou aplicativo não funcionar corretamente após a atualização, o computador possa ser revertido para o Windows 7. Os computadores atualizados por padrão têm 10 dias, para que você possa iniciar manualmente uma reversão para o Windows 7, se necessário.

As atualizações in-loco podem ser automatizadas usando as ferramentas de implantação do sistema operacional como o [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) ou o [Kit de Ferramentas de Implantação da Microsoft](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit). Este artigo destaca as abordagens e otimizações automatizadas juntamente com links para recursos relacionados para obter ajuda adicional.

## <a name="upgrading-a-small-number-of-computers"></a>Atualizar um pequeno número de computadores

No caso de um único computador ou de vários computadores, a abordagem manual da atualização geralmente é a melhor opção em comparação com abordagens mais automatizadas. Você pode encontrar o software e as licenças necessárias na [Microsoft Store](https://go.microsoft.com/fwlink/p/?LinkId=808282), outros revendedores de software ou no  [Centro de Atendimento de Licenciamento por Volume](https://www.microsoft.com/licensing/servicecenter/default.aspx), caso tenha um licenciamento por volume. Para obter instruções detalhadas sobre como atualizar um único PC para o Windows 10, bem como as opções de restauração pós-atualização, confira o [Guia passo a passo de atualização manual do Windows 7 para Windows 10](https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade).

## <a name="how-to-upgrade-many-computers"></a>Como atualizar muitos computadores

Se você gerencia dezenas ou milhares de computadores, a melhor opção é executar atualizações in-loco usando a automação de sequência de tarefas com o Microsoft Endpoint Configuration Manager ou o Kit de Ferramentas de Implantação da Microsoft. Embora o processo seja muito confiável na maioria das situações, dependendo do número de computadores que você está atualizando, ainda faz sentido realizar os testes e os controles necessários no local para garantir o sucesso em escala.

Isso significa que você pode ignorar a disponibilidade do diretório ou as tarefas associadas ao Azure Active Directory, ao Office e à distribuição de aplicativos de linha de negócios e a migração de arquivos do usuário, pois esses aspectos são mantidos como parte da atualização, e a segurança deve ser levada adiante. Essas áreas podem ser melhoradas ao mesmo tempo.

As opções de implantação de atualização são abordadas na [Implantação de SO e atualizações de recursos](https://www.aka.ms/mdd6) e embora você possa criar facilmente soluções com script que executem a configuração do Windows 10 de maneira automatizada com interação mínima ou sem administração, uma sequência de tarefas fornecerá um controle mais granular para:

  - Executar verificações de pré-implantação,

  - Gerenciar o estado de criptografia de unidade pré-atualização,

  - Desinstalar os drivers e aplicativos problemáticos conhecidos,

  - Instalar drivers adicionais e aplicativos pós-atualização,

  - Gerenciar o estado de criptografia de unidade após a atualização,

  - Restaurar um computador para um estado anterior – onde os aplicativos ou drivers desinstalados são reinstalados – no caso de falha na atualização,

  - Além de tudo o que você precisa configurar para alcançar um estado pronto para empresas

![](../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-2.png)

Os motivos mais comuns pelos quais as atualizações podem não ser concluídas ou não podem incluir desafios com:

  - Drivers de dispositivo desatualizados

  - Criptografia de disco de<sup>terceiros</sup>

  - Soluções de código de baixo nível, como anti-malware, VPN ou virtualização

Os modelos de [Atualização de sequência de tarefas](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) estão incorporados ao Branch atual do Microsoft Endpoint Configuration Manager e estão disponíveis para várias versões. Em versões recentes, há melhorias significativas de tecnologia no Configuration Manager que tornam o processo ainda mais eficiente para determinar a compatibilidade de dispositivos e do Office, reduzindo o tráfego de rede e configurando novas opções como o backup do OneDrive. Assista a esta [ apresentação do Microsoft Mechanics](https://youtu.be/CYRnAmCD7ls) para saber mais sobre as atualizações recentes para a implantação do sistema operacional do Configuration Manager.

Caso não use o Microsoft Endpoint Configuration Manager, você pode usar o Kit de Ferramentas de Implantação da Microsoft para criar e executar a atualização de sequências de tarefas de implantação.

## <a name="pre-cache-task-sequence-upgrades"></a>Atualizações de sequência de tarefas anteriores ao cache

A [opção de cache anterior](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system#configure-pre-cache-content) para o Configuration Manager permite que os clientes baixem o conteúdo do pacote de atualização do sistema operacional antes da sequência de tarefas atualizar o sistema operacional. Anteriormente, iniciar a sequência de tarefas iniciaria o download do conteúdo do pacote. O conteúdo anterior ao cache também oferece a opção de baixar o pacote de atualização do SO aplicável e todo o conteúdo mencionado assim que ele recebe a implantação.

Sequências de tarefas anteriores ao cache combinadas com verificações de compatibilidade

Além de economizar tempo para o download do pacote, você pode pré-testar o pacote de atualização e usar a instalação do Windows para avaliar se a atualização in-loco será bem-sucedida antes de executar a atualização do Windows. A seguinte sintaxe de linha de comando pode ser usada para executar silenciosamente uma verificação de compatibilidade e descobrir se a instalação do Windows avalia ou não o dispositivo como pronto para atualização.

Os logs serão enviados para o caminho de servidor definido e a instalação do Windows não será exibida para o usuário e feche sem a interação do usuário.

Os resultados dos próprios logs serão:

1.  Se a instalação não encontrar um problema de compatibilidade e o PC parecer atender a todos os requisitos, ele retornará\_MOSETUP\_E\_COMPAT SCANONLY (0xC1900210)

2.  Se a configuração encontrar problemas de compatibilidade acionáveis, como aplicativos incompatíveis, eles retornarão\_MOSETUP\_E\_COMPAT\_INSTALLREQ Block (0xC1900208)

3.  Se a configuração encontrar o computador não for elegível para o Windows 10, ele retornará\_MOSETUP\_SYSREQ\_\_E COMPAT (0xC1900200)

4.  Se a instalação achar que o computador não tem espaço livre suficiente para instalar, ele retornará MOSETUP\_E\_INSTALLDISKSPACE\_Block (0xC190020E)

Depois de implantar seqüências de cache com verificações de compatibilidade para um grande número de PCs em um conjunto, você pode começar a analisar os arquivos de log para a prontidão do dispositivo. Usar as saídas listadas acima \#, 1 (0xC1900210) pode ser reportado como "pronto para implantar \#" e 4 (0xC190020E) pode ser transportado ao liberar espaço em disco. Nesse caso, tome cuidado com o que excluir, mas a limpeza e a limpeza do Windows Update, da lixeira e dos arquivos temporários são locais para iniciar e muitos casos oferecem espaço suficiente para que a atualização seja bem-sucedida. Você pode executar a verificação de compatibilidade quantas vezes forem necessárias até que o PC esteja pronto para a atualização in-loco. Você pode encontrar mais informações sobre as opções de linha de comando da instalação do Windows no <https://aka.ms/setupswitches>

## <a name="desktop-deployment-center"></a>[Centro de Implantação do Computador](https://aka.ms/howtoshift)
