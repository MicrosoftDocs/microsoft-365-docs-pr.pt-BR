---
title: Preparar resultados de pesquisa para Descoberta Eletrônica Avançada do Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Saiba como preparar os resultados de uma pesquisa de conteúdo no centro de conformidade & segurança no Office 365 para análise adicional com a ferramenta de descoberta eletrônica avançada.
ms.openlocfilehash: 244fae317964261ad1eeadbdca2d4dffeda0a23a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073433"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>Preparar resultados de pesquisa para Descoberta Eletrônica Avançada do Office 365

Depois que uma pesquisa associada a um caso de descoberta eletrônica no centro de conformidade & segurança for executada com êxito, você poderá preparar os resultados da pesquisa para análise adicional com a descoberta eletrônica avançada do Office 365, que permite analisar conjuntos de dados grandes e não estruturados e Reduza a quantidade de dados relevantes para um caso jurídico. Os recursos avançados de descoberta eletrônica incluem:
  
- **Reconhecimento óptico de caracteres** : ao preparar os resultados de pesquisa para descoberta eletrônica avançada, a funcionalidade de reconhecimento óptico de caracteres (OCR) extrai automaticamente o texto de imagens e o inclui com os resultados de pesquisa que são carregados no no Descoberta eletrônica avançada para análise. O OCR tem suporte para arquivos soltos, anexos de email e imagens incorporadas. Isso permite que você aplique os recursos analíticos de texto de descoberta eletrônica avançada (quase duplicatas, threads de email, temas e codificação de previsão) ao conteúdo de texto em arquivos de imagem. O OCR de descoberta eletrônica avançada oferece suporte aos seguintes formatos de arquivos de imagem:

    - GIF
    - JPEG
    - JPG
    - PNG
    - TIFF
    
- **Detecção quase duplicada** : permite que você estruture sua análise de dados com mais eficiência, portanto, uma pessoa revisa um grupo de documentos semelhantes. Isso ajuda a evitar que vários revisores tenham que exibir versões diferentes do mesmo documento. 
    
- **Encadeamento de email** – ajuda a identificar as mensagens exclusivas em um thread de email para que você possa se concentrar apenas nas novas informações de cada mensagem. Em uma conversa de email, a segunda mensagem contém a primeira. Da mesma forma, as mensagens posteriores contêm todas as mensagens anteriores. O encadeamento de emails remove a necessidade de revisar cada mensagem inteira em um thread de email. 
    
- **Temas** : ajuda você a obter informações valiosas sobre seus dados além das estatísticas de pesquisa de palavra-chave. Os temas ajudam nas investigações agrupando documentos relacionados para que você possa examiná-los em contexto. Ao usar temas, você pode exibir os temas relacionados para um conjunto de documentos, determinar qualquer sobreposição e, em seguida, identificar as seções cruzadas de dados relacionados. 
    
- **Codificação preditiva** : permite que você treine o sistema do que você está procurando, permitindo tomar decisões (sobre se algo é relevante ou não) em um pequeno conjunto de documentos. A descoberta eletrônica avançada, em seguida, aplica o aprendizado (com base nas suas diretrizes) durante a análise de todos os documentos no conjunto de dados. Com base nesse aprendizado, a descoberta eletrônica avançada fornece uma classificação de relevância para que você possa decidir quais documentos serão revisados com base em qual documento é o mais provável de ser relevante para o caso. 
    
- **Exportando dados para aplicativos de revisão** -você pode exportar dados de descoberta eletrônica avançada e do Office 365 depois de concluir a análise e reduzir o conjunto de dados. O pacote de exportação inclui um arquivo CSV que contém as propriedades do conteúdo exportado e dos metadados da análise. Esse pacote de exportação pode ser importado para um aplicativo de análise de descoberta eletrônica. 
    
## <a name="before-you-begin"></a>Antes de começar

- Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada. Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5. 
    
- Você precisa ser um gerente de descoberta eletrônica ou um administrador de descoberta eletrônica no centro de conformidade de & de segurança para preparar resultados de pesquisa para descoberta eletrônica avançada. Um Gerente de Descoberta Eletrônica é membro do grupo de função de Gerente de Descoberta Eletrônica. Um Administrador de Descoberta Eletrônica também é membro do grupo de função de Gerente de Descoberta Eletrônica, mas privilégios adicionais de Descoberta Eletrônica lhe foram atribuídos. Para obter instruções sobre como atribuir permissões de administrador de descoberta eletrônica, confira a etapa 1 em [casos de descoberta eletrônica](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Etapa 1: preparar resultados de pesquisa para descoberta eletrônica avançada

Você pode preparar os resultados de uma pesquisa associada a uma ocorrência de descoberta eletrônica. Ao preparar resultados de pesquisa para descoberta eletrônica avançada, os dados são carregados e temporariamente armazenados em uma área de armazenamento exclusiva do Windows Azure na nuvem da Microsoft. Nesse ponto, a funcionalidade do OCR extrai texto de imagens nos resultados da pesquisa. Na [etapa 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), esse texto e os outros dados de resultados da pesquisa são carregados no caso da descoberta eletrônica avançada.
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso em que você deseja preparar os resultados da pesquisa para análise na descoberta eletrônica avançada. 
    
3. Na **Home** Page do caso, clique em **Pesquisar**e selecione a pesquisa.
    
4. No painel de detalhes, em **analisar resultados com descoberta eletrônica avançada**, clique em **preparar resultados para análise**.
    
    > [!NOTE]
    > Se os resultados de pesquisa tiverem mais de sete dias, você será solicitado a atualizá-los. 
  
5. Na página **Preparar os resultados para análise**, faça o seguinte:  
    
    - Opte por preparar itens indexados, itens indexados e não indexados ou apenas itens não indexados para análise na descoberta eletrônica avançada.
    
    - Escolha se deseja incluir todas as versões de documentos encontrados no SharePoint que atendam aos critérios de pesquisa. Essa opção será mostrada apenas se as fontes de conteúdo da pesquisa incluírem sites.
    
    - Especifique se você deseja que uma mensagem de notificação seja enviada (ou copiada) para uma pessoa quando o processo de preparação for concluído e os dados estiverem prontos para serem processados na descoberta eletrônica avançada.
    
6. Clique em **Preparar**.
    
    Os resultados da pesquisa estão preparados para análise com descoberta eletrônica avançada.
    
7. No painel de detalhes, clique em **verificar status de preparação** para exibir informações sobre o processo de preparação. Quando o processo de preparação for concluído, você poderá ir para o caso em descoberta eletrônica avançada para processar os dados para análise. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Etapa 2: adicionar os dados dos resultados da pesquisa ao caso na descoberta eletrônica avançada
<a name="step2"> </a>

Quando a preparação é concluída, a próxima etapa é usar a descoberta eletrônica avançada e carregar os dados dos resultados da pesquisa (que foram carregados para uma área de armazenamento do Azure na nuvem da Microsoft) para o caso na descoberta eletrônica avançada. Conforme explicado anteriormente, para acessar a descoberta eletrônica avançada, você precisa ser um administrador de descoberta eletrônica no centro de conformidade & segurança ou um administrador na descoberta eletrônica avançada.
  
> [!NOTE]
> O tempo necessário para que os dados do centro de conformidade & de segurança fique disponível para adicionar a um caso na descoberta eletrônica avançada varie, dependendo do tamanho dos resultados da pesquisa de descoberta eletrônica. 
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja carregar dados na descoberta eletrônica avançada. 
    
3. Na página **Início** do caso, clique em **Descoberta Eletrônica Avançada**. 
    
    ![Clique em alternar para descoberta eletrônica avançada para abrir o caso na descoberta eletrônica avançada](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    A barra de progresso **conectando-se à descoberta eletrônica avançada** é exibida. Quando você estiver conectado à descoberta eletrônica avançada, uma lista de contêineres será exibida na página de configuração do caso. 
    
    ![O caso é exibido na descoberta eletrônica avançada](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Esses contêineres representam os resultados de pesquisa que você preparou para análise na descoberta eletrônica avançada na etapa 1. Observe que o nome do contêiner tem o mesmo nome da pesquisa no caso no centro de conformidade de & de segurança. Os contêineres na lista são aqueles que você preparou. Se um usuário diferente preparou resultados de pesquisa para descoberta eletrônica avançada, os contêineres correspondentes não serão incluídos na lista. 
    
4. Para carregar os dados de resultado de pesquisa de um contêiner para o caso na descoberta eletrônica avançada, selecione um contêiner e clique em **processo**.
    
## <a name="next-steps"></a>Próximas etapas

Depois que os resultados de uma pesquisa de descoberta eletrônica são adicionados a um caso, a próxima etapa é usar as ferramentas de descoberta eletrônica avançadas para analisar os dados e identificar o conteúdo que responde a um caso jurídico específico. Para obter informações sobre como usar a descoberta eletrônica avançada, confira a [descoberta eletrônica avançada do Office 365](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Mais informações

Todas as mensagens de email criptografadas por RMS incluídas nos resultados da pesquisa serão descriptografadas quando você prepará-las para análise na descoberta eletrônica avançada. Esse recurso de descriptografia é habilitado por padrão para membros do grupo de funções Gerenciador de descoberta eletrônica. Isso ocorre porque a função de gerenciamento de descriptografia do RMS é atribuída a esse grupo de função. Lembre-se das seguintes coisas em relação à descriptografia de mensagens de email:
  
- Atualmente, esse recurso de descriptografia não inclui conteúdo criptografado de sites do SharePoint e do OneDrive for Business. Somente mensagens de email criptografadas por RMS serão descriptografadas quando você exportá-las.
    
- Se uma mensagem de email criptografada por RMS tiver um anexo (como um documento ou outra mensagem de email) também criptografada, somente a mensagem de email de nível superior será descriptografada.
    
- Se você precisar impedir que alguém descriptografe mensagens criptografadas por RMS ao preparar resultados de pesquisa para análise na descoberta eletrônica avançada, será necessário criar um grupo de função personalizado (copiando o grupo de função de Gerenciador de descoberta eletrônica interno) e remover o RMS Descriptografar função de gerenciamento do grupo de função personalizado. Em seguida, adicione a pessoa que você não deseja descriptografar mensagens como um membro do grupo de função personalizado.
