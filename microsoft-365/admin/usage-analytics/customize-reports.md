---
title: Personalizar os relatórios na análise de uso do Microsoft 365
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Saiba como personalizar relatórios no navegador e no Power BI desktop.
ms.openlocfilehash: 6e4bb6cf977607ca6e3b3f57240ac89dbd530e4f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355152"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizar os relatórios na análise de uso do Microsoft 365

A análise de uso do Microsoft 365 fornece um painel no Power BI que oferece informações sobre como os usuários adotam e usam o Microsoft 365. O painel é apenas um ponto de partida para interagir com os dados de uso. Os relatórios podem ser personalizados para informações mais personalizadas.
  
Você também pode usar a área de trabalho do Power BI para personalizar ainda mais seus relatórios conectando-os a outras fontes de dados para obter informações mais detalhadas sobre sua empresa.
  
## <a name="customizing-reports-in-the-browser"></a>Personalizando relatórios no navegador

Os dois exemplos a seguir mostram como modificar um visual existente e como criar um novo visual.
  
### <a name="modify-an-existing-visual"></a>Modifique um visual existente

Este exemplo mostra como modificar a guia de **ativação** dentro do relatório de **ativação/licenciamento** . 
  
1. No relatório de **ativação/licenciamento** , clique na guia **ativação** .
    
2. Insira o modo de edição clicando no botão **Editar** na parte superior através do ![botão mais página no botão Power bi](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) . 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. No canto superior direito, clique em **duplicar esta página**.
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. No canto inferior direito, clique em qualquer um dos gráficos de barras mostrando a contagem de ativação de usuários com base no sistema operacional, como Android, iOS, Mac, etc.
    
5. Na área **visualizações** para a direita, para remover a **contagem de Mac** do Visual, clique no **X** ao lado dela.

    ![Remover contagem de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Criar um novo visual

O exemplo a seguir mostra como criar um novo visual para rastrear novos usuários do Yammer mensalmente.
  
1. Vá para o relatório de **uso do produto** usando a barra de navegação esquerda e clique na guia do **Yammer** .
    
2. Alterne para o modo de edição clicando ![no botão mais página no Power bi](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **Editar**. 
    
3. Na parte inferior da página, clique em ![O botão Adicionar página no Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) para criar uma nova página.
  
4. Na área **visualizações** à direita, clique no **gráfico de barras empilhadas** (linha superior, primeiro à esquerda).

    ![Selecionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Clique na parte inferior direita dessa visualização e arraste para ampliá-la.

6. Na área **campos** à direita, expanda a tabela **calendário** .

7. Arraste **MonthName** para a área de campos, diretamente abaixo do cabeçalho **Eixo** na área **Visualizações**.
 
    ![Arrastar nome do mês](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Na área **Campos** à direita, expanda a tabela **TenantProductUsage**.

9. Arraste **FirstTimeUsers** para a área de campos, diretamente abaixo do cabeçalho **Valor**.

10. Arraste **Produto** para a área **Filtros**, diretamente abaixo do cabeçalho **Filtros de nível visual**.

11. Na área **Tipo de filtro** que aparece, selecione a caixa de seleção **Yammer**.

    ![Caixa de seleção selecionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Logo abaixo da lista de visualizações, **clique no ícone Format** Icon ![Format no Power bi Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).

13. Expanda o título e altere o valor do **Título do Texto** para **Usuários do Yammer pela primeira vez por mês**.
    
14. Altere o valor do **Tamanho do texto** para **12**.
    
15. Altere o título da nova página editando o nome da página no canto inferior direito.

16.  Salve o relatório clicando em modo de **exibição de leitura** na parte superior e em **salvar**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizar os relatórios na área de trabalho do Power BI

Para a maioria dos clientes, modificar os relatórios e os gráficos visuais na Web do Power BI será suficiente. Para alguns, porém, pode haver necessidade de juntar esses dados a outras fontes de dados para obter informações mais complexas e contextuais para seus próprios negócios, caso em que eles podem personalizar e criar relatórios adicionais usando a Área de trabalho do Power BI. Você pode baixar a [Área de trabalho do Power BI](https://go.microsoft.com/fwlink/p/?linkid=849797) gratuitamente. 
  
### <a name="use-the-reporting-apis"></a>Use as APIs de relatórios

Você pode começar conectando-se diretamente com as APIs de relatório ODATA da Microsoft 365 que alimentam esses relatórios.
  
1. Vá até **obter dados** \> **Outros** \> **Feed ODATA** \> **Conectar**.
    
2. Na janela URL, digite "https://<i></i>Reports.Office.com/PBI/v1.0/\<tenantid\>"
    
    **Observação:** As APIs de relatórios estão em visualização e estão sujeitas a alterações até que entrem em produção. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Digite suas credenciais de administrador do Microsoft 365 (organização ou escola) para se autenticar no Microsoft 365 quando solicitado.
    
    Consulte as [perguntas frequentes](usage-analytics.md#faq) para obter mais informações sobre quem tem permissão para acessar os relatórios de aplicativos de modelo de adoção do Microsoft 365. 
    
4. Uma vez que a conexão é autorizada, você verá a janela do Navegador que mostra os conjuntos de dados disponíveis para se conectar.
    
    Selecione todos e clique em **Carregar**.
    
    Isso baixará os dados em sua Área de trabalho do Power BI. Salve este arquivo e então você poderá começar a criar os relatórios de que precisa.
    
    ![Valores de ODATA disponíveis na API de relatórios](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Usar o modelo de análise de uso do Microsoft 365

Você também pode usar o arquivo de modelo do Power BI que corresponde aos relatórios de análise de uso do Microsoft 365 como ponto de partida para se conectar aos dados. A vantagem de usar o arquivo .pbit é que ele possui a sequência de conexão já estabelecida. Você também pode aproveitar todas as medidas personalizadas que são criadas, em cima dos dados que o esquema base retorna e criar ainda mais.
  
Você pode baixar o arquivo de modelo do Power BI no centro de download da Microsoft a partir do [centro de download](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Depois de baixar o arquivo de modelo do Power BI, siga estas etapas para começar:
  
1. Abra o arquivo .pbit.
    
2. Digite o valor da ID do locatário na caixa de diálogo.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Digite suas credenciais de administrador para se autenticar no Microsoft 365 quando solicitado.
    
     para obter mais informações sobre quem tem permissão para acessar os relatórios de análise de uso do Microsoft 365. 
    
    Uma vez autorizado, os dados serão atualizados no arquivo Power BI.
    
    A carga de dados pode levar algum tempo, uma vez concluída, você pode salvar o arquivo como um arquivo .pbix e continuar a personalizar os relatórios ou trazer uma fonte de dados adicional para este relatório.
    
4. Siga a documentação [Introdução ao Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para entender como criar relatórios, publicá-los no serviço do Power BI e compartilhar com sua organização. Seguir esse caminho para personalização e compartilhamento pode exigir licenças adicionais do Power BI. Confira as [diretrizes de licenciamento](https://go.microsoft.com/fwlink/p/?linkid=849803) do Power BI para obter mais detalhes. 
    

