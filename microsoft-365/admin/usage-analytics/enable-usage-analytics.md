---
title: Habilitar a análise de uso do Microsoft 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Saiba como começar a coletar dados para seu locatário usando o aplicativo de modelo de Análise de Uso do Microsoft 365 no Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114232"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar a análise de uso do Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

A análise de uso do Microsoft 365 ainda não está disponível para o Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Etapas para habilitar a análise de uso do Microsoft 365

Para começar a usar a análise de uso do Microsoft 365, primeiro você deve disponibilizar os dados no Centro de administração do Microsoft 365 e, em seguida, iniciar o aplicativo de modelo no Power BI.
  
### <a name="get-power-bi"></a>Obter o Power BI

Se ainda não tiver o Power BI, [inscreva-se](https://go.microsoft.com/fwlink/p/?linkid=845347)no Power BI Pro. Selecione **Experimentar gratuitamente** para se inscrever em uma avaliação ou **Comprar agora** para obter o Power BI Pro.
  
  
Você também pode expandir **Produtos** para comprar uma versão do Power BI. 

> [!NOTE]
> Você precisa de uma licença do Power BI Pro para instalar, personalizar e distribuir um aplicativo de modelo. Para obter mais informações, consulte [Pré-requisitos.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Para compartilhar seus dados, você e as pessoas com quem você compartilha os dados precisam de uma licença do Power BI Pro ou o conteúdo precisa estar em um espaço de trabalho em um serviço Premium do [Power BI.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Habilitar o aplicativo de modelo

Para habilitar o aplicativo de modelo, você precisa ser um **administrador global.**
  
Consulte [as funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
    
2. Na página **Uso,** localize o cartão de análise de uso do **Microsoft 365** e selecione **Começar.**
    
3. No painel Relatórios que é aberto, de definir Disponibilizar dados para a análise de uso do **Microsoft 365** para Power BI como **Ao** \> **salvar.** 
  
O processo de coleta de dados será concluído em duas a 48 horas, dependendo do tamanho do locatário. O **botão Ir para o Power BI** será habilitado (não mais cinza) quando a coleta de dados for concluída. 
    
### <a name="start-the-template-app"></a>Iniciar o aplicativo de modelo

Para iniciar o aplicativo de modelo, você precisa ser um administrador **global** **,** leitor de relatório, administrador do **Exchange**, administrador do Skype **for Business** ou administrador **do SharePoint**. 
  
1. Copie a ID do locatário e selecione **Ir para o Power BI.**
    
2.  Quando chegar ao Power BI, entre. Em **seguida, selecione** -> **Aplicativos Obter** aplicativos no menu de navegação.    
  
3. Na guia **Aplicativos,** digite Microsoft 365 na caixa de pesquisa e selecione Análise de uso do **Microsoft 365** \> **Obter agora.**

    [![Selecione Obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Depois que o aplicativo for instalado. Selecione o tile para abri-lo.

5.  Selecione **Explorar aplicativo para** exibir o aplicativo com dados de exemplo. Escolha **Conectar** para conectar o aplicativo aos dados da sua organização.

6.  Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1) and select **Next**.
    
7. Na tela seguinte, selecione **OAuth2** como o método **de autenticação** \> **Entrar.** Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo falhará.
    
    ![Escolha a conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Depois que o aplicativo de modelo for instaurido, o painel de análise de uso do Microsoft 365 estará disponível no Power BI na Web. O carregamento inicial do painel levará de 2 a 30 minutos.
  
Os agregados de nível de locatário estarão disponíveis em todos os relatórios após a aceitação. **Os detalhes no nível do usuário só estarão disponíveis por** volta do dia 5 do próximo mês do calendário após a aceitação. Isso afetará todos os relatórios da Atividade do Usuário (confira Navegar e utilizar os relatórios na análise de uso do [Microsoft 365](navigate-and-utilize-reports.md) para ver dicas sobre como exibir e usar esses relatórios).
    
## <a name="make-the-collected-data-anonymous"></a>Tornar os dados coletados anônimos

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Isso ocultará informações identificáveis, como nomes de usuário, grupo e site em relatórios e no aplicativo de modelo.
  
1. In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos.** Essa configuração é aplicada aos relatórios de uso e ao aplicativo de modelo.
  
3. Selecione **Salvar alterações**.
