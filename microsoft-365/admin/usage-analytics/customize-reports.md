---
title: Personalizar os relatórios na análise Microsoft 365 uso
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Aprenda a personalizar relatórios no navegador e Power BI Desktop.
ms.openlocfilehash: 0ef2364c82318dfea93e8df4e64d53a66caa8d74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580769"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizar os relatórios na análise Microsoft 365 uso

Microsoft 365 análise de uso fornece um painel em Power BI que oferece informações sobre como os usuários adotam e usam Microsoft 365. O painel é apenas um ponto de partida para interagir com os dados de uso. Os relatórios podem ser personalizados para informações mais personalizadas.
  
Você também pode usar a área de trabalho do Power BI para personalizar ainda mais seus relatórios conectando-os a outras fontes de dados para obter informações mais detalhadas sobre sua empresa.
  
## <a name="customizing-reports-in-the-browser"></a>Personalizando relatórios no navegador

Os dois exemplos a seguir mostram como modificar um visual existente e como criar um novo visual.
  
### <a name="modify-an-existing-visual"></a>Modifique um visual existente

Este exemplo mostra como modificar a guia **Ativação** no relatório **de Ativação/Licenciamento.** 
  
1. No relatório **Ativação/Licenciamento,** selecione a **guia Ativação.**
    
2. Insira o modo de edição escolhendo o **botão Editar** na parte superior por meio do botão Mais página ![ Power BI ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) botão. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Na parte superior direita, escolha **Duplicar esta página**.
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. Na parte inferior direita, escolha qualquer um dos gráficos de barras mostrando a contagem de usuários ativando com base no sistema operacional, como Android, iOS, Mac, etc.
    
5. Na área **Visualizações** à direita, para remover **Mac Count** do visual, selecione **o X** ao lado dele.

    ![Remover Contagem de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Criar um novo visual

O exemplo a seguir mostra como criar um novo visual para rastrear novos usuários do Yammer mensalmente.
  
1. Vá para o **relatório uso do** produto usando a navegação à esquerda e selecione a guia **Yammer.**
    
2. Alternar para o modo de edição escolhendo O botão mais página no Power BI ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **Editar**. 
    
3. Na parte inferior da página, selecione o ![O botão adicionar página no Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) para criar uma nova página.
  
4. Na área **Visualizações** à direita, escolha o gráfico da barra **empilhada** (linha superior, primeiro da esquerda).

    ![Selecionar Gráfico de Barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Selecione a parte inferior direita dessa visualização e arraste para torná-la maior.

6. Na área **Campos** à direita, expanda a **tabela Calendário.**

7. Arraste **MonthName** para a área de campos, diretamente abaixo do cabeçalho **Eixo** na área **Visualizações**.
 
    ![Nome do mês de arrastar](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Na área **Campos** à direita, expanda a tabela **TenantProductUsage**.

9. Arraste **FirstTimeUsers** para a área de campos, diretamente abaixo do cabeçalho **Valor**.

10. Arraste **Produto** para a área **Filtros**, diretamente abaixo do cabeçalho **Filtros de nível visual**.

11. Na área **Tipo de filtro** que aparece, selecione a caixa de seleção **Yammer**.

    ![Selecione Yammer caixa de seleção](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Logo abaixo da lista de visualizações, escolha o ícone **Formatar** ícone Formatar ícone Em Power BI ![ Visualizações ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .

13. Expanda o título e altere o valor do **Título do Texto** para **Usuários do Yammer pela primeira vez por mês**.
    
14. Altere o valor do **Tamanho do texto** para **12**.
    
15. Altere o título da nova página editando o nome da página na parte inferior direita.

16.  Salve o relatório clicando em Exibição de **Leitura** na parte superior e, em seguida, **Salvar**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizar os relatórios na área de trabalho do Power BI

Para a maioria dos clientes, modificar os relatórios e os gráficos visuais na Web do Power BI será suficiente. Para alguns, porém, pode haver necessidade de juntar esses dados a outras fontes de dados para obter informações mais complexas e contextuais para seus próprios negócios, caso em que eles podem personalizar e criar relatórios adicionais usando a Área de trabalho do Power BI. Você pode baixar a [Área de trabalho do Power BI](https://go.microsoft.com/fwlink/p/?linkid=849797) gratuitamente. 
  
### <a name="use-the-reporting-apis"></a>Use as APIs de relatórios

Você pode começar conectando-se diretamente às APIs de relatório ODATA Microsoft 365 que ligam esses relatórios.
  
1. Vá até **obter dados** \> **Outros** \> **Feed ODATA** \> **Conectar**.
    
2. Na janela URL, digite "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"
    
    **OBSERVAÇÃO:** As APIs de relatório estão em visualização e estão sujeitas a alterações até entrar em produção. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Insira suas Microsoft 365 de administrador (organização ou escola) para autenticar para Microsoft 365 quando solicitado.
    
    Consulte as [Perguntas Frequentes](usage-analytics.md#faq) para obter mais informações sobre quem tem permissão para acessar os relatórios do aplicativo de modelo Microsoft 365 Adoção. 
    
4. Uma vez que a conexão é autorizada, você verá a janela do Navegador que mostra os conjuntos de dados disponíveis para se conectar.
    
    Selecione tudo e escolha **Carregar**.
    
    Isso baixará os dados em sua Área de trabalho do Power BI. Salve este arquivo e então você poderá começar a criar os relatórios de que precisa.
    
    ![Valores ODATA disponíveis na API de relatórios](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Usar o modelo Microsoft 365 análise de uso

Você também pode usar o arquivo Power BI de modelo que corresponde aos relatórios Microsoft 365 análise de uso como ponto de partida para se conectar aos dados. A vantagem de usar o arquivo .pbit é que ele possui a sequência de conexão já estabelecida. Você também pode aproveitar todas as medidas personalizadas que são criadas, em cima dos dados que o esquema base retorna e criar ainda mais.
  
Você pode baixar o arquivo Power BI de modelo do [Centro de Download da Microsoft.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) Depois de baixar o arquivo Power BI modelo, siga estas etapas para começar:
  
1. Abra o arquivo .pbit.
    
2. Digite o valor da ID do locatário na caixa de diálogo.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Insira suas credenciais de administrador para autenticar para Microsoft 365 quando solicitado.
    
     para obter mais informações sobre quem tem permissão para acessar os relatórios Microsoft 365 análise de uso. 
    
    Uma vez autorizado, os dados serão atualizados no arquivo Power BI.
    
    A carga de dados pode levar algum tempo, uma vez concluída, você pode salvar o arquivo como um arquivo .pbix e continuar a personalizar os relatórios ou trazer uma fonte de dados adicional para este relatório.
    
4. Siga a documentação [Introdução ao Power BI](/power-bi/fundamentals/desktop-getting-started) para entender como criar relatórios, publicá-los no serviço do Power BI e compartilhar com sua organização. Seguir esse caminho para personalização e compartilhamento pode exigir licenças adicionais do Power BI. Confira as [diretrizes de licenciamento](https://go.microsoft.com/fwlink/p/?linkid=849803) do Power BI para obter mais detalhes. 
