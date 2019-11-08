---
title: Etapa 7 - Manutenção do Windows e do Office
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Saiba como se preparar para a manutenção do Windows e do Office em seu ambiente.
ms.openlocfilehash: a1cc9cb66754ed86f982d90db0ccbcce16b5ffb1
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031496"
---
# <a name="step-7-windows-and-office-servicing"></a>Etapa 7: Manutenção do Windows e do Office

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Etapa 7: Manutenção do Windows e do Office</strong></p>
<p>O Windows 10 e o Office 365 ProPlus adicionam continuamente novos recursos para melhorar a segurança e a experiência do usuário com as últimas inovações. Saiba como instalar as atualizações semestrais e mensais, descubra como o novo modelo de serviço funciona e que opções e ferramentas você tem.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>A manutenção do Windows e do Office é a sétima etapa no nosso processo de implantação recomendado que aborda os aspectos de planejamento de preparação para atualizações semestrais dos recursos. Para ver o processo completo de implantação de desktop, visite o [Centro de Implantação do Computador](https://aka.ms/HowToShift).
>

O Windows 10 e o Office 365 ProPlus apresentam novas opções de manutenção, modelos de suporte e linhas do tempo de atualizações. Essas alterações simplificam o processo para se manter atualizado com os recursos mais recentes. Com essas atualizações, há novas opções de configuração para habilitar os planos de manutenção que atendam às suas necessidades. Saiba como se preparar para as atualizações nos canais semestrais, as quais oferecem novos recursos e funcionalidades no Windows 10 e no Office 365 ProPlus, ao mesmo tempo que aprimoram novas funcionalidades no System Center Configuration Manager (Branch Atual).

[Como ajudar clientes a mudar para o Windows 10 e o Office 365 ProPlus](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Tipos de atualização

Há duas categorias principais de atualizações, as atualizações de recursos e, posteriormente, as atualizações de qualidade e segurança que contêm correções de bugs, confiabilidade e segurança cumulativa. Em termos frequência, tanto o Windows quanto o Office oferecem um canal semestral que fornece novos recursos duas vezes por ano, por volta de março e de setembro, enquanto as atualizações de qualidade e segurança ocorrerem mensalmente. Além disso, oferecemos com exclusividade para os aplicativos do Office 365 uma opção de canal mensal, com suporte total, em que há atualizações de novos recursos e de qualidade.

Se você está acostumado a um ciclo mais longo entre as atualizações do sistema operacional da área de trabalho e de aplicativo, deve estar se perguntando:

  - As atualizações serão compatíveis?

  - Será necessário continuar treinando meus usuários?

  - E quais são os riscos?

Para responder a essas perguntas e demonstrar o raciocínio para fornecer novos recursos com mais frequência, falaremos sobre algumas das vantagens dessa abordagem

### <a name="feature-update-benefits"></a>Benefícios da atualização de recursos

Primeiro, abandonamos o modelo do passado que apresentaria ondas gigantes de alterações a cada três anos e passamos para alterações incrementais menores com atualizações de recursos duas vezes por ano. Por quê? Com as tendências de tecnologia mudando tão depressa, além das ameaças à segurança evoluírem rapidamente, isso deixa as experiências e as proteções mais atualizadas. Algumas das atualizações de segurança relacionadas, por exemplo, não podem apenas ser entregues por atualizações de segurança mensais ou arquivos de assinaturas de antivírus; podem ser uma plataforma de alterações de baixo nível, como a segurança baseada em virtualização.

[Guia rápido para o Windows como serviço](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Mitigar as ameaças usando recursos de segurança do Windows 10](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Benefícios do modelo de atualização cumulativa

Fornecer atualizações de qualidade e segurança como um pacote de atualização cumulativa corrige vários dos problemas do passado. Antes era possível escolher entre várias atualizações mensalmente para o Windows e o Office. Como você pode imaginar, isso cria um conjunto de matrizes de teste com suporte praticamente inviável. Além disso, se você instalasse uma versão do Windows ou Office que tivesse um ano ou fosse mais antiga, poderia levar horas ou, às vezes dias, para aplicar todas as atualizações fornecidas desde que essa versão foi lançada.

Com o modelo cumulativo, basta apenas uma única atualização e a quantidade de atualizações mensais que você precisa implantar é menor. Cada atualização contém as atualizações dos meses anteriores e todas as correções necessárias. As atualizações cumulativas são especialmente úteis quando os computadores ficaram desligados por vários meses por estarem aguardando serem reatribuídos a outro usuário.

### <a name="expanded-validation-of-updates"></a>Validação expandida das atualizações

Outra vantagem é que, antes de distribuirmos as atualizações para a ampla implantação, lançamos primeiro builds por meio dos programas Insider para o [Office](https://products.office.com/office-insider?tab=Windows-Desktop) e o [Windows](https://insider.windows.com/), o que nos permite obter dados de diagnóstico e comentários antes de lançar as atualizações de forma mais abrangente. Agora, os programas Insider estão abertos para todos, assim você poderá entender as atualizações com antecedência. Quando lançarmos as atualizações, já teremos recebido dados de diagnóstico de milhões de configurações; portanto, ao disponibilizamos as atualizações, a qualidade será inerentemente mais previsível

E uma última coisa. Como os builds do Office 365 ProPlus Insider refletirão as atualizações de canal mensais, se você estiver usando um canal semestral para o Office para fornecer atualizações de recursos duas vezes por ano com alinhamento ao Windows, também poderá validar esses builds antecipadamente usando as versões direcionadas do canal semestral.

### <a name="supporting-management-tools"></a>Suporte a ferramentas de gerenciamento

Também pensamos em como simplificar a implantação das atualizações para você. O System Center Configuration Manager (Branch Atual) é atualizado frequentemente para oferecer suporte à distribuição dessas atualizações para o Windows e o Office e os novos recursos.

[Implantar as atualizações do Windows 10 usando o System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Gerenciar o Office 365 ProPlus com o Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Visão geral dos canais do Windows e do Office

O Windows 10 oferece três canais de manutenção:

- O [**Programa Windows Insider**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) é direcionado para que as organizações testem e forneçam comentários sobre os recursos que serão disponibilizados na atualização de recursos seguinte
- O **Canal Semestral** fornece novas funcionalidades com as versões de atualização de recursos, duas vezes por ano
- O **Canal de Manutenção em Longo Prazo** é projetado somente para dispositivos especializados que necessitam de uma opção de manutenção mais longa

O Office 365 oferece quatro canais de manutenção:

- O [**Programa Office Insider**](https://support.office.com/article/What-is-Office-Insider-f4208185-b63a-4b68-9c7a-9a32d2411c16) é direcionado para que as organizações testem e forneçam comentários sobre os recursos e as funcionalidades mais recentes do Office ainda em desenvolvimento
- O **Canal Mensal** oferece aos usuários os recursos mais recentes do Office, assim que eles são disponibilizados.
- O **Canal Semestral** fornece novas funcionalidades com novos recursos, apenas duas vezes por ano
- O **Canal Semestral (direcionado)** é um build com suporte total do Office que permite aos usuários-piloto e a testadores de compatibilidade do aplicativo testar e validar o próximo Canal Semestral

Para obter informações detalhadas sobre os canais de manutenção do Windows e do Office, examine a documentação a seguir:

- [Visão geral do Windows como Serviço](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>Implantação de atualizações em fases

Agora vamos mudar de assunto e falar como você implantará essas atualizações. Para qualquer versão, recomendamos pelo menos três fases de implantação para TI: validação, piloto e implantação de produção ampla. Quando estiver executando o Windows 10 e o Office 365 ProPlus, você usará o atendimento mensal para receber atualizações críticas de segurança e qualidade. Em seguida, passará para atualizações semestrais para novos recursos.

### <a name="monthly-updating"></a>Atualização mensal

O modelo do serviço é projetado para que você possa optar por limitar a distribuição dos novos recursos para duas vezes por ano e, se necessário, você poderá até mesmo ignorar uma atualização semestral e continuar a receber atualizações de segurança e qualidade. Conforme mencionado, a natureza cumulativa das atualizações mensais significa que cada uma aumentará de tamanho a cada mês.

#### <a name="express-updates"></a>Atualizações Expressas

Usando uma tecnologia chamada "Atualizações Expressas" no Windows e na compactação de delta binário no ice, podemos reduzir consideravelmente o tamanho do download. Em ambas as abordagens, os mecanismos de atualização comparam o que está no computador e descobrem apenas as diferenças que devem ser atualizadas.

[Atualizações de qualidade do Windows 10 explicadas e o final das atualizações de delta](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

O Windows Update para Empresas e o Windows Server Update Services têm suporte para atualizações expressas há muito tempo, mas agora ampliamos esse suporte para o System Center Configuration Manager (Branch Atual) para que ele também possa usar as Atualizações Expressas.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Compactação de Delta Binário

A Compactação de Delta Binário no Office é usada apenas se você estiver atualizando da versão mais recente do Office 365 ProPlus. Dessa forma, para usar essa abordagem, você precisará estar atualizando de uma compilação anterior e não poderá ignorar atualizações.

Os canais de atualização do Windows e do Office podem ser gerenciados pelo Gerenciador de Configuração usando o processo padrão de direcionamento e aprovação. Além disso, você pode usar as configurações de política no Office e no Windows para impor os canais de atualização usados, além das configurações relacionadas.

### <a name="semi-annual-updates"></a>Atualizações semestrais

Essas são as nossas considerações sobre as atualizações mensais. Agora vamos falar das atualizações semestrais maiores.

Como abordamos na preparação do dispositivo e do aplicativo, convém começar sua preparação para essas atualizações maiores usando as mesmas ferramentas de preparação que configuramos na Etapa 1 do processo de implantação.

Para as ferramentas, você pode usar as configurações de política com o Windows Update para Empresas, o gerenciamento de atualizações de software por meio do System Center Configuration Manager (Branch Atual), o Windows Server Update Services (WSUS) ou as políticas de atualização definidas pelo Microsoft Intune. Se você estiver preocupado com a largura de banda, confira a Etapa 2: Preparação de Diretório e Rede, para saber mais sobre as opções para reduzir o tráfego de rede pela Otimização de Entrega e outras tecnologias de cache ponto a ponto.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Canal Semestral do Windows](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Canal Semestral para o Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Atualizar as sequências de tarefas

Instalar as atualizações de recursos maiores por meio de rotinas de gerenciamento de atualização de software é uma opção compatível, mas muitas organizações optarão por usar uma Sequência de tarefas de atualização com o System Center Configuration Manager (Branch Atual) ou o Kit de Ferramentas de Implantação da Microsoft.

Uma sequência de tarefas permite que você crie verificações ou tarefas personalizadas ANTES de instalar a atualização de recursos e permite executar tarefas personalizadas APÓS a instalação da atualização ser concluída. As tarefas após a atualização podem incluir suspensão temporária de serviços se isso for necessário durante a atualização, instalação e substituição de driver, atualizações de aplicativo ou barra de tarefas e configurações de personalização inicial do Windows 10.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

Se você já está usando as sequências de tarefas para migrar seus computadores com o Windows 7 para o Windows 10 e está habituado com essas ferramentas, este é um ótimo lugar para começar e exercer o máximo controle. Embora seja possível usar uma única sequência de tarefas para a atualização inteira, é muito comum que as organizações usem duas sequências de tarefas: uma para garantir que os computadores estejam prontos para a atualização, que silenciosamente prepara para as fases todos os arquivos de instalação necessários nos computadores de destino e um para fazer a atualização de fato. Esta abordagem garante que a produtividade do usuário seja menos afetada.

[Criar uma sequência de tarefas para atualizar um sistema operacional no Gerenciador de Configurações](https://docs.microsoft.com/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Suporte de canal semestral para atualizações de recursos

[Conforme anunciado em setembro de 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), a linha do tempo de suporte para atualizações de canal semestral usará o modelo a seguir.

  - Todas as atualizações de recursos com suporte no momento do Windows 10 Enterprise e Education, a partir da versão 1607, terá suporte para 30 meses a partir de sua data de lançamento original.

  - Todas as atualizações de recursos futuras, a partir da versão 1809, com previsão para setembro, terão suporte por 30 meses a partir de sua data de lançamento.

  - As atualizações de recursos futuras, a partir da versão 1903 em março, terão suporte por 18 meses a partir de sua data de lançamento.

  - As atualizações semestrais do Office 365 ProPlus continuam a ter suporte para 18 meses

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Opções adicionais de automação de instalação fora das sequências de tarefas

Se você não usa as sequências de tarefas de atualização, agora pode executar ações personalizadas ou aplicar arquivos driver durante as atualizações de recurso na fase de pré-instalação, antes de a configuração ser executada nas verificações de compatibilidade, ou na fase de pré-confirmação, antes da aplicação da atualização.

[Novidades na instalação do Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Próxima etapa 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[Etapa 8: Treinamento e comunicações de usuários](https://aka.ms/mdd8)

## <a name="previous-step"></a>Etapa anterior 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[Etapa 6: Implantação de sistema operacional e atualizações de recursos](https://aka.ms/mdd6)