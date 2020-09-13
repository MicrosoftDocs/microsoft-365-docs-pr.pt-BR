---
title: Microsoft 365 Apps para empresas
description: Como implantar os aplicativos do Microsoft 365, como eles são atualizados e como as configurações são gerenciadas
keywords: histórico de alterações
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547741"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

## <a name="initial-deployment"></a>Implantação inicial

O Microsoft Managed desktop garante que o Microsoft 365 aplicativos para empresas (64 bits) sejam instalados como parte da imagem em todos os [dispositivos de programa](../service-description/device-list.md). Todos os aplicativos a seguir devem estar presentes no dispositivo quando entregues:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

Essa abordagem minimiza o impacto na rede e garante que os usuários possam ser produtivos assim que receberem seus dispositivos. Em seguida, implantamos políticas adicionais em dispositivos gerenciados para configurar os aplicativos para uso.

> [!NOTE]
> O Microsoft Teams é implantado separadamente dos aplicativos da Microsoft 365 para empresas e não está incluído na imagem base. 

### <a name="available-deployment-to-users"></a>Implantação disponível para os usuários

Se um usuário não tiver aplicativos Microsoft 365 em seus dispositivos por qualquer motivo, você poderá usar um pacote para retornar o dispositivo ao estado esperado. Adicione o usuário ao grupo de **área de trabalho moderna-Office-Office365_Install** e os aplicativos serão disponibilizados para eles no portal da empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Aplicativos da Microsoft 365 para empresas (32 bits)

A área de trabalho gerenciada da Microsoft não suporta a implantação da versão de 32 bits dos aplicativos do M365 para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Atualizações para os aplicativos do Microsoft 365

