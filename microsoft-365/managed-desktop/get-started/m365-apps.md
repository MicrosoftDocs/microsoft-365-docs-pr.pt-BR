---
title: Microsoft 365 Apps para empresas
description: Como implantar Microsoft 365 Apps, como eles são atualizados e como as configurações são gerenciadas
keywords: histórico de alterações
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904847"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

## <a name="initial-deployment"></a>Implantação inicial

Área de Trabalho Gerenciada da Microsoft garante que Microsoft 365 Apps para Grandes Empresas (64 bits) sejam instalados como parte da imagem em todos os dispositivos [de programa.](../service-description/device-list.md) Todos os seguintes aplicativos devem estar presentes no dispositivo quando ele for entregue:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

Essa abordagem minimiza o impacto na rede e garante que os usuários possam ser produtivos assim que receberem seus dispositivos. Em seguida, implantamos mais políticas em dispositivos gerenciados para configurar os aplicativos para uso.

> [!NOTE]
> Microsoft Teams é implantado separadamente do Microsoft 365 Apps para Grandes Empresas e não está incluído na imagem base. 

### <a name="available-deployment-to-users"></a>Implantação disponível para usuários

Se um usuário não tiver Microsoft 365 Apps em seu dispositivo por qualquer motivo, você poderá usar um pacote para retornar o dispositivo ao seu estado esperado. Adicione o usuário ao grupo **Office-Office365_Install** e os aplicativos estarão disponíveis para eles no Portal da Empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps para Grandes Empresas (32 bits)

Área de Trabalho Gerenciada da Microsoft não dá suporte à implantação da versão de 32 bits do M365 Apps para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Atualizações para Microsoft 365 Apps

Microsoft 365 Apps são definidos para atualizar no [Canal mensal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)Enterprise Canal . Essa prática fornece aos usuários novos recursos Office todos os meses, mas eles receberão apenas uma atualização por mês em um cronograma de lançamento previsível. As atualizações são lançadas na segunda terça-feira do mês; essas atualizações podem incluir atualizações de recursos, segurança e qualidade. Essas atualizações ocorrem automaticamente e são retiradas diretamente do Office CDN para esse canal específico.

Área de Trabalho Gerenciada da Microsoft escalona cada versão para identificar possíveis problemas em seu ambiente. Concluimos a versão 28 dias após a versão do grupo de produtos Microsoft 365 App. Área de Trabalho Gerenciada da Microsoft agenda as versões de atualização para diferentes grupos para permitir tempo para validação e teste da seguinte maneira: 

- Teste: zero dias
- Primeiro: zero dias
- Rápido: 3 dias
- Broad: 7 dias

