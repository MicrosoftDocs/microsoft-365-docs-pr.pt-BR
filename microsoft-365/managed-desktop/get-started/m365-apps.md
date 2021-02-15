---
title: Microsoft 365 Apps para empresas
description: Como implantar o Microsoft 365 Apps, como eles são atualizados e como as configurações são gerenciadas
keywords: histórico de alterações
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840330"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

## <a name="initial-deployment"></a>Implantação inicial

A Área de Trabalho Gerenciada da Microsoft garante que os Aplicativos do Microsoft 365 para empresas (64 bits) sejam instalados como parte da imagem em todos os dispositivos [de programa.](../service-description/device-list.md) Todos os seguintes aplicativos devem estar presentes no dispositivo quando ele for entregue:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Acessar
- Skype for Business
- OneNote

Essa abordagem minimiza o impacto na rede e garante que os usuários possam ser produtivos assim que receberem seus dispositivos. Em seguida, implantamos mais políticas em dispositivos gerenciados para configurar os aplicativos para uso.

> [!NOTE]
> O Microsoft Teams é implantado separadamente do Microsoft 365 Apps para empresas e não está incluído na imagem base. 

### <a name="available-deployment-to-users"></a>Implantação disponível para usuários

Se um usuário não tiver os Aplicativos do Microsoft 365 em seu dispositivo por qualquer motivo, você poderá usar um pacote para retornar o dispositivo ao estado esperado. Adicione o usuário ao grupo **Modern Workplace-Office-Office365_Install** e os aplicativos serão disponibilizados no Portal da Empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Aplicativos do Microsoft 365 para empresas (32 bits)

A Área de Trabalho Gerenciada da Microsoft não dá suporte à implantação da versão de 32 bits do M365 Apps para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Atualizações do Microsoft 365 Apps

