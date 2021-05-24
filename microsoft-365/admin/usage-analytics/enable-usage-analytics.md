---
title: Habilitar Microsoft 365 análise de uso
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Saiba como começar a coletar dados para seu locatário usando o aplicativo Microsoft 365 modelo de Análise de Uso no Power BI.
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635409"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar Microsoft 365 análise de uso

Microsoft 365 análise de uso ainda não está disponível para Microsoft 365 us government Community.
  
## <a name="before-you-begin"></a>Antes de começar

Para começar a usar Microsoft 365 análise de uso, primeiro você deve disponibilizar os dados no centro de administração Microsoft 365 e, em seguida, iniciar o aplicativo de modelo Power BI.
  
## <a name="get-power-bi"></a>Obter o Power BI

Se você ainda não tiver Power BI, poderá inscrever-se [no](https://go.microsoft.com/fwlink/p/?linkid=845347)Power BI Pro . Selecione **Experimentar gratuitamente** para se inscrever em uma avaliação ou **Comprar agora** para obter Power BI Pro.
  
  
Você também pode expandir **Produtos** para comprar uma versão do Power BI. 

> [!NOTE]
> Você precisa de uma Power BI Pro para instalar, personalizar e distribuir um aplicativo de modelo. Para obter mais informações, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartilhar seus dados, você e as pessoas com quem você compartilha os dados precisam de uma licença de Power BI Pro, ou o conteúdo precisa estar em um espaço de trabalho em um serviço [Power BI premium](/power-bi/service-premium-what-is). 
  
## <a name="enable-the-template-app"></a>Habilitar o aplicativo de modelo

Para habilitar o aplicativo de modelo, você precisa ser um **administrador global.**
  
Confira [mais informações sobre funções de](../add-users/about-admin-roles.md) administrador. 
  
1. No centro de administração, vá para a guia Serviços de configurações **Configurações** \>  \>  Org. 
    
2. Na guia **Serviços,** selecione  **Relatórios**.
    
3. No painel Relatórios que é aberto, de definir Tornar dados de relatório disponíveis para Microsoft 365 análise de uso **para** Power BI **como Ao** \> **salvar**. 
  
O processo de coleta de dados será concluído em duas a 48 horas, dependendo do tamanho do locatário. O **botão Ir para Power BI** será habilitado (não mais cinza) quando a coleta de dados for concluída. 
    
## <a name="start-the-template-app"></a>Iniciar o aplicativo de modelo

Para iniciar **o** aplicativo de modelo, você precisa ser um administrador **global,** um leitor de **relatório,** um administrador **Exchange,** um administrador Skype for Business ou um **SharePoint administrador**. 
  
1. Copie a ID do locatário e selecione **Ir para Power BI**.
    
2.  Quando chegar ao Power BI, entre. Em **seguida, selecione** -> **Aplicativos Obter aplicativos** no menu de navegação.    
  
3. Na guia **Aplicativos,** digite Microsoft 365 na caixa de pesquisa e selecione Microsoft 365 **análise de** uso \> **Obter agora**.

    [![Selecione Obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Depois que o aplicativo for instalado. Selecione o azulejo para abri-lo.

5.  Selecione **Explorar aplicativo** para exibir o aplicativo com dados de exemplo. Escolha **Conexão** conectar o aplicativo aos dados da sua organização.

6.  Escolha **Conexão**, no Conexão para Microsoft 365 análise de uso, digite **a** ID do locatário (sem traços) que você copiou na etapa (1) e selecione **Próximo**.
    
7. Na próxima tela, selecione **OAuth2** como o método **Authentication Entrar** \> . Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo falhará.
    
    ![Escolher conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Depois que o aplicativo de modelo é instaurou Microsoft 365 painel de análise de uso estará disponível Power BI na Web. O carregamento inicial do painel levará entre 2 a 30 minutos.
  
Os agregados de nível de locatário estarão disponíveis em todos os relatórios após a aceitação. **Os detalhes no nível do usuário** só estarão disponíveis por volta do dia 5 do próximo mês de calendário após a aceitação em . Isso afetará todos os relatórios em Atividade do Usuário (Consulte Navegar e utilizar os relatórios em Microsoft 365 [análise](navigate-and-utilize-reports.md) de uso para dicas sobre como exibir e usar esses relatórios).
    
## <a name="make-the-collected-data-anonymous"></a>Tornar os dados coletados anônimos

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Isso ocultará informações identificáveis, como nomes de usuário, grupo e site em relatórios e no aplicativo de modelo.
  
1. No centro de administração, vá para **a** Configurações \> **Org Configurações** e, em **Serviços,** escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos.** Essa configuração é aplicada tanto aos relatórios de uso quanto ao aplicativo de modelo.
  
3. Selecione **Salvar alterações**.

## <a name="related-content"></a>Conteúdo relacionado

[Sobre análise de uso](usage-analytics.md) (artigo)\
[Obter a versão mais recente da análise de uso](get-the-latest-version-of-usage-analytics.md) (artigo)\
[Navegue e utilize os relatórios Microsoft 365 análise de uso](navigate-and-utilize-reports.md) (artigo)