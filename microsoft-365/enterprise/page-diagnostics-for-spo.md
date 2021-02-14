---
title: Usar a ferramenta Diagnóstico de Página para SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Use a ferramenta Diagnóstico de Página para SharePoint para analisar o portal moderno do SharePoint Online e as páginas clássicas de publicação em relação a um conjunto pré-definido de critérios de desempenho.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695369"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Usar a ferramenta Diagnóstico de Página para SharePoint

Este artigo descreve como usar a ferramenta Diagnóstico de Página para SharePoint para analisar páginas de site clássicos e modernas do SharePoint Online em relação a um conjunto pré-definido de **critérios** de desempenho.

A ferramenta Diagnóstico de Página para SharePoint pode ser instalada para:

- **Microsoft Edge** [(extensão do Edge)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(extensão do Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>A **versão 2.0.0** e posterior inclui suporte para páginas modernas, além de páginas clássicas do site. Se não tiver certeza de qual versão da ferramenta está usando, você poderá selecionar o **link** Sobre ou as re elipses (...) para verificar sua versão. **Sempre atualize para a versão mais recente** ao usar a ferramenta.

A ferramenta Diagnóstico de Página para SharePoint é uma extensão do navegador para os novos navegadores Microsoft Edge (https://www.microsoft.com/edge) e Chrome que analisam o portal moderno do SharePoint Online e as páginas clássicas do site de publicação. Essa ferramenta só funciona para o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

A ferramenta gera um relatório para cada página analisada mostrando o desempenho da página em relação a um conjunto de regras pré-definido e exibe informações detalhadas quando os resultados de um teste estão fora do valor da linha de base. Os administradores e designers do SharePoint Online podem usar a ferramenta para solucionar problemas de desempenho e garantir que as novas páginas sejam otimizadas antes da publicação.

A ferramenta Diagnóstico de Página foi projetada para analisar apenas páginas de site do SharePoint, não páginas do sistema, como *allitems.aspx* ou *sharepoint.aspx*. Se você tentar executar a ferramenta em uma página do sistema ou em qualquer outra página que não seja do site, receberá uma mensagem de erro avisando que a ferramenta não pode ser executado para esse tipo de página.

![Deve ser executado em uma página do SharePoint](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Isso não é um erro na ferramenta, pois não há valor na avaliação de bibliotecas ou páginas do sistema. Navegue até uma página de site do SharePoint para usar a ferramenta. Se esse erro ocorrer em uma página do SharePoint, verifique a página mestra para garantir que as metatags do SharePoint não tenham sido removidas.

To provide feedback about the tool, select the ellipsis at the top right corner of the tool and then select [Give feedback](https://go.microsoft.com/fwlink/?linkid=874109).

![Envie comentários](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Instalar a ferramenta Diagnóstico de Página para SharePoint

O procedimento de instalação nesta seção funcionará para os navegadores Chrome e Microsoft Edge.

> [!IMPORTANT]
> A Microsoft não lê dados ou conteúdo de página analisado pela ferramenta Diagnóstico de Página para SharePoint e não capturamos informações pessoais, site ou informações de download. A única informação identificável registrada na Microsoft pela ferramenta é o nome do locatário, as contagens de regras que falharam e a data e hora em que a ferramenta foi executado. Essas informações são usadas pela Microsoft para entender melhor o portal moderno e as tendências de uso do site de publicação e problemas comuns de desempenho.

1. Instale a ferramenta Diagnóstico de Página para SharePoint para **Microsoft Edge (extensão do** [Edge)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) ou **Chrome (extensão** [do Chrome).](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi) Revise a Política de Privacidade do Usuário fornecida na página de descrição na loja. Ao adicionar a ferramenta ao navegador, você verá o aviso de permissões a seguir.

    ![Permissões de extensão](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Esse aviso está em andamento porque uma página pode conter conteúdo de locais fora do SharePoint, dependendo das web parts e personalizações na página. Isso significa que a ferramenta lerá as solicitações e respostas quando o botão Iniciar for clicado e somente para a guia ativa do SharePoint em que a ferramenta está sendo executado. Essas informações são capturadas localmente pelo navegador da Web e estão disponíveis para você por  meio do botão Exportar para **JSON** ou Exportar para **HAR** na guia Rastreamento de rede da ferramenta. As informações não são enviadas ou capturadas pela **Microsoft.** (A ferramenta respeita a política de privacidade da Microsoft acessível [aqui.)](https://go.microsoft.com/fwlink/p/?linkid=857875)

    A _permissão Gerenciar downloads_ abrange o uso da funcionalidade **Exportar para JSON da** ferramenta. Siga as diretrizes de privacidade da própria empresa antes de compartilhar o arquivo JSON fora da sua organização, pois os resultados contêm URLs e podem ser classificados como PII (Informações de Identificação Pessoal).
1. Se você quiser usar a ferramenta no modo Anônimo ou InPrivate, siga o procedimento do navegador:
    1. No Microsoft Edge, navegue até **Extensões** ou digite _edge://extensions_ na barra de URL e selecione **Detalhes** da extensão. Nas configurações de extensão, marque a caixa de seleção para **permitir em InPrivate**.
    1. No Chrome, navegue **até Extensões** ou _digite chrome://extensions_ na barra de URL e selecione **Detalhes** da extensão. Nas configurações de extensão, selecione o controle deslizante **para permitir incógnito**.
1. Navegue até a página do site do SharePoint no SharePoint Online que você gostaria de revisar. Nós permitimos "atrasar o carregamento" de itens em páginas; portanto, a ferramenta não será parada automaticamente (isso é feito por design para acomodar todos os cenários de carregamento de página). Para interromper a coleção, selecione **Parar**. Certifique-se de que o carregamento da página foi concluído antes de interromper a coleta de dados ou você irá capturar apenas um rastreamento parcial.
1. Clique no botão da barra de ferramentas da extensão ![Page Diagnostics for SharePoint logo](../media/page-diagnostics-for-spo/pagediag-icon32.png) para carregar a ferramenta e você receberá a seguinte janela pop-up de extensão:

    ![Pop-up da ferramenta Diagnóstico de Página](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Selecione **Iniciar** para começar a coletar dados para análise.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>O que você verá na ferramenta Diagnóstico de Página para SharePoint

1. Clique nas re elipses (...) no canto superior direito da ferramenta para encontrar os seguintes links:
   1. O **link Recursos adicionais** fornece orientações gerais e detalhes sobre a ferramenta, incluindo um link de volta para este artigo.
   1. O link **Dar feedback** fornece um link para o site de Voz do Usuário de Colaboração e Sites _do SharePoint._
   1. O  link Sobre inclui a versão instalada no momento da ferramenta e um link direto para o aviso de terceiros da ferramenta.  
1. A **ID de Correlação, SPRequestDuration, SPIISLatency** **,** Tempo de carregamento da página e detalhes da **URL** são informativas e podem ser usadas para algumas finalidades.

    ![Detalhes de diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** é um elemento importante ao trabalhar com o Suporte da Microsoft, pois permite coletar dados de diagnóstico adicionais para a página específica.
   - **SPRequestDuration** é o tempo que o SharePoint levou para processar a página. Navegação estrutural, imagens grandes, muitas chamadas de API podem contribuir com durações mais longas.
   - **SPIISLatency** é o tempo em milissegundos que o SharePoint Online começa a carregar a página. Esse valor não inclui o tempo que o aplicativo Web deve responder.
   - **O tempo de carregamento** da página é o tempo total registrado pela página, desde o momento da solicitação até o momento em que a resposta foi recebida e renderizada no navegador. Esse valor é afetado por uma variedade de fatores, incluindo latência de rede, o desempenho do computador e o tempo necessário para o navegador carregar a página.
   - A **URL da Página** (Uniform Resource Locator) é o endereço da Web da página atual.

1. A [**guia Testes de**](#how-to-use-the-diagnostic-tests-tab) diagnóstico exibe os resultados da análise em três categorias; **Nenhuma ação necessária,** oportunidades **de melhoria** **e atenção necessária.** Cada resultado de teste é representado por um item em uma destas categorias, conforme descrito na tabela a seguir:

    |Categoria  |Cor  |Descrição  |
    |---------|---------|---------|
    |**Atenção necessária** |Vermelho |O resultado do teste está fora do valor da linha de base e está afetando o desempenho da página. Siga as orientações de correção.|
    |**Oportunidades de melhoria** |Amarelo |O resultado do teste está fora do valor da linha de base e pode estar contribuindo para problemas de desempenho. Critérios específicos do teste podem ser aplicados.|
    |**Nenhuma ação é necessária** |Verde |O resultado do teste está dentro do valor de linha de base do teste.|

    ![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Uma [**guia Rastreamento de**](#how-to-use-the-network-trace-tab) rede fornece detalhes sobre solicitações e respostas de com build de página.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Como usar a guia Testes de diagnóstico

Quando você analisa uma página de portal moderna do SharePoint ou uma página de site de publicação clássica com a ferramenta Diagnóstico  de Página para SharePoint, os resultados são analisados usando regras pré-definidas que comparam os resultados com valores de linha de base e são exibidos na guia Testes de diagnóstico. As regras para determinados testes podem usar valores de linha de base diferentes para o portal moderno e sites de publicação clássicos, dependendo de como características de desempenho específicas diferem entre os dois.

Os resultados do  teste que  aparecem nas oportunidades de melhoria ou nas categorias De atenção necessárias indicam áreas que devem ser revisadas em relação às práticas recomendadas e podem ser selecionadas para exibir informações adicionais sobre o resultado. Os detalhes de cada item incluem _um_ link Saiba mais que levará você diretamente para as orientações apropriadas relacionadas ao teste. Os resultados do teste que aparecem na **categoria Nenhuma** ação necessária indicam a conformidade com a regra relevante e não exibem detalhes adicionais quando selecionados.

As informações na guia Testes de Diagnóstico não lhe dirá como projetar páginas, mas destacarão fatores que podem afetar o desempenho da página. Algumas funcionalidades e personalizações de página têm um impacto inevitável no desempenho da página e devem ser revisadas para correção ou omissão potenciais da página se o impacto for substancial.

Os resultados vermelhos ou amarelos também podem indicar web parts que atualizem dados com muita frequência. Por exemplo, as notícias corporativas não são atualizadas a cada segundo, mas as Web Parts personalizadas geralmente são criadas para buscar as notícias mais recentes a cada segundo, em vez de implementar elementos de cache que poderiam melhorar a experiência geral do usuário. Lembre-se de que, ao incluir Web Parts em uma página, muitas vezes há maneiras simples de reduzir o impacto no desempenho avaliando o valor de cada parâmetro disponível para garantir que ele seja definido adequadamente para sua finalidade pretendida.

>[!NOTE]
>Sites de equipe clássicos que não têm o recurso de publicação habilitado não podem usar CDNs. Quando você executar a ferramenta nesses sites, espera-se que o teste de CDN falhe e possa ser ignorado, mas todos os testes restantes são aplicáveis. A funcionalidade adicional do recurso de publicação do SharePoint pode aumentar o tempo de carregamento da página, portanto, ele não deve ser habilitado apenas para permitir a funcionalidade da CDN.

>[!IMPORTANT]
>As regras de teste são adicionadas e atualizadas regularmente, portanto, consulte a versão mais recente da ferramenta para obter detalhes sobre as regras atuais e informações específicas incluídas nos resultados do teste. Você pode verificar a versão gerenciando suas extensões e a extensão avisará se uma atualização está disponível.

## <a name="how-to-use-the-network-trace-tab"></a>Como usar a guia Rastreamento de Rede

A **guia Rastreamento de** Rede fornece informações detalhadas sobre as solicitações para criar a página e as respostas recebidas do SharePoint.

1. **Procure os tempos de carregamento do item sinalizados como vermelho.** Cada solicitação e resposta é codificada por cores para indicar seu impacto no desempenho geral da página usando as seguintes métricas de latência:
    - Verde: \< 500 ms
    - Amarelo: 500 a 1000 ms
    - Vermelho: \> 1000 ms

    ![Rastreamento de rede](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    Na imagem mostrada acima, o item vermelho pertence à página padrão. Ele sempre será vermelho, a menos que a página seja carregada em \< 1000 ms (menos de 1 segundo).

2. **Tempos de carregamento do item de teste.** Em alguns casos, não haverá nenhum indicador de hora ou cor porque os itens já foram armazenados em cache pelo navegador. Para testar corretamente, abra a página, limpe  o cache do navegador e clique em Iniciar, pois isso força uma carga de página "a frio" e será um reflexo real do carregamento inicial da página. Isso deve ser comparado à carga de página "morna", pois isso também ajudará a determinar quais itens estão sendo armazenados em cache na página.

3. **Compartilhe detalhes relevantes com outras pessoas que podem ajudar a investigar problemas.** Para compartilhar os detalhes ou informações fornecidos na ferramenta com seus desenvolvedores ou uma pessoa de suporte técnico, clique em Exportar para **JSON** (conforme mostrado na imagem acima). Isso permitirá que você baixe os resultados, que podem ser visualizados com um visualizador de arquivos JSON.

    Se você optou por usar o recurso de visualização habilitar Exportar para *HAR,* o tipo de exportação será mostrar como **Exportar para HAR**.

    ![Rastreamento de rede](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Esses resultados contêm URLs e podem ser classificados como PII (Informações de Identificação Pessoal). Siga as diretrizes da sua organização antes de distribuir essas informações.

## <a name="engaging-with-microsoft-support"></a>Interagir com o suporte da Microsoft

Incluímos um recurso **de nível de** suporte da Microsoft que só deve ser usado ao trabalhar diretamente em um caso de suporte. A utilização desse recurso não oferecerá nenhum benefício quando usado sem suporte ao envolvimento da equipe e poderá fazer com que a página tenha um desempenho significativamente mais lento. Não há informações adicionais ao usar esse recurso na ferramenta, pois as informações adicionais são adicionadas ao registro em log no serviço.

Nenhuma alteração é visível, exceto que você será notificado de que a habilitará e seu desempenho de página será significativamente degradado por 2 a 3 vezes mais lento desempenho enquanto estiver habilitado. Ela só será relevante para a página específica e essa sessão ativa. Por esse motivo, isso deve ser usado com moderação e somente quando ativamente envolvido com o suporte.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Para habilitar o recurso de nível de Suporte da Microsoft

1. Abra a ferramenta Diagnóstico de Página para SharePoint.
2. No teclado, pressione **ALT-Shift-L**. Isso exibirá a caixa **de seleção Habilitar log** de suporte.
3. Marque a caixa de seleção e clique em **Iniciar** para recarregar a página e gerar o log detalhado.

    ![Opção de suporte habilitada](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Você deve observar a CorrelationID (exibida na parte superior da ferramenta) e forneça-a ao seu representante de suporte para permitir que eles reúnam informações adicionais sobre a sessão de diagnóstico.

## <a name="related-topics"></a>Tópicos relacionados

[Ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)

[Desempenho na experiência moderna do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Redes de distribuição de conteúdo](content-delivery-networks.md)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)
