---
title: Testar e implantar aplicativos do Microsoft 365 por parceiros no portal aplicativos integrados
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Encontre, teste e implante aplicativos de parceiros microsoft e microsoft para usuários e grupos em sua organização a partir do portal aplicativos integrados no centro de administração do Microsoft 365.
ms.openlocfilehash: da67cbe5f8b6e5f2da42e1f4b57a55d7d4a768fb
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644471"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testar e implantar aplicativos do Microsoft 365 por parceiros no portal aplicativos integrados

O Centro de administração do Microsoft 365 oferece a flexibilidade para implantar aplicativos de armazenamento único, linha de negócios personalizada de aplicativos e aplicativos parceiros do Microsoft 365 de um único local. O local pode ser acessado no Centro de Administração da Microsoft > Configurações > aplicativos integrados. A capacidade de encontrar, testar e implantar totalmente aplicativos comprados e licenciados por parceiros da Microsoft no portal aplicativos integrados fornece a conveniência e os benefícios necessários para manter os serviços comerciais atualizados regularmente e em execução com eficiência.

Para obter informações adicionais sobre como comprar e licenciar aplicativos do Microsoft 365 de parceiros para sua organização, consulte [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Para obter mais informações sobre como os parceiros criam esses aplicativos, consulte [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

O portal aplicativos integrados só está acessível para administradores globais e está disponível apenas para clientes de todo o mundo. Esse recurso não está disponível em nuvens soberanas e governamentais.

O portal aplicativos integrados exibe uma lista de aplicativos, que inclui aplicativos individuais e aplicativos do Microsoft 365 de parceiros implantados em sua organização. Somente aplicativos Web, aplicativos SPFx, complementos do Office e aplicativos do Teams estão listados. Para aplicativos Web, você pode ver dois tipos de aplicativos.

- Aplicativos SaaS que estão disponíveis no appsource.microsoft.com e podem ser implantados por administradores que dão consentimento em nome da organização.
- Aplicativos de galeria SAML vinculados aos complementos do office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gerenciar aplicativos no portal aplicativos integrados

Você pode gerenciar testes e implantação de aplicativos do Microsoft 365 adquiridos e licenciados de parceiros.

1. No centro de administração, na tela esquerda, escolha **Configurações** e, em seguida, escolha **Aplicativos integrados.**

2. Escolha um aplicativo **com Status** de **Mais aplicativos disponíveis** para abrir o painel **Gerenciar.** O status de **mais aplicativos** disponíveis permite que você saiba que há mais integrações dos ISVs que ainda não foram implantados.

3. Na guia **Visão Geral,** selecione **Implantar**. Alguns aplicativos exigem que você adicione usuários antes de selecionar Implantar.

4. Selecione  **Usuários**, escolha **É uma implantação de teste** e escolha **Toda** a organização , **Usuários/grupos específicos** **ou Somente eu**. Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização. Usuários ou grupos específicos podem ser um grupo do Microsoft 365, um grupo de segurança ou um grupo de distribuição.

5. Selecione **Atualizar** **e,** em seguida, Feito . Agora você pode selecionar Implantar na guia Visão Geral.

6. Revise as informações do aplicativo e selecione **Implantar**.

7. Selecione **Concluído na** página Implantação concluída e revise os detalhes do teste ou implantação completa na guia **Visão** geral.

8. Se o aplicativo tiver um status de **Atualização** pendente, você poderá clicar no aplicativo para abrir o painel Gerenciar e atualizar o aplicativo.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Encontre aplicativos publicados para teste e implantação completa

Você pode encontrar, testar e implantar totalmente aplicativos publicados que ainda não aparecem na lista na página Aplicativos integrados. Ao comprar e licenciar os aplicativos do centro de administração, você pode adicionar aplicativos de parceiros Microsoft e Microsoft à sua lista de um único local.

1. No centro de administração, na tela esquerda, escolha **Configurações** e, em seguida, escolha **Aplicativos integrados.**

2. Selecione **Obter aplicativos** para obter uma exibição dos aplicativos.

3. Na página **Aplicativos publicados do Microsoft 365 Apps,** selecione o aplicativo que você deseja implantar escolhendo **Obter agora**. Os aplicativos exibidos principalmente são Word, PowerPoint, Excel, complementos do Outlook, aplicativos do Teams e aplicativos do SharePoint (baseados na tecnologia da Estrutura do SharePoint). Aceite as permissões e selecione **Continuar**.

5. Selecione **Implantar** na parte superior da página ao lado da mensagem que se refere à espera de ser implantada.

    Se o aplicativo selecionado estiver vinculado a uma oferta SaaS por um ISV, todos os outros aplicativos que fazem parte dessa oferta vinculada aparecerão na página Configuração. Se você optar por implantar todos os aplicativos, selecione **Próximo**. Caso contrário, **selecione Editar** e escolha quais aplicativos você deseja implantados. Alguns aplicativos exigem que você adicione usuários antes de selecionar **Implantar**.

6. Selecione **Adicionar usuários**, escolha É uma **implantação de teste** e escolha **Toda** a organização ou **Usuários/grupos específicos** ou **Apenas eu**.

    Usuários/grupos específicos podem ser um grupo do Microsoft 365, um grupo de segurança ou um grupo distribuído. Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização.

7. Selecione **Próximo** para chegar à página **Aceitar solicitação de** permissão. Os recursos do aplicativo e as permissões de cada um dos aplicativos estão listados. Se o aplicativo precisar de consentimento, selecione **Aceitar permissões**. Somente um administrador global pode dar consentimento.

8. Selecione **Próximo para** revisar a implantação e escolha Concluir **implantação**. Você pode exibir a implantação na guia **Visão** Geral escolhendo **Exibir essa implantação**. No Centro de administração do Microsoft 365, você pode ver o status de cada aplicativo implantado e a data em que implantou o aplicativo.

> [!NOTE]
> Se um aplicativo tiver sido implantado anteriormente em outro lugar que não seja o portal aplicativos integrados, o Tipo **de Implantação** será **Personalizado.**

## <a name="unsupported-scenarios"></a>Cenários sem suporte

Você não poderá implantar um único aplicativo de loja ou Aplicativos do Microsoft 365 por parceiro no portal de aplicativos integrados para os seguintes cenários.

- O mesmo complemento está vinculado a mais de uma oferta SaaS.
- A oferta saaS está vinculada a complementos, mas não se integra ao Microsoft Graph e nenhuma ID do aplicativo AAD é fornecida.
- A oferta saaS está vinculada a complementos, mas a ID do aplicativo AAD fornecida para a integração do Microsoft Graph é compartilhada em várias ofertas saaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Carregar aplicativos de linha de negócios personalizados para testes e implantação completa

1. No centro de administração, na nav esquerda, escolha **Configurações** e, em seguida, **aplicativos integrados.**

2. Selecione **Carregar aplicativos personalizados**. Há suporte apenas para uma linha personalizada de aplicativos para Word, PowerPoint, Excel e Outlook.

3. Carregue o arquivo de manifesto do dispositivo ou adicione um link de URL. Alguns aplicativos exigem que você adicione usuários antes de selecionar Implantar.

4. Selecione **Adicionar usuários**, escolha É uma **implantação de** teste e escolha **Toda** a organização ou **Usuários/grupos específicos** ou **Somente eu**.

    Usuários/grupos específicos podem ser um grupo do Microsoft 365, um grupo de segurança ou um grupo distribuído. Você também pode escolher **Testar implantação** se quiser esperar para implantar o aplicativo em toda a organização.

5. Selecione **Próximo** para chegar à página **Aceitar solicitação de** permissão. Os recursos do aplicativo e as permissões dos aplicativos estão listados. Se o aplicativo precisar de consentimento, selecione **Aceitar permissões**. Somente um administrador global pode dar consentimento.

6. Selecione **Próximo para** revisar a implantação e escolha Concluir **implantação**. Você pode exibir a implantação na guia **Visão** Geral escolhendo **Exibir essa implantação**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Qual função de administrador preciso acessar aplicativos integrados?

Somente administradores globais podem acessar Aplicativos Integrados. Os aplicativos integrados não aparecerão na nav esquerda para outros administradores.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Por que vejo o Add-in no nav esquerdo em Configuração, mas não aplicativos integrados?

Pode haver alguns motivos:

- O administrador conectado é um administrador do Exchange.
- O cliente está na nuvem soberana e a experiência de aplicativos integrados ainda está disponível para clientes de nuvem soberanas.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Quais aplicativos posso implantar a partir de aplicativos integrados?

Aplicativos integrados permitem a implantação de aplicativos Web, aplicativo do Teams, Excel, PowerPoint, Word, complementos do Outlook e aplicativos SPFx. Para os complementos, os aplicativos integrados suportam a implantação para caixas de correio online do Exchange e não caixas de correio locais do Exchange.

### <a name="can-administrators-delete-or-remove-apps"></a>Os administradores podem excluir ou remover aplicativos?

Sim. Os administradores globais podem excluir ou remover aplicativos.

- Selecione um aplicativo na exibição de lista. Na guia **Configuração,** selecione quais aplicativos remover.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Os aplicativos integrados estão disponíveis na nuvem soberana?

Não. Os aplicativos integrados não estão disponíveis para clientes de nuvem soberanas.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Os aplicativos integrados estão disponíveis nas nuvens do governo?

Não. Os aplicativos integrados não estão disponíveis para clientes de nuvem do governo.
