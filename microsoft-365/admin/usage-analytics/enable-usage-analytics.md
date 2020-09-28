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
ms.openlocfilehash: 1e59811d6812c6a9d68878f6766181e85efb668b
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295321"
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

Você precisa de uma licença do Power BI pro para compartilhar seu conteúdo e as pessoas com as quais você o compartilha, ou o conteúdo precisa estar em um espaço de trabalho em uma [capacidade Premium](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Habilitar o aplicativo de modelo

Para habilitar o aplicativo de modelo, você deve ser um **administrador global**, um **leitor de relatórios**, um **administrador do Exchange**, **administrador do Skype for Business**ou **administrador do SharePoint**. 
  
Consulte [sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
    
2. Na página **uso** , localize o cartão de **análise de uso do Microsoft 365** e selecione **introdução**.
    
3. No painel de relatórios que é aberto, defina **disponibilizar dados para a análise de uso do Microsoft 365 para o Power bi** **para ao** \> **salvar**. 
  
Isso iniciará o processo de coleta de dados e será concluído em 2 a 48 horas, dependendo do tamanho do seu locatário. O botão **ir para Power bi** será habilitado (não mais cinza) quando a coleta de dados estiver concluída. 
    
### <a name="initiate-the-template-app"></a>Iniciar o aplicativo de modelo

Para iniciar o aplicativo de modelo, você deve ser um **administrador global**, um **leitor de relatórios**, um **administrador do Exchange**, **administrador do Skype for Business**ou **administrador do SharePoint**. 
  
1. Copie a ID do locatário e selecione **ir para o Power bi**.
    
2.  Quando chegar ao Power BI, entre. Selecione aplicativos->obter aplicativos no menu de navegação.    
  
3. Na guia **aplicativos** , digite Microsoft 365 na caixa de pesquisa e selecione análise de **uso do Microsoft 365** \> **agora**.

    [![Selecionar obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Depois que o aplicativo é instalado. Clique no bloco para abri-lo.

5.  Clique em **explorar aplicativo** para exibir o aplicativo com dados de exemplo. Clique em **conectar** para conectar o aplicativo aos dados da sua organização.

6.  Após clicar em **conectar**, na tela **conectar ao Microsoft 365 Usage Analytics** , digite a ID do locatário (sem traços) que você copiou na etapa (1) e selecione **Avançar**.
    
7. Na tela seguinte, selecione **OAuth2** como o **método de autenticação** \> **entrar**. Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo irá falhar.
    
    ![Escolha a conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Depois que o aplicativo de modelo é instanciado, o painel de análise de uso do Microsoft 365 estará disponível no Power BI na Web. O carregamento inicial do painel levará entre 2 e 30 minutos.
  
Os agregados de nível do locatário estarão disponíveis em todos os relatórios. Os **detalhes no nível do usuário só ficarão disponíveis após o 1º ou o 15º dia do mês do calendário após o recebimento**. Isso afetará todos os relatórios da atividade do usuário (consulte [navegar e usar a análise de uso dos relatórios no Microsoft 365](navigate-and-utilize-reports.md) para obter dicas sobre como exibir e usar esses relatórios).
    
## <a name="make-the-collected-data-anonymous"></a>Tornar os dados coletados anônimos

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Isso ocultará as informações de identificação, como nomes de site, de grupo e de usuário em relatórios e no aplicativo de modelo.
  
1. No centro de administração, vá para as **Settings** configurações da \> **organização**configurações e, na guia **Serviços** , escolha **relatórios**.
    
2. Selecione **relatórios**e, em seguida, escolha **Exibir identificadores anônimos**. Essa configuração é aplicada tanto para os relatórios de uso quanto para o aplicativo de modelo.
  
3. Selecione **Salvar alterações**.
