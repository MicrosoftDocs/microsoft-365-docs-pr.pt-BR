---
title: Habilitar análise de uso do Microsoft 365
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
description: Saiba como iniciar a coleta de dados para o seu locatário usando o aplicativo de modelo de análise de uso do Microsoft 365 no Power BI.
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941326"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar análise de uso do Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

A análise de uso do Microsoft 365 ainda não está disponível para a Comunidade do governo dos EUA da Microsoft 365.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Etapas para habilitar a análise de uso do Microsoft 365

Para começar a usar a análise de uso do Microsoft 365, primeiro você deve tornar os dados disponíveis no centro de administração do Microsoft 365 e, em seguida, iniciar o aplicativo de modelo no Power BI.
  
### <a name="get-power-bi"></a>Obter o Power BI

Se você ainda não tem o Power BI, é possível [inscrever-se no Power bi pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Selecione **tentar liberar** para inscrever-se em uma avaliação ou **Compre agora** para obter o Power bi pro.
  
  
Você também pode expandir **Produtos** para comprar uma versão do Power BI. 

> [!NOTE]
> Você precisa de uma licença do Power BI pro para instalar, personalizar e distribuir um aplicativo de modelo. Para obter mais informações, consulte [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartilhar seus dados, você e as pessoas com as quais você compartilha os dados, precisam de uma licença do Power BI pro ou o conteúdo precisa estar em um espaço de trabalho em um [serviço Premium do Power bi](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Habilitar o aplicativo de modelo

Para habilitar o aplicativo de modelo, você precisa ser um **administrador global**.
  
Consulte [sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
    
2. Na página **uso** , localize o cartão de **análise de uso do Microsoft 365** e selecione **introdução**.
    
3. No painel de relatórios que é aberto, defina **disponibilizar dados para a análise de uso do Microsoft 365 para o Power bi** **para ao** \> **salvar**. 
  
O processo de coleta de dados será concluído em duas a 48 horas, dependendo do tamanho do seu locatário. O botão **ir para Power bi** será habilitado (não mais cinza) quando a coleta de dados estiver concluída. 
    
### <a name="start-the-template-app"></a>Iniciar o aplicativo de modelo

Para iniciar o aplicativo de modelo, você deve ser um **administrador global** , um **leitor de relatórios** , um **administrador do Exchange** , **administrador do Skype for Business** ou **administrador do SharePoint**. 
  
1. Copie a ID do locatário e selecione **ir para o Power bi**.
    
2.  Quando chegar ao Power BI, entre. Em seguida, **selecione aplicativos** -> **obter aplicativos** no menu de navegação.    
  
3. Na guia **aplicativos** , digite Microsoft 365 na caixa de pesquisa e selecione análise de **uso do Microsoft 365** \> **agora**.

    [![Selecionar obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Depois que o aplicativo é instalado. Selecione o bloco para abri-lo.

5.  Selecione **explorar aplicativo** para exibir o aplicativo com dados de exemplo. Escolha **conectar** para conectar o aplicativo aos dados da sua organização.

6.  Escolha **conectar** , na tela **conectar ao Microsoft 365 Usage Analytics** e, em seguida, digite a ID do locatário (sem traços) que você copiou na etapa (1) e selecione **Avançar**.
    
7. Na tela seguinte, selecione **OAuth2** como o **método de autenticação** \> **entrar**. Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo irá falhar.
    
    ![Escolha a conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Depois que o aplicativo de modelo é instanciado, o painel de análise de uso do Microsoft 365 estará disponível no Power BI na Web. O carregamento inicial do painel levará entre 2 e 30 minutos.
  
Os agregados de nível do locatário estarão disponíveis em todos os relatórios. Os **detalhes no nível do usuário só ficarão disponíveis após o 1º ou o 15º dia do mês do calendário após o recebimento**. Isso afetará todos os relatórios da atividade do usuário. Consulte [navegar e usar os relatórios no Microsoft 365 análise de uso](navigate-and-utilize-reports.md) para obter dicas sobre como exibir e usar esses relatórios.
    
## <a name="make-the-collected-data-anonymous"></a>Tornar os dados coletados anônimos

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Isso ocultará as informações de identificação, como nomes de site, de grupo e de usuário em relatórios e no aplicativo de modelo.
  
1. No centro de administração, vá para as **Settings** configurações da \> **organização** configurações e, na guia **Serviços** , escolha **relatórios**.
    
2. Selecione **relatórios** e, em seguida, escolha **Exibir identificadores anônimos**. Essa configuração é aplicada tanto para os relatórios de uso quanto para o aplicativo de modelo.
  
3. Selecione **Salvar alterações**.