Área de Trabalho Gerenciada da Microsoft um prazo de atualização de sete dias [para](/deployoffice/configure-update-settings-microsoft-365-apps) dispositivos. Depois que a atualização estiver disponível, ela deverá ser instalada dentro de sete dias. Os usuários são [notificados](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de que as atualizações são necessárias em vários locais: o aplicativo, na bandeja do sistema 12 horas antes do prazo, e eles recebem um aviso de 15 minutos antes do prazo. Todas Microsoft 365 Apps devem ser fechadas para que a atualização seja concluída.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar ou reverter uma atualização

Se você precisar pausar ou reverter Microsoft 365 atualização do aplicativo [](../working-with-managed-desktop/admin-support.md) por qualquer motivo, arquivar uma solicitação de suporte de administrador por meio do portal Área de Trabalho Gerenciada da Microsoft.

Durante uma versão, Área de Trabalho Gerenciada da Microsoft monitora as taxas de erro de todas as Microsoft 365 Apps. Se observarmos uma diferença significativa na qualidade entre a nova versão e seu predecessor, podemos entrar em contato com você por meio do portal Área de Trabalho Gerenciada da Microsoft Administrador. Dependendo da gravidade, perguntaremos se você deseja pausar a versão ou informar que fizemos uma ação para atenuar um problema. 

### <a name="delivery-optimization"></a>Otimização de entrega

A Otimização de Entrega é uma tecnologia de distribuição ponto a ponto disponível no Windows 10. Ele permite que os dispositivos compartilhem conteúdo, como atualizações, que os dispositivos baixaram da Microsoft pela Internet. Usá-lo pode ajudar a reduzir a largura de banda de rede porque um dispositivo pode obter partes da atualização de outro dispositivo em sua rede local, em vez de ter que baixar a atualização completamente da Microsoft.

[A Otimização](/deployoffice/delivery-optimization) de Entrega é habilitada por padrão em dispositivos que executam Windows 10 Enterprise ou Windows 10 Education edições. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciado por Área de Trabalho Gerenciada da Microsoft

A Microsoft gerencia algumas configurações como parte do serviço. Área de Trabalho Gerenciada da Microsoft não gerencia uma linha de base de segurança Office, mas você pode definir uma por conta própria seguindo as diretrizes na seção Configurações [você gerencia.](#settings-you-manage)

### <a name="update-settings"></a>Atualizar configurações

Área de Trabalho Gerenciada da Microsoft mantém todas as configurações de atualização para [dispositivos gerenciados](/deployoffice/configure-update-settings-microsoft-365-apps) e você deve modificar essas configurações.

### <a name="set-updates-to-occur-automatically"></a>Definir atualizações para ocorrer automaticamente

**Valor padrão**: Habilitado

Essa política é configurada para garantir que todos os dispositivos Office possam ser mantidos atualizados da nuvem. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Definir um prazo quando as atualizações devem ser aplicadas

**Valor padrão**: 7 dias

A **política UpdateDeadline** é usada para configurar o período de carência que os usuários têm antes que uma atualização seja imposta no dispositivo. Essa política de prazo também dispara [notificações](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) ao usuário para informá-lo sobre as alterações necessárias em seu dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Adiar atualizações em um dispositivo por um período

Essa política é configurada de forma diferente para cada grupo de dispositivos de gerenciamento de atualização e é necessária para que Área de Trabalho Gerenciada da Microsoft atender às suas metas de atualização:  

- Teste: zero dias
- Primeiro: zero dias
- 7 dias rápidos
- Broad: 21 dias

### <a name="update-notifications-settings"></a>Atualizar configurações de notificações

**Valor padrão**: False

A configuração "ocultar notificações de atualização" é definida como **False** em dispositivos [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) Área de Trabalho Gerenciada da Microsoft para fornecer a melhor experiência de atualização para os usuários notificando-os quando as atualizações são necessárias.

### <a name="specify-a-location-to-look-for-updates"></a>Especificar um local para procurar atualizações

**Valor padrão**: Canal mensal Enterprise Canal

Uma combinação das políticas **UpdatePath** e **UpdateChannel** é usada conforme necessário para atingir o cronograma de atualização. Essas políticas são definidas para garantir que todos os Office recebam atualizações diretamente do CDN para o Canal de Enterprise Mensal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especifique a versão de destino do Microsoft 365 Apps

A política versão de destino às vezes é usada por Área de Trabalho Gerenciada da Microsoft para reverter ou fixar uma versão específica do Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar a opção para habilitar ou desabilitar Office atualizações automáticas

**Valor padrão**: Habilitado

Essa configuração é necessária para Área de Trabalho Gerenciada da Microsoft atender às suas metas de atualização para Microsoft 365 Aplicativos. 

### <a name="first-run-settings"></a>Configurações de primeira executar 

Há várias configurações que afetam o comportamento na primeira vez Office é executado.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceitar os termos de licença em nome do usuário final

**Valor padrão**: Desabilitado

Na primeira vez que um usuário abre um Microsoft 365 App, ele é solicitado a aceitar os termos de licença. Se você quiser aceitar os termos de licença em nome de seus usuários, arquiva uma solicitação de serviço com a equipe de operações Área de Trabalho Gerenciada da Microsoft solicitando que essa configuração seja habilitada. 

### <a name="suppress-outlook-mobile-check-box"></a>Suprimir Outlook caixa de seleção móvel

**Valor padrão**: Desabilitado

A primeira vez que um usuário abre Outlook é solicitado a instalar o Outlook Mobile. Se você não quiser que os usuários vejam essa caixa de seleção, arquivar uma solicitação de serviço com a equipe de operações Área de Trabalho Gerenciada da Microsoft solicitando que essa configuração seja habilitada para seus dispositivos. 

## <a name="other-settings"></a>Outras configurações

Há outras configurações Microsoft 365 App que Área de Trabalho Gerenciada da Microsoft podem ser configuradas opcionalmente em seu nome. 

### <a name="disable-personal-onedrive"></a>Desabilitar a OneDrive

**Valor padrão**: Desabilitado

Algumas organizações estão preocupados com os usuários que têm acesso a arquivos corporativos e pessoais em seus dispositivos. Você pode arquivar uma solicitação de serviço com a equipe Área de Trabalho Gerenciada da Microsoft Operações solicitando que essa configuração seja habilitada. 

## <a name="settings-you-manage"></a>Configurações gerenciar

Há muitas outras políticas que Área de Trabalho Gerenciada da Microsoft ainda não são definidas como parte do nosso serviço. Você pode configurar essas políticas usando o Microsoft Intune, que usa o serviço Office [Política de](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Nuvem. Para definir essas políticas, siga estas etapas:

1.  Entre no centro de Microsoft Endpoint Manager de administração.
2.  Selecione **Aplicativos > Políticas para Office aplicativos > Criar**
3.  Na página **Criar configuração** de política, faça o seguinte:
    - Insira um nome.
    - Forneça uma descrição (opcional).
    - Em **atribuições,** escolha se essa política se aplica a todos os usuários do Microsoft 365 Apps para Grandes Empresas ou apenas aos usuários que acessam documentos anonimamente usando Office para a Web.
    - Selecione o grupo de segurança baseado em AAD atribuído à configuração da política. Cada configuração de política só pode ser atribuída a um grupo, e cada grupo só pode ser atribuído a uma configuração de política.
    - Configure as configurações de política a serem incluídas na configuração da política. Você pode pesquisar o nome da configuração de política para encontrar a configuração de política que deseja configurar. Você também pode filtrar no aplicativo se a política é uma linha de base de segurança recomendada e se a política foi configurada. A coluna da plataforma indica se a política é aplicada Microsoft 365 Apps para Grandes Empresas dispositivos Windows, Office para a Web ou tudo.
4.  Depois de fazer suas seleções, escolha **Criar**.

> [!NOTE]
> Office As Políticas de Configuração só suportam a implantação baseada no usuário