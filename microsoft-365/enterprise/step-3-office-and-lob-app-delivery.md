---
title: 'Etapa 3: Entrega de aplicativos do Office e LOB'
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
description: Saiba como entregar aplicativos do Office e LOB.
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865333"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Etapa 3: Entrega de aplicativos do Office e LOB

Agora você está pronto para entregar seus aplicativos do Office e LOB. Há algumas maneiras de fazer isso, inclusive algumas novas opções incríveis. Reserve um tempo para analisar e escolher os melhores métodos para suas necessidades atuais.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Etapa 3: Entrega de aplicativos do Office e LOB</strong></p>
<p>Certifique-se de que os aplicativos estejam empacotados e prontos para instalação automatizada. Saiba como o empacotamento Clique para Executar com o Office 365 ProPlus oferece novas opções para configurar, oferecer e manter seus aplicativos do Office atualizados.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>A entrega de aplicativos do Office e LOB é a terceira etapa de nossa roda da implantação recomendada que aborda as opções para instalar e gerenciar o Office e a LOB. Para uma implantação bem-sucedida, não ignore as primeiras duas etapas. Para ver o processo completo de implantação do computador, acesse o [Centro de Implantação do Computador Moderno](https://aka.ms/HowToShift).
>

Embora alguns aplicativos só estejam disponíveis como uma versão compilada de 32 ou 64 bits, outros, incluindo o Office 365 ProPlus, tanto como código compilado nativo de 32 e de 64 bits, e uma das maiores decisões que você fará é a versão que deseja implantar. Para aproveitar a RAM e a capacidade de cálculo adicionais em novos dispositivos, convém usar a versão de 64 bits, mas, antes disso, será necessário descobrir quaisquer dificuldades de compatibilidade relacionadas a arquivo ou a suplemento existentes. Para isso, talvez você precise voltar a visitar a Etapa 1 Preparação de dispositivos e aplicativos antes de continuar.

Se nada estiver impedindo você, recomendamos a implantação de versões de 64 bits de todos os aplicativos, incluindo o Microsoft Office. Os aplicativos nativos compilados de 64 bits oferecem o melhor desempenho e são a opção mais adequada para o futuro.

Há muitos métodos e modelos para instalar aplicativos no Windows, portanto, vamos analisar suas opções de entrega.

[Gerenciamento de aplicativos do Windows 10](https://docs.microsoft.com/pt-BR/windows/application-management/)

## <a name="msi-based-deployments"></a>Implantações baseadas em MSI

Para seus aplicativos de linha de negócios, você provavelmente usará pacotes ou executáveis baseados em MSI e instalará aplicativos como parte de uma sequência de tarefas de distribuição de SO. O Windows 10 continua a funcionar com esses pacotes

As ferramentas de implantação de software, como o System Center Configuration Manager e o Microsoft Intune, também são otimizadas para entregar aplicativos empacotados por MSI. Depois de validar seus aplicativos no Windows 10, você poderá usar o System Center Configuration Manager (ramificação atual) para a entrega de aplicativos. Se usar o Portal da Empresa no Microsoft Intune, você poderá estender a escolha de aplicativos sancionados pela TI disponíveis para a sua organização, com a finalidade de incluir os aplicativos mais recentes, e os usuários para que escolham eles mesmos o que precisam.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>Geração de imagens de computador

Outro método popular de entrega de aplicativos é a geração de imagens de computador. Nesse caso, os aplicativos são instalados via sequência de tarefas ou manualmente em um computador de amostra e, em seguida, uma imagem do sistema é capturada com os aplicativos necessários pré-instalados. A abordagem de geração de imagens para criar e capturar pode economizar tempo ao provisionar novos computadores, mas lembre-se de que sistemas operacionais e aplicativos dentro da imagem podem se tornar obsoletos rapidamente. O modelo de Atualização Cumulativa no Windows 10 e no Office 365 ProPlus ajuda com esse problema, mas não o elimina completamente. É por isso que recomendamos uma abordagem de imagem fina, em que seus aplicativos são instalados de fora da imagem no momento da implantação.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Se você quiser incluir o Office 365 ProPlus na sua imagem, lembre-se de que isso usa uma ativação baseada no usuário; não pode ser pré-ativado pelo administrador do sistema. Use a Ferramenta de Implantação do Office para pré-instalar o Office no dispositivo que você está gerando imagens e ignorar a entrada do usuário. Os usuários podem entrar, receber a ativação e aproveitar outros recursos que aproveitam a entrada no primeiro uso.

[Criar uma sequência de tarefas para instalar um sistema operacional](https://docs.microsoft.com/pt-BR/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>Clique para Executar 

O Office 365 ProPlus é instalado usando o Clique para Executar, e o Clique para Executar substitui o pacote baseado em MSI em todas as versões da próxima versão do Office 2019 para Windows. Ele traz várias vantagens, incluindo instalações mais rápidas, atualização mais rápida e eficiente e desinstalação mais limpa.

Os programas entregues por meio do Clique para Executar são executados em um ambiente de aplicativo virtual em seu computador e, assim, coexistem com outros aplicativos sem conflito; eles também ocupam metade do espaço em disco que usariam como um pacote baseado em MSI. E como o Clique para Executar oferece suporte ao streaming de programas, ao transmitir os recursos mais usados primeiro, os usuários podem começar a usar os aplicativos do Office em apenas alguns minutos, em vez de esperar que o Office seja instalado totalmente primeiro. Isso é importante não apenas para a implantação inicial, isso significa que as atualizações podem ser transmitidas perfeitamente em segundo plano com impacto mínimo nos usuários.

Se você usar o System Center Configuration Manager, ainda poderá usá-lo para uma ampla implantação do Office 365 ProPlus. O System Center Configuration Manager (ramificação atual) tem suporte nativo para a Ferramenta de Personalização do Office atualizada, personalização de pacote para o Clique para Executar no momento da instalação e suporte nativo para pós-instalação de gerenciamento de atualização de software.

[Guia de implantação do Office 365 ProPlus](https://docs.microsoft.com/pt-BR/deployoffice/deployment-guide-for-office-365-proplus)

[Remover as versões MSI existentes do Office durante a atualização para o Office 365 ProPlus](https://docs.microsoft.com/pt-BR/deployoffice/upgrade-from-msi-version)

[Gerenciar o Office 365 ProPlus com o Configuration Manager](https://docs.microsoft.com/pt-BR/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Atribuir aplicativos do Office 365 a dispositivos do Windows 10 com o Microsoft Intune](https://docs.microsoft.com/pt-BR/intune/apps-add-office365)

## <a name="browser-based-apps"></a>Aplicativos baseados em navegador

Há algumas coisas a serem consideradas para garantir que os aplicativos baseados em navegador continuem funcionando conforme o esperado. Se tiver sites e aplicativos específicos que você sabe que têm problemas de compatibilidade com o Microsoft Edge, poderá usar a lista de sites do Modo Empresarial para que os sites sejam abertos automaticamente no Internet Explorer 11.

Além disso, se você souber que os sites da sua intranet não funcionarão adequadamente no Microsoft Edge, poderá definir todos os sites da intranet para serem abertos usando o Internet Explorer 11 automaticamente. Esse processo usa um arquivo XML para determinar se o IE11 é usado para cada site, usando a Política de Grupo para impor configurações.

Até agora, abordamos métodos de implantação bem conhecidos. Mas há duas novas abordagens para a implantação de aplicativos que você pode considerar.

[O que é o Modo Empresarial](https://docs.microsoft.com/pt-BR/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas 

A Microsoft Store para Empresas fornece uma maneira flexível de descobrir, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos para dispositivos Windows 10 em grande escala. Como administrador de TI, você pode publicar aplicativos da Microsoft Store selecionados, juntamente com seus próprios aplicativos personalizados, em sua própria loja particular e atribuir e reutilizar licenças conforme necessário. Seus usuários são direcionados apenas a essa loja e, por isso, só podem encontrar e instalar aplicativos aprovados.

Os aplicativos da Store podem ser criados nativamente como aplicativos UWP, ou você pode usar a Ponte de Desktop para reempacotar seus aplicativos existentes para a Loja e adicionar experiências modernas para o Windows 10. Além do código usado para iluminar experiências do Windows 10, seu aplicativo permanece inalterado e continua a executar no modo de usuário de confiança total.

## <a name="msix-containerization"></a>Transporte em contêineres de MSIX

Uma nova opção para o empacotamento de aplicativos é o MSIX. O MSIX usa a tecnologia de transporte em contêineres disponível no Windows, reunindo os melhores aspectos do empacotamento Clique para Executar, UWP e MSI. Com ferramentas para migrar instaladores existentes como EXE, MSI, APPV e APPX diretamente para o MSIX, vemos que o Transporte em Contêineres de MSIX fornece um caminho uniformizado para as muitas tecnologias de instalação em uso atualmente. O suporte a MSIX vem incluído nas versões atuais do Windows: qualquer dispositivo que execute o Windows 10 RS5 ou mais recente inclui tudo o que você precisa para instalar e executar aplicativos em pacote do MSIX. O Windows 10 integra dinamicamente os contêineres MSIX que recebe, mantendo os aplicativos separados do sistema operacional.

Transporte em contêineres significa desinstalação e remoção limpa de pacotes ao contrário de uma grande quantidade de pacotes baseados em MSI e EXE atualmente que pode deixar itens no sistema. Isso também significa apenas a necessidade de credenciais de Usuário Padrão para instalar aplicativos – você não precisa ter as credenciais de administrador para instalar contêineres MSIX. Contêineres MSIX são mais eficientes para atualizar também. Quando uma atualização for publicada, o uso de diferenciais de nível de bloqueio significa que apenas binários novos de rede são aplicados, reduzindo a carga de atualização, para implantações mais rápidas que consomem menos largura de banda.

Você pode encontrar mais informações sobre o MSIX através do [site da Comunidade Técnica do MSIX](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>Próxima etapa

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[Etapa 4: Arquivos e configurações de usuários](https://aka.ms/mdd4)

## <a name="previous-step"></a>Etapa anterior

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Etapa 2: Diretório e preparação de rede](https://aka.ms/mdd2) 