---
title: Preparar dados para a Descoberta Eletrônica Avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Saiba como usar o centro de &amp; conformidade de segurança para preparar dados para análise com a descoberta eletrônica avançada. '
ms.openlocfilehash: 25b500e88e53dfae9b8fa9d504a402f4e2f7ce12
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208095"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>Preparar dados para descoberta eletrônica avançada (clássico)

Este tópico descreve como carregar os resultados de uma pesquisa de conteúdo em um caso na descoberta eletrônica avançada (clássico). 
  
> [!IMPORTANT]
> À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*. Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como * solução de Descoberta Eletrônica Avançada no Microsoft 365*) o mais rápido possível. O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão. Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>Etapa 1: preparar dados para descoberta eletrônica avançada

Para analisar dados com a descoberta eletrônica avançada, você pode usar os resultados de uma pesquisa de conteúdo que você executa no centro de conformidade de segurança do Microsoft 365 &amp; (listado na página de **pesquisa de conteúdo** no centro de conformidade de segurança da Microsoft 365 &amp; ) ou uma pesquisa associada a uma ocorrência de descoberta eletrônica (listada na página **descoberta eletrônica** no centro de conformidade de segurança &amp; ). 
  
Para obter as etapas detalhadas sobre como preparar resultados de pesquisa para análise na descoberta eletrônica avançada, consulte [preparar resultados de pesquisa para descoberta eletrônica avançada](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Se você tiver dados fora do Microsoft 365 e quiser importá-los para a Microsoft 365 para que você possa preparar e analisá-lo na descoberta eletrônica avançada, veja [visão geral da importação de arquivos pst para o Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) e [arquivamento de dados de terceiros](https://go.microsoft.com/fwlink/p/?linkid=716918). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Etapa 2: carregar dados de resultados de pesquisa em um caso na descoberta eletrônica avançada

Após preparar os resultados da pesquisa no &amp; centro de conformidade de segurança para análise, a próxima etapa é carregar os resultados da pesquisa em um caso de descoberta eletrônica avançada. Para obter informações mais detalhadas, consulte [executar o módulo de processo](run-the-process-module-in-advanced-ediscovery.md).
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. No Centro de Conformidade e Segurança, clique em **Pesquisa e investigação** \> **Descoberta Eletrônica** para exibir a lista de casos na sua organização. 
    
4. Clique em **abrir** ao lado do caso para o qual você deseja carregar dados na descoberta eletrônica avançada. 
    
5. Na página **Início** do caso, clique em **Descoberta Eletrônica Avançada**. 
    
    ![Clique em alternar para descoberta eletrônica avançada para abrir o caso na descoberta eletrônica avançada](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    A barra de progresso **conectando-se à descoberta eletrônica avançada** é exibida. Quando você estiver conectado à descoberta eletrônica avançada, uma lista de contêineres será exibida na página de configuração do caso. 
    
    ![O caso é exibido na descoberta eletrônica avançada](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Esses contêineres representam os resultados de pesquisa que você preparou para análise na descoberta eletrônica avançada na etapa 1. Observe que o nome do contêiner tem o mesmo nome da pesquisa de conteúdo no caso do centro de conformidade de segurança &amp; . Os contêineres na lista são aqueles que você preparou. Se um usuário diferente preparou resultados de pesquisa para descoberta eletrônica avançada, os contêineres correspondentes não serão incluídos na lista. 
    
6. Para carregar os dados de resultado de pesquisa de um contêiner para o caso na descoberta eletrônica avançada, selecione um contêiner e clique em **processo**.
    
Após os resultados da pesquisa do centro de conformidade de segurança &amp; serem adicionados ao caso na descoberta eletrônica avançada, a próxima etapa é usar as ferramentas da descoberta eletrônica avançada para analisar e examinar os dados relevantes para o caso. 
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Configurar usuários e casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analisar os dados do caso](analyze-case-data-with-advanced-ediscovery.md)
  
[Gerenciamento da configuração de relevância](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Usar o módulo de Relevância](use-relevance-in-advanced-ediscovery.md)
  
[Exportar dados de caso](export-case-data-in-advanced-ediscovery.md)