Os Aplicativos do Microsoft 365 estão definidos para atualização no [Canal Empresarial Mensal.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Essa prática fornece aos usuários novos recursos do Office a cada mês, mas eles receberão apenas uma atualização por mês em um cronograma de lançamento previsível. As atualizações são lançadas na segunda terça-feira do mês; essas atualizações podem incluir atualizações de recursos, segurança e qualidade. Essas atualizações ocorrem automaticamente e são retiradas diretamente da CDN do Office para esse canal específico.

A Área de Trabalho Gerenciada da Microsoft escalona cada versão para identificar possíveis problemas em seu ambiente. Concluiremos a lançamento 28 dias após o lançamento do grupo de produtos do Aplicativo do Microsoft 365. A Área de Trabalho Gerenciada da Microsoft agenda versões de atualização para grupos diferentes para permitir tempo para validação e teste da seguinte maneira: 

- Teste: zero dias
- Primeiro: zero dias
- Rápido: 7 dias
- Ampla: 21 dias

A Área de Trabalho Gerenciada da Microsoft define um prazo de atualização [de sete dias](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) para dispositivos. Depois que a atualização estiver disponível, ela deverá ser instalada no prazo de sete dias. Os usuários são [notificados](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de que as atualizações são necessárias em vários locais: o aplicativo, na bandeja do sistema 12 horas antes da data limite, e eles recebem um aviso de 15 minutos antes da data limite. Todos os Aplicativos do Microsoft 365 devem ser fechados para que a atualização seja concluída.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar ou reverter uma atualização

Se você precisar pausar ou reverter a atualização do aplicativo [](../working-with-managed-desktop/admin-support.md) Microsoft 365 por qualquer motivo, protocole uma solicitação de suporte do administrador por meio do portal da Área de Trabalho Gerenciada da Microsoft.

Durante uma versão, a Área de Trabalho Gerenciada da Microsoft monitora as taxas de erro de todos os Aplicativos do Microsoft 365. Se observarmos uma diferença significativa na qualidade entre a nova versão e seu predecessor, podemos entrar em contato com você por meio do portal do Administrador da Área de Trabalho Gerenciada da Microsoft. Dependendo da gravidade, perguntaremos se você deseja pausar a versão ou informá-lo de que a ação foi tomada para atenuar um problema. 

### <a name="delivery-optimization"></a>Otimização de entrega

A Otimização de Entrega é uma tecnologia de distribuição ponto a ponto disponível no Windows 10. Ele permite que os dispositivos compartilhem conteúdo, como atualizações, que os dispositivos baixaram da Microsoft pela Internet. Usá-lo pode ajudar a reduzir a largura de banda da rede porque um dispositivo pode obter partes da atualização de outro dispositivo em sua rede local, em vez de precisar baixar a atualização completamente da Microsoft.

[A Otimização](https://docs.microsoft.com/deployoffice/delivery-optimization) de Entrega é habilitada por padrão em dispositivos que executam as edições Windows 10 Enterprise ou Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciadas pela Área de Trabalho Gerenciada da Microsoft

A Microsoft gerencia algumas configurações como parte do serviço. A Área de Trabalho Gerenciada da Microsoft não gerencia uma linha de base de Segurança do Office, mas você pode definir uma por conta própria seguindo as orientações na seção [Configurações gerenciadas.](#settings-you-manage)

### <a name="update-settings"></a>Atualizar configurações

A Área de Trabalho Gerenciada da Microsoft mantém todas as configurações de atualização para [dispositivos gerenciados](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) e você deve modificar essas configurações.

### <a name="set-updates-to-occur-automatically"></a>Definir que as atualizações ocorram automaticamente

**Valor padrão:** Habilitado

Essa política é configurada para garantir que todos os dispositivos do Office possam ser mantidos atualizados a partir da nuvem. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Definir uma data limite quando as atualizações devem ser aplicadas

**Valor padrão:** 7 dias

A **política UpdateDeadline** é usada para configurar o período de carência que os usuários têm antes que uma atualização seja imposta no dispositivo. Essa política de data limite também dispara [notificações](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) ao usuário para informá-lo sobre as alterações necessárias em seu dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Adiar atualizações em um dispositivo por um período

Essa política é configurada de forma diferente para cada grupo de dispositivos de gerenciamento de atualização e é necessária para que a Área de Trabalho Gerenciada da Microsoft conheça seus destinos de atualização:  

- Teste: zero dias
- Primeiro: zero dias
- 7 dias rápidos
- Ampla: 21 dias

### <a name="update-notifications-settings"></a>Atualizar configurações de notificações

**Valor padrão:** False

A configuração "ocultar notificações de atualização" é definida como **False** em dispositivos da Área de Trabalho Gerenciada da Microsoft para fornecer a melhor experiência de atualização para os usuários, notificando-os quando as atualizações são necessárias. [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)

### <a name="specify-a-location-to-look-for-updates"></a>Especificar um local para procurar atualizações

**Valor padrão:** Canal Empresarial Mensal

Uma combinação das **políticas UpdatePath** e **UpdateChannel** é usada conforme necessário para atingir o cronograma de atualização. Essas políticas são definidas para garantir que todos os dispositivos do Office recebam atualizações diretamente da CDN para o Canal Empresarial Mensal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especificar a versão de destino do Microsoft 365 Apps

Às vezes, a política de Versão de Destino é usada pela Área de Trabalho Gerenciada da Microsoft para reverter ou fixar uma versão específica do Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar a opção para habilitar ou desabilitar as atualizações automáticas do Office

**Valor padrão:** Habilitado

Essa configuração é necessária para a Área de Trabalho Gerenciada da Microsoft cumprir seus destinos de atualização para aplicativos do Microsoft 365. 

### <a name="first-run-settings"></a>Configurações de primeira executar 

Há várias configurações que afetam o comportamento na primeira vez que o Office é executado.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceitar os termos de licença em nome do usuário final

**Valor padrão:** Desabilitado

Na primeira vez que um usuário abre um aplicativo do Microsoft 365, ele é solicitado a aceitar os termos de licença. Se você quiser aceitar os termos de licença em nome de seus usuários, protocole uma solicitação de serviço com a equipe de Operações de Área de Trabalho Gerenciada da Microsoft solicitando que essa configuração seja habilitada. 

### <a name="suppress-outlook-mobile-check-box"></a>Suprimir caixa de seleção do Outlook Mobile

**Valor padrão:** Desabilitado

Na primeira vez que um usuário abre o Outlook, ele é solicitado a instalar o Outlook Mobile. Se você não quiser que os usuários vejam essa caixa de seleção, arquiva uma solicitação de serviço com a equipe de Operações de Área de Trabalho Gerenciada da Microsoft solicitando que essa configuração seja habilitada para seus dispositivos. 

## <a name="other-settings"></a>Outras configurações

Há outras configurações de aplicativo do Microsoft 365 que a Área de Trabalho Gerenciada da Microsoft pode, opcionalmente, definir em seu nome. 

### <a name="disable-personal-onedrive"></a>Desabilitar o OneDrive Pessoal

**Valor padrão:** Desabilitado

Algumas organizações estão interessadas em que os usuários tenham acesso a arquivos corporativos e pessoais em seus dispositivos. Você pode registrar uma solicitação de serviço com a equipe de Operações da Área de Trabalho Gerenciada da Microsoft solicitando que essa configuração seja habilitada. 

## <a name="settings-you-manage"></a>Configurações gerenciadas

Há muitas outras políticas que a Área de Trabalho Gerenciada da Microsoft ainda não definiu como parte do nosso serviço. Você pode configurar essas políticas usando o Microsoft Intune, que usa o serviço de Política de [Nuvem do Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Para definir essas políticas, siga estas etapas:

1.  Entre no centro de administração do Microsoft Endpoint Manager.
2.  Selecionar **Políticas > Aplicativos para Aplicativos do Office > Criar**
3.  Na página **Criar configuração** de política, faça o seguinte:
    - Insira um nome.
    - Forneça uma descrição (opcional).
    - Nas **atribuições,** escolha se essa política se aplica a todos os usuários do Microsoft 365 Apps para empresas ou apenas aos usuários que acessam documentos anonimamente usando o Office para a Web.
    - Selecione o grupo de segurança baseado em AAD atribuído à configuração de política. Cada configuração de política só pode ser atribuída a um grupo, e cada grupo só pode ser atribuído a uma configuração de política.
    - Definir as configurações de política a serem incluídas na configuração de política. Você pode pesquisar o nome da configuração de política para encontrar a configuração de política que deseja definir. Você também pode filtrar o aplicativo, se a política é uma linha de base de segurança recomendada e se a política foi configurada. A coluna da plataforma indica se a política é aplicada ao Microsoft 365 Apps para empresas para dispositivos Windows, Office para a Web ou todos.
4.  Depois de fazer suas seleções, escolha **Criar**.

> [!NOTE]
> As Políticas de Configuração do Office suportam apenas a implantação baseada no usuário
