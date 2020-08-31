---
title: Pontuação de produtividade da Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Visão geral da pontuação da produtividade da Microsoft.
ms.openlocfilehash: 47675f37e9146586b3fe0dd8d974887fd2435bf3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307472"
---
# <a name="microsoft-productivity-score-preview"></a>Pontuação de produtividade da Microsoft (versão prévia)

Pontuação de produtividade ajuda as organizações a transformar como o trabalho é feito com ideias sobre como as pessoas usam o Microsoft 365 e as experiências tecnológicas que dão suporte a eles. A pontuação reflete o desempenho da organização em relação à experiência de funcionários e tecnologias e compara sua pontuação com organizações como a sua.

A pontuação inclui:

- **Métricas** para ajudá-lo a ver como as pessoas estão usando produtos Microsoft 365 para colaborar, comunicar e trabalhar entre plataformas.
- **Informações sobre os** dados para ajudá-lo a identificar oportunidades para melhorar a produtividade e a satisfação dos funcionários.
- **Ações recomendadas** que você pode executar para ajudar as pessoas da sua organização a usar os produtos do Microsoft 365 com eficiência para que todos possam realizar o melhor trabalho.

Fornecemos dados, ideias e recomendações em duas áreas: 

- **Experiência do funcionário:** Medimos como as pessoas colaboram com o conteúdo, como usam os produtos da Microsoft 365 para se comunicarem e se usam o Microsoft 365 entre plataformas. 

    Fornecemos esses percepções porque, quando as pessoas colaboram online, elas economizam tempo. Quando eles têm liberdade para trabalhar em qualquer dispositivo, eles são mais produtivos e satisfeitos. Quando eles podem se comunicar de forma flexível, eles são mais eficientes, relações melhores de formulário e sua organização é mais unificado. Para obter evidências, consulte [Forrester Report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Experiência de tecnologia:** A produtividade depende da tecnologia confiável e de desempenho, bem como do uso eficiente do Microsoft 365. Fornecemos a [análise de ponto de extremidade](https://aka.ms/endpointanalytics), que o ajuda a entender como a produtividade dos usuários pode ser afetada por problemas de desempenho e integridade com seu hardware e software de ponto de extremidade, enquanto fornece ações recomendadas para corrigi-los; e fornecemos informações de conectividade de rede da Microsoft 365 para sua organização.

Veja [o que é o Endpoint Analytics](https://docs.microsoft.com/mem/analytics/overview) para obter uma visão geral e os detalhes dos pré-requisitos. Para saber mais sobre o Microsoft 365 insights de conectividade de rede, leia [a visão geral da conectividade de rede](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Como a pontuação é calculada

A pontuação da produtividade baseia-se nas pontuações combinadas das categorias de experiência de seus funcionários e tecnologias. Cada categoria é ponderada igualmente, com um total de 100 pontos por categoria. O total de pontos possíveis para a pontuação de produtividade é de 500.

### <a name="score-categories"></a>Categorias de Pontuação 

- Colaboração de conteúdo (100 pontos)
- Comunicação (100 pontos)
- Mobilidade (100 pontos)
- Análise de ponto de extremidade (100 pontos)
- Conectividade de rede (100 pontos)
- **Total possível = 500 pontos**
 
 Em cada categoria, identificamos padrões para as principais atividades que são indicadores de como as pessoas usam os produtos da Microsoft 365 para colaborar, comunicar e trabalhar entre plataformas. Fornecemos visualizações de 28 dias e 180 dias das principais atividades. Também fornecemos métricas de suporte que não fazem parte do cálculo de pontuação, mas são importantes para ajudá-lo a identificar comportamentos e configurações subjacentes que podem ser atuados na alteração da unidade.

### <a name="products-included-in-productivity-score"></a>Produtos incluídos na pontuação de produtividade 

Pontuação de produtividade inclui dados do Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer e Skype.

Sua pontuação é atualizada diariamente e reflete as ações do usuário concluídas nos últimos 28 a 180 dias (incluindo o dia atual).


## <a name="pre-requisites"></a>Pré-requisitos 

Você precisa de uma assinatura do Microsoft 365 for Business ou do Office 365 para Enterprise para obter os dados da experiência do funcionário, e você precisa estar usando serviços em nuvem de vários locatários. Para obter dados de análise do ponto de extremidade para seu locatário, você precisa adicionar o Microsoft Intune à sua assinatura. O Intune ajuda você a proteger os dados da sua organização por meio do gerenciamento de dispositivos e aplicativos.       Depois de ter o Intune, você pode ativar a análise de ponto de extremidade dentro da experiência do Intune. Saiba mais sobre o Microsoft Intune. 

Para exibir a pontuação de produtividade da sua organização, você deve ter uma das seguintes funções: 

- Administrador global 
- Administradores do Exchange
- Administrador do SharePoint 
- Administrador do Skype for Business 
- Administrador de equipes 
- Leitor global 
- Leitor de relatórios 

Você pode acessar a experiência da página inicial do Microsoft 365 admin em **relatórios**de  >  **produtividade**.

## <a name="interpreting-productivity-score"></a>Interpretação da Pontuação de produtividade 

A Home Page de Pontuação de produtividade mostra a pontuação total e o histórico de pontuação, bem como a principal percepção de cada categoria

![Home Page de Pontuação de produtividade](../../media/pslanding.png)

**Sua pontuação** é mostrada como um valor de porcentagem, bem como em pontos, para que você possa ver seus pontos (numerador) e os pontos máximos possíveis (denominadores).

Os **benchmarks de ponto** permitem comparar sua pontuação com organizações como a sua. Para as categorias de experiência do funcionário, a medida de benchmark de ponto é calculada como a média de medidas dentro de um conjunto de organizações semelhantes. O conjunto é composto por organizações em sua região com um número semelhante de usuários licenciados, tipos de licenças, setor e gestão com o Microsoft 365. 

O benchmark ponto de extremidade da análise do Endpoint inclui destinos para o desempenho de inicialização do dispositivo e a configuração de software recomendada com base em valores medianos agregados em todos os locatários.

Para conectividade de rede, o benchmark recomendado é de 80 pontos.

A seção de **divisão de Pontuação** fornece uma divisão da sua pontuação de produtividade com benchmarks por funcionários e áreas de experiência de tecnologia.

O histórico de Pontuação exibe como sua pontuação em cada categoria foi alterada nos últimos seis meses.

As áreas **experiência do funcionário** e **experiência tecnológica** contêm os principais fatos para as categorias nessas áreas. Você pode clicar em cada categoria para ver informações mais profundas.

## <a name="category-details-pages"></a>Páginas de detalhes da categoria

Cada página de detalhes da categoria mostra a principal percepção e as métricas de suporte, bem como as pesquisas e ações relacionadas que você pode tomar para conduzir as alterações em sua organização. A pesquisa oferece suporte à importância e lógica por trás dos principais insights para cada categoria. para obter mais informações, [Leia o relatório da Forrester](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

### <a name="content-collaboration-details"></a>Detalhes de colaboração de conteúdo

A principal visão da colaboração de conteúdo é o número de pessoas que criar, ler e colaborar (editar e compartilhar) online. Essas medidas são importantes porque a pesquisa mostra que, quando as pessoas colaboram com arquivos online, cada pessoa salva uma média de 100 minutos ou quase 2 horas por semana.

Definimos a colaboração de conteúdo como uma pessoa criando e compartilhando um arquivo do Office e, em seguida, pelo menos uma outra pessoa editando-o. 

Leitores: pessoas que acessam ou fazem download de arquivos online no OneDrive ou no SharePoint.

**Criadores:** Pessoas que criam, modificam, carregam, sincronizam, fazem check-in, copiam ou movem arquivos do OneDrive ou do SharePoint Online.

Colaboradores: pessoas que colaboram com arquivos online usando o OneDrive ou o SharePoint. Duas pessoas são colaboradores se um deles lê ou edita um documento online do Word, Excel, PowerPoint, OneNote ou em nuvem do PDF depois que a outra pessoa cria ou modifica, em uma janela de 28 dias.

Os tipos de arquivo considerados para colaboração são arquivos do Word, Excel, PowerPoint, OneNote e PDF.

Fornecemos informações sobre os tempos de inicialização e configurados para dispositivos em sua organização, bem como insights de conectividade de rede para colaboração de conteúdo porque a colaboração de arquivos online requer dispositivos confiáveis que começam a ter software atualizado, bem como boa conectividade para o Microsoft 365.

### <a name="communication-details"></a>Detalhes de comunicação

A principal visão da comunicação é a freqüência com que as pessoas em sua organização usam Postagens de email, chat e comunidade para se comunicar. Essa percepção é importante porque, quando as pessoas usam uma variedade de ferramentas de comunicação em tempo real, elas podem escolher o modo de comunicação que ajuda a ser mais eficiente, e elas têm ferramentas como chat e comunidades que ajudam a desenvolver relações entre os locais do Office.

### <a name="mobility-details"></a>Detalhes da mobilidade

A principal percepção para mobilidade é o número de pessoas que acessam arquivos e usam email e bate-papo em várias plataformas. A capacidade de trabalhar a partir de qualquer local em qualquer dispositivo que ele escolha seja importante para pessoas com funções de vendas, gerentes seniores, consultores e outros que precisam trabalhar fora do escritório para serem produtivos. Os aprimoramentos desses funcionários têm um grande impacto. 

Medimos a porcentagem e o número absoluto de pessoas que usavam pelo menos um aplicativo de produtividade da Microsoft 365 em duas ou mais plataformas, incluindo desktops, móveis e Web. Os aplicativos de produtividade que medemos são Outlook, Teams, Word, Excel, PowerPoint, OneNote, Yammer e Skype. As pessoas devem ter aplicativos da Microsoft 365 para licenças Enterprise, Exchange, Yammer, Skype ou Teams a serem medidos. 

## <a name="business-continuity-special-report"></a>Relatório especial de continuidade de negócios

O relatório de continuidade de negócios é um relatório de inteligência de trabalho em tempo limitado disponível para todos os clientes da Microsoft 365 para ajudá-los a guiar suas organizações durante esse tempo desafiador.  

Este relatório ajuda os líderes de negócios a entender: 

- Como a colaboração e a comunicação são afetadas pela mudança para o trabalho remoto. 

- O impacto no equilíbrio de vida útil como as pessoas se ajustam para trabalhar de casa. 

- Se as reuniões remotas oferecerem suporte à tomada de decisão eficaz.

[Saiba mais sobre o relatório de continuidade de negócios](https://aka.ms/bcrps)

[Saiba mais sobre o Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Compartilhe suas opiniões sobre a pontuação de produtividade e suas ideias sobre como aprimorá-la. Use as seções de **comentários** dentro do produto e/ou acesse a equipe de Pontuação de produtividade em ProductivityScorePreview@service.microsoft.com.