Os aplicativos do Microsoft 365 estão configurados para atualização no [canal corporativo mensal](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Esta prática fornece aos usuários novos recursos do Office a cada mês, mas eles receberão apenas uma atualização por mês em um cronograma de lançamento previsível. As atualizações são lançadas na segunda terça-feira do mês; essas atualizações podem incluir atualizações de recursos, segurança e qualidade. Essas atualizações ocorrem automaticamente e são retiradas diretamente da CDN do Office para esse canal específico.

O Microsoft Managed desktop Escalona cada versão para identificar possíveis problemas em seu ambiente. Concluímos a distribuição 28 dias após o lançamento do grupo de produtos de aplicativo do Microsoft 365. A área de trabalho gerenciada da Microsoft agenda versões de atualização para diferentes grupos para permitir o tempo de validação e teste da seguinte maneira: 

- Teste: 0 dias
- Primeiro: 0 dias
- Rápido: 7 dias
- Amplo: 21 dias

O Microsoft Managed desktop define um prazo de [atualização](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) de sete dias para dispositivos. Após a atualização estar disponível, ela deve ser instalada dentro de sete dias. Os usuários são [notificados](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de que as atualizações são necessárias em vários locais: o aplicativo, na bandeja do sistema 12 horas antes do prazo final, e eles recebem um aviso de 15 minutos antes do prazo final. Todos os aplicativos do Microsoft 365 devem ser fechados para que a atualização seja concluída.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar ou reverter uma atualização

Se você precisar pausar ou reverter a atualização do aplicativo Microsoft 365 por qualquer motivo, registre uma [solicitação de suporte de administrador](../working-with-managed-desktop/admin-support.md) por meio do portal de área de trabalho gerenciada da Microsoft.

Durante uma versão, a área de trabalho gerenciada da Microsoft monitora as taxas de erro de todos os aplicativos do Microsoft 365. Se observarmos uma diferença significativa na qualidade entre a nova versão e sua predecessora, poderemos contatá-lo pelo portal de administração de área de trabalho gerenciada da Microsoft. Dependendo da gravidade, perguntaremos se você deseja pausar a versão ou informá-lo de que fizemos uma ação para reduzir um problema. 

### <a name="delivery-optimization"></a>Otimização de entrega

A otimização de entrega é uma tecnologia de distribuição ponto a ponto disponível no Windows 10. Permite que os dispositivos compartilhem conteúdo, como atualizações, que os dispositivos tenham baixado da Microsoft pela Internet. Isso pode ajudar a reduzir a largura de banda da rede, pois um dispositivo pode obter partes da atualização de outro dispositivo em sua rede local, em vez de precisar baixar a atualização completamente da Microsoft.

A [otimização de entrega](https://docs.microsoft.com/deployoffice/delivery-optimization) é habilitada por padrão em dispositivos que executam o Windows 10 Enterprise ou Windows 10 Education Editions. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciadas pela área de trabalho gerenciada da Microsoft

A Microsoft gerencia algumas configurações como parte do serviço. A área de trabalho gerenciada da Microsoft não gerencia uma linha de base de segurança do Office, mas você pode definir uma, seguindo as orientações da seção [configurações que você gerencia](#settings-you-manage) .

### <a name="update-settings"></a>Atualizar configurações

A área de trabalho gerenciada da Microsoft mantém todas [as configurações de atualização](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) para dispositivos gerenciados e você deve modificar essas configurações.

### <a name="set-updates-to-occur-automatically"></a>Definir que as atualizações ocorram automaticamente

**Valor padrão**: habilitado

Essa política é configurada para garantir que todos os dispositivos do Office possam ser mantidos atualizados da nuvem. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Definir um prazo final quando as atualizações precisarem ser aplicadas

**Valor padrão**: 7 dias

A política **UpdateDeadline** é usada para configurar o período de cortesia que os usuários têm antes que uma atualização seja imposta ao dispositivo. Essa política de prazos também dispara [notificações](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) ao usuário para informá-las sobre as alterações necessárias em seus dispositivos.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Adiar atualizações em um dispositivo por um período

Essa política é configurada de forma diferente para cada grupo de dispositivos de gerenciamento de atualizações e é necessária para que o Microsoft Managed desktop atenda aos seus destinos de atualização:  

- Teste: 0 dias
- Primeiro: 0 dias
- Rápidos 7 dias
- Amplo: 21 dias

### <a name="update-notifications-settings"></a>Configurações de notificações de atualização

**Valor padrão**: false

A configuração "ocultar notificações de atualização" é definida como **false** nos dispositivos de área de trabalho gerenciada da Microsoft para fornecer a melhor experiência de atualização para os usuários [notificando](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) -os quando as atualizações forem necessárias.

### <a name="specify-a-location-to-look-for-updates"></a>Especificar um local para procurar atualizações

**Valor padrão**: canal corporativo mensal

Uma combinação das políticas **UpdatePath** e **UpdateChannel** é usada conforme necessário para obter o cronograma de atualização. Essas políticas são definidas para garantir que todos os dispositivos do Office recebam atualizações diretamente da CDN para o canal corporativo mensal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especificar a versão de destino dos aplicativos do Microsoft 365

A política de versão de destino às vezes é usada pelo Microsoft Managed desktop para reverter ou fixar uma versão específica do Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar a opção para habilitar ou desabilitar atualizações automáticas do Office

**Valor padrão**: habilitado

Essa configuração é necessária para que o Microsoft Managed desktop atenda aos seus destinos de atualização para os aplicativos do Microsoft 365. 

### <a name="first-run-settings"></a>Configurações de tela de apresentação 

Há várias configurações que afetam o comportamento na primeira vez que o Office é executado.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceitar os termos de licença em nome do usuário final

**Valor padrão**: desabilitado

Na primeira vez que um usuário abrir um aplicativo do Microsoft 365, será solicitado que eles aceitem os termos de licença. Se você quiser aceitar os termos de licença em nome dos seus usuários, confira a solicitação de serviço com a equipe de operações de área de trabalho gerenciada da Microsoft solicitando que essa configuração seja habilitada. 

### <a name="suppress-outlook-mobile-check-box"></a>Caixa de seleção suprimir o Outlook Mobile

**Valor padrão**: desabilitado

Na primeira vez que um usuário abre o Outlook, ele é solicitado a instalar o Outlook Mobile. Se você não quiser que os usuários vejam essa caixa de seleção, faça uma solicitação de serviço com a equipe de operações de área de trabalho gerenciada da Microsoft solicitando que essa configuração seja habilitada para seus dispositivos. 

## <a name="other-settings"></a>Outras configurações

Há outras configurações do aplicativo da Microsoft 365 que a área de trabalho gerenciada da Microsoft pode configurar opcionalmente em seu nome. 

### <a name="disable-personal-onedrive"></a>Desabilitar o OneDrive pessoal

**Valor padrão**: desabilitado

Algumas organizações estão preocupada com os usuários que têm acesso a arquivos corporativos e pessoais em seus dispositivos. Você pode arquivar uma solicitação de serviço com a equipe de operações de área de trabalho gerenciada da Microsoft solicitando que essa configuração seja habilitada. 

## <a name="settings-you-manage"></a>Configurações que você gerencia

Há muitas outras políticas que o Microsoft Managed desktop ainda não definiu como parte do nosso serviço. Você pode configurá-los usando o Microsoft Intune, que usa o serviço de [política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) . Para fazer isso, siga estas etapas:

1.  Entre no centro de administração do Microsoft Endpoint Manager.
2.  Selecionar **aplicativos > políticas para aplicativos do Office > criar**
3.  Na página **criar** configuração de política, faça o seguinte:
    - Insira um nome.
    - Forneça uma descrição (opcional).
    - Em **atribuições**, escolha se esta política se aplica a todos os usuários de aplicativos do Microsoft 365 para empresas ou apenas aos usuários que acessam anonimamente os documentos usando o Office para a Web.
    - Selecione o grupo de segurança baseado em AAD atribuído à configuração de política. Cada configuração de política só pode ser atribuída a um grupo e cada grupo só pode ser atribuído a uma configuração de política.
    - Defina as configurações de política a serem incluídas na configuração da política. Você pode pesquisar o nome da configuração de política para localizar a configuração de política que deseja configurar. Você também pode filtrar o aplicativo, se a política é uma linha de base de segurança recomendada e se a política foi configurada. A coluna plataforma indica se a política é aplicada ao Microsoft 365 aplicativos para Enterprise para dispositivos Windows, Office para a Web ou todos.
4.  Depois de fazer suas seleções, escolha **criar**.

> [!NOTE]
> As políticas de configuração do Office só dão suporte à implantação baseada no usuário
