---
title: Pontuação de Produtividade da Microsoft - Colaboração de conteúdo
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Detalhes da colaboração de conteúdo - as pessoas experimentam a Pontuação de Produtividade.
ms.openlocfilehash: 43a5fbc3b1c4b6227cd29d79bfb0928a3b4b8ac9
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903317"
---
# <a name="content-collaboration--people-experiences"></a>Colaboração de conteúdo – Experiências de pessoas

A Pontuação de Produtividade fornece informações sobre a jornada de transformação digital da sua organização por meio do uso do Microsoft 365 e das experiências de tecnologia que o suportam. A pontuação da sua organização reflete as medidas de experiência de pessoas e tecnologias e pode ser comparada a comparações de organizações semelhantes às suas. A categoria de colaboração de conteúdo faz parte das medições de experiências de pessoas. Para saber mais, confira a visão geral [da Pontuação de Produtividade](productivity-score.md) e leia a Declaração de Privacidade da [Microsoft.](https://privacy.microsoft.com/privacystatement)

## <a name="prerequisites"></a>Pré-requisitos

Para começar a obter informações de colaboração de conteúdo, as pessoas em sua organização precisam ser licenciadas para:

- OneDrive for Business
- SharePoint
- Exchange Online

Para obter mais informações, [consulte atribuir licenças aos usuários](../manage/assign-licenses-to-users.md).

 Depois que as pessoas foram ativas nos produtos acima pelo menos uma vez nos últimos 28 dias, você começará a ver as informações.

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>Por que sua organização&#39;pontuação de colaboração de conteúdo importa

Um aspecto fundamental da transformação digital é como as pessoas colaboram nos arquivos. Com seu conteúdo no Microsoft 365, as pessoas acessam, criam, modificam e colaboram no conteúdo com outras pessoas de qualquer local. A pesquisa mostra que quando as pessoas colaboram com arquivos online, cada pessoa economiza uma média de 100 minutos por semana. [Consulte a evidência](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

## <a name="how-we-calculate-the-content-collaboration-score"></a>Como calculamos a pontuação de colaboração de conteúdo

Fornecemos uma visão principal que contém as principais métricas para colaboração de conteúdo em sua organização. Em seguida, uma estrutura de pontuação detalhada abaixo é usada para essas métricas calcularem a pontuação da sua organização.

> [!NOTE]
> Em 22 de abril de 2021, mudamos a forma como a métrica dos colaboradores é calculada. Isso afeta a visão [primária](#primary-insight), o insight de colaboração [de](#number-of-files-collaborated-on)arquivos e a forma como a pontuação de colaboração de conteúdo é medida. Essa alteração ajuda a reduzir o ruído nos dados de agentes não humanos (ou bots) da Microsoft e de outros aplicativos de terceiros, resultando em uma pontuação mais precisa e a ação.

### <a name="primary-insight"></a>Visão primária

O Microsoft OneDrive for Business e o SharePoint ajudam as pessoas a criar, ler e descobrir facilmente seu conteúdo individual e compartilhado no Microsoft 365 entre dispositivos e aplicativos. Eles também permitem que as pessoas compartilhem e colaborem com segurança no conteúdo. O insight principal contém informações de todos os que podem usar o OneDrive for Business e o SharePoint. Além disso, ele divide os detalhes sobre quantas pessoas leem, criam e colaboram no conteúdo armazenado no OneDrive for Business e no SharePoint.

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="Principais percepções da pontuação de colaboração de comunicação.":::


Os tipos considerados para essas informações incluem arquivos Word, Excel, PowerPoint, OneNote e PDF.

1. **Header:** Mostra a porcentagem de pessoas em sua organização que têm acesso ao OneDrive ou Ao SharePoint que estão colaborando no conteúdo.
2. **Corpo:** Fornece mais informações sobre como os comportamentos de leitura e criação de arquivos online são vinculados à colaboração em arquivos.
3. **Visualização (estado atual):**
    - Barras horizontais onde as partes coloridas em azul representam a porcentagem de pessoas habilitadas para  colaboração de arquivos por meio do OneDrive ou do SharePoint que foram **leitores,** criadores ou colaboradores em arquivos online nos últimos 28 dias.

        Eles são definidos da seguinte forma:</br>
        **Leitores:** Pessoas que acessam ou baixam arquivos online no OneDrive ou no SharePoint.</br>
        **Criadores:** Pessoas que criam, modificam, carregam, sincronizam, fazem check-in, copiam ou movem arquivos online do OneDrive ou do SharePoint.</br>
        **Colaboradores:** Pessoas que colaboram com arquivos online usando o OneDrive ou o SharePoint. Duas pessoas serão colaboradoras se uma delas ler ou editar um aplicativo do Office online ou PDF depois que a outra pessoa o tiver criado ou modificado, em uma janela de 28 dias.

        > [!NOTE]
        > Os arquivos considerados na visualização são arquivos word, Excel, PowerPoint, OneNote ou PDF que estão online e salvos no OneDrive ou no SharePoint. 

    - O destaque (numerador/denominador) da fração é usado para calcular a porcentagem expressa em cada uma das barras horizontais.
    
      - **Leitores:**</br>
          - Numerador: número de pessoas que acessam ou baixam arquivos online no OneDrive ou no SharePoint nos últimos 28 dias</br>
          - Denominador: Número de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos 1 dos últimos 28 dias</br>
      - **Criadores:**</br>
        - Numerador: número de pessoas que criam, modificam, carregam, sincronizam, fazem check-in, copiam ou movem arquivos online no OneDrive ou no SharePoint nos últimos 28 dias</br>
        - Denominador: número de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos 1 dos últimos 28 dias. </br> 
      - **Colaboradores:**</br>
        - Numerador: número de pessoas que colaboraram em arquivos online no OneDrive ou no SharePoint nos últimos 28 dias</br>
        - Denominador: número de pessoas que tiveram acesso para OneDrive ou SharePoint por pelo menos 1 dos últimos 28 dias

    - O valor de referência par para cada um dos leitores, criadores e colaboradores também é mostrado como uma porcentagem. Em outras palavras, o valor do número de criadores é mostrado como uma porcentagem do número de pessoas que têm acesso ao OneDrive ou Ao SharePoint.
    
1. **Link para recursos:** Selecione este link para exibir vídeos colados e outros conteúdos de ajuda relacionados.


#### <a name="trend-visualization-of-primary-insight"></a>Visualização de tendências do insight primário

O gráfico de visualizações de tendência mostra a linha de tendência das principais métricas de insight principais para leitores, criadores e colaboradores, nos últimos 180 dias. Cada ponto de dados no gráfico é um agregado de atividade dos últimos 28 dias. Cada ponto de dados do criador fornece uma contagem de todas as pessoas que foram marcadas como criadores nos últimos 28 dias para cada data no eixo x.

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="Gráfico com tendências para visão primária de colaboração.":::

### <a name="scoring-framework"></a>Estrutura de pontuação

A pontuação de colaboração de conteúdo para sua organização mede em um nível agregado (organização) se as pessoas estão lendo, criando ou colaborando consistentemente em arquivos do Office online, como Word, Excel, PowerPoint, OneNote ou PDFs, ou no OneDrive ou no SharePoint.

As pontuações não são fornecidas no nível de usuário individual.

## <a name="explore-how-your-organization-collaborates"></a>Explorar como sua organização colabora

Também fornecemos informações que ajudam você a obter visibilidade sobre como sua organização colabora no conteúdo. Essas métricas adicionais não contribuem diretamente para a Pontuação de Produtividade, mas ajudam você a criar um plano de ação como parte da transformação digital para ajudar a otimizar a maneira como as pessoas trabalham.

### <a name="creating-files-in-onedrive-or-sharepoint"></a>Criando arquivos no OneDrive ou no SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="Gráfico que mostra o número de pessoas que criam arquivos no OneDrive ou no SharePoint":::

1. **Header:** Realça a porcentagem de pessoas ativas em aplicativos do Microsoft 365 Office que criam arquivos no OneDrive ou no SharePoint.
2. **Corpo:** Fornece informações sobre o valor da criação de conteúdo no OneDrive e no SharePoint.
3. **Visualização:** A divisão na visualização representa até que ponto as pessoas que estão usando Microsoft Office aplicativos para criar arquivos no OneDrive e no SharePoint, da seguinte maneira:
      - **OneDrive:** A parte azul (colorida) da barra e a fração na barra representam a porcentagem de pessoas ativas em aplicativos do Office criando conteúdo no OneDrive da seguinte forma:
        - Numerador: o número de pessoas que criam, modificam, carregam, sincronizam, fazem check-in, copiam ou movem arquivos do Office online no OneDrive nos últimos 28 dias.</br>
        - Denominador: o número de pessoas que têm acesso ao OneDrive ou Ao SharePoint e acessam arquivos do office nos últimos 28 dias.
      - **SharePoint:** A parte azul (colorida) da barra e a fração na barra representam a porcentagem de pessoas que estão ativas em aplicativos do Office e criam conteúdo no SharePoint como:</br>
         - Numerador: o número de pessoas que criam, modificam, carregam, sincronizam, verificam, copiam ou movem arquivos do Office online (arquivos do Microsoft Word, Excel, PowerPoint ou OneNote) no SharePoint nos últimos 28 dias.</br>
        - Denominador: o número de pessoas que têm acesso ao OneDrive ou Ao SharePoint e acessaram arquivos do Office nos últimos 28 dias.

4. **Link para recursos:** Selecione este link para exibir o conteúdo da ajuda.

### <a name="use-of-attachments-in-email"></a>Uso de anexos no email

:::image type="content" source="../../media/emailattachments.png" alt-text="Uso de anexos de email.":::

1. **Header:** Realça a porcentagem de pessoas que usam anexos em emails que não foram salvos no OneDrive ou no SharePoint.
2. **Corpo:** Fornece informações sobre o valor de compartilhamento de links para arquivos online de uma perspectiva de colaboração e segurança.
3. **Visualização:** A divisão na visualização deve representar a extensão em que as pessoas que estão anexando conteúdo em emails estão usando modos diferentes (arquivos que não estão no OneDrive ou no SharePoint; links para arquivos online e links inseridos no email):
      - **Anexar arquivos:** A parte azul (colorida) da barra e a fração (numerador/denominador) na barra representa a porcentagem de pessoas que usam anexos em emails.
        - Numerador: o número de pessoas que anexam arquivos a emails que não foram salvos no OneDrive ou no SharePoint nos últimos 28 dias.
        - Denominador: o número de pessoas que tiveram acesso ao Exchange e Ao OneDrive, Ao SharePoint ou ambos nos últimos 28 dias.
      - **Links para arquivos online:** A parte azul (colorida) da barra e a fração (numerador/denominador) na barra representam a porcentagem de pessoas usando anexos e anexando links a arquivos em emails.
        - Numerador: o número de pessoas anexando links a arquivos online (salvos no OneDrive ou no SharePoint) para emails nos últimos 28 dias.
        - Denominador: o número de pessoas que têm acesso ao Exchange e Ao OneDrive, Ao SharePoint ou ambos nos últimos 28 dias.
      - **Inserir links no email:** A parte azul (colorida) da barra e a fração na barra representam a porcentagem de pessoas que incorporam links no corpo dos emails.
        - Numerador: o número de pessoas incorporando links no corpo de emails para arquivos online (salvos no OneDrive ou no SharePoint) nos últimos 28 dias.
        - Denominador: o número de pessoas que têm acesso ao Exchange e Ao OneDrive, Ao SharePoint ou ambos nos últimos 28 dias.
4. **Link para recursos:** Selecione este link para exibir o conteúdo da ajuda.

### <a name="sharing-of-online-files"></a>Compartilhamento de arquivos online

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="Gráfico que mostra o número de pessoas compartilhando arquivos online.":::

1. **Header:** Realça a porcentagem de pessoas que têm acesso para OneDrive ou SharePoint que estão compartilhando arquivos externamente.
2. **Corpo:** Fornece informações sobre os administradores&#39; capacidade de alterar as configurações de compartilhamento de arquivos na organização para habilitar o nível de colaboração mais adequado à sua organização.
3. **Visualização:** Representa até que ponto as pessoas que têm acesso ao OneDrive ou Ao SharePoint estão compartilhando arquivos interna ou externamente:
      - **Externamente:** A parte azul (colorida) da barra e a fração (numerador/denominador) na barra representam a porcentagem de pessoas que têm acesso ao OneDrive ou Ao SharePoint e estão compartilhando arquivos externamente.
        -  Numerador: o número de pessoas que compartilharam arquivos externamente nos últimos 28 dias
        - Denominador: o número total de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos 1 dos últimos 28 dias.
      - **Somente internamente:** A parte azul (colorida) da barra e a fração (numerador/denominador) na barra representam a porcentagem de pessoas que têm acesso ao OneDrive ou Ao SharePoint e estão compartilhando arquivos apenas internamente.
        - Numerador: o número de pessoas que compartilharam arquivos internamente somente nos últimos 28 dias
        - Denominador: o número total de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos 1 dos últimos 28 dias.
4. **Link para recursos:** Selecione este link para exibir o conteúdo da ajuda.

### <a name="number-of-files-collaborated-on"></a>Número de arquivos em que colaboraram

:::image type="content" source="../../media/intensityofcollab.png" alt-text="Gráfico mostrando quantos arquivos foram mais colaborados.":::

1. **Header:** Realça a porcentagem de pessoas que têm acesso ao OneDrive ou Ao SharePoint que estão colaborando em 4 ou mais arquivos.
2. **Corpo:** Fornece informações sobre como as pessoas podem aproveitar arquivos online para melhor colaboração.
3. **Visualização:** Mostra uma distribuição das pessoas que têm acesso ao OneDrive ou Ao SharePoint, com base no número de arquivos em que colaboram. Isso é mostrado pelas 4 categorias a seguir (para cada uma, a parte azul da barra e a fração representam a porcentagem de pessoas que têm acesso ao OneDrive ou Ao SharePoint que se enquadram nessa categoria):
      - **Nenhuma colaboração:**
        - Numerador: número de pessoas que não colaboraram em nenhum arquivo nos últimos 28 dias.
        - Denominador: Número total de pessoas que têm acesso ao OneDrive ou Ao SharePoint por pelo menos um dos últimos 28 dias.
      - **Colaboração em arquivos de 1 a 3:**
        - Numerador: número de pessoas colaborando em arquivos de 1 a 3 nos últimos 28 dias.
        - Denominador: Número total de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos um dos últimos 28 dias.
      - **Colaboração em arquivos de 4 a 10:**
        - Numerador: número de pessoas colaborando em 4 a 10 arquivos nos últimos 28 dias.
        - Denominador: Número total de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos um dos últimos 28 dias.
      - **Colaboração em 11 ou mais arquivos:**
        - Numerador: número de pessoas colaborando em 11 ou mais arquivos nos últimos 28 dias.
        - Denominador: Número total de pessoas que tiveram acesso ao OneDrive ou Ao SharePoint por pelo menos um dos últimos 28 dias.
        
4. **Link para recursos:** Selecione este link para exibir o conteúdo da ajuda.

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>Força de desempenho de rede para OneDrive e SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="Gráfico mostrando o desempenho da rede para OneDrive e SharePoint.":::

1. **Header:** Realça a porcentagem de dispositivos fora de todos os testados que têm uma conexão de rede ruim com o OneDrive e o SharePoint. 
2. **Corpo:** Fornece informações sobre por que o desempenho da conexão de rede é importante para a colaboração. 
3. **Visualização:** Mostra uma porcentagem de dispositivos com níveis diferentes de desempenho de conectividade de rede relacionados ao OneDrive e ao SharePoint:
      - **81-100 (melhor)**: a parte verde escuro (colorida) da barra representa a porcentagem de dispositivos com o melhor desempenho.
      - **61-80**: A parte verde (colorida) da barra representa a porcentagem de dispositivos com uma pontuação de desempenho de rede entre 60 e 80. 
      - **41-60**: A parte laranja (colorida) da barra representa a porcentagem de dispositivos com uma pontuação de desempenho de rede entre 40 e 60. 
      - **21-40**: A parte vermelha (colorida) da barra representa a porcentagem de dispositivos com uma pontuação de desempenho de rede entre 20 e 40. 
      - **0-20**: A parte vermelha escura (colorida) da barra representa a porcentagem de dispositivos com a pior pontuação de desempenho de rede entre 0 e 20. 

## <a name="related-content"></a>Conteúdo relacionado

[Saúde dos aplicativos do Microsoft 365 – Experiências de tecnologia](apps-health.md) (artigo)\
[Comunicação – Experiências de pessoas](communication.md) (artigo)\
[Reuniões – Experiências de pessoas](meetings.md) (artigo)\
[Mobilidade – Experiências de pessoas](mobility.md) (artigo)\
[Controles de privacidade para Pontuação de Produtividade](privacy.md) (artigo)\
[Trabalho em equipe – Experiências de pessoas](teamwork.md) (artigo)
