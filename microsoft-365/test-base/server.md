---
title: Windows Teste de aplicativo de servidor
description: Como validar com testes de aplicativos do Windows Server
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: d6e6d2098ab187d2473acb5dcf0c3938a9ef7459
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322490"
---
# <a name="windows-server-application-testing"></a>Windows Teste de aplicativo de servidor 

Com a Base de Teste para Microsoft 365, agora você pode validar seus aplicativos em relação Windows Server 2016 2019, incluindo Server Core!

Para começar a validar seus aplicativos carregados em atualizações de pré-lançamento para sistemas operacionais Windows Server 2016 e 2019 na Base de Teste para Microsoft 365, acate as seguintes etapas:

1.   Faça logoff no nosso portal de integração de autoatendamento. No menu de navegação do lado esquerdo, selecione ```Upload new package``` em e preencha os detalhes do ```Package catalogue``` teste.

2.  Selecione ```Security updates``` como o tipo de atualização do sistema operacional:

![Selecionar atualizações de segurança](Media/selecting-security-updates.png)

3. Em versões do sistema operacional a testar, selecione as versões do sistema operacional aplicáveis. Você pode selecionar Windows versões do sistema operacional do Servidor ou uma combinação de versões do sistema operacional cliente e servidor.

![Selecionar versão do sistema operacional](Media/selecting-OS-versions.png)

4. Forneça outras informações necessárias, revise os detalhes fornecidos e carregue seu pacote de aplicativos. Depois de carregar, você pode exibir o status do pacote na guia Gerenciar pacotes de menu.


5. Para exibir resultados de teste e insights da validação do seu aplicativo em relação às atualizações de segurança de pré-lançamento para o Windows Server 2016 e 2019, acesse a página Resumo de teste ou a página Resultados da atualização de segurança.

![Exibir resultados do teste](Media/access-test-results.png)

Avançar para o próximo artigo para começar com testes **funcionais**
> [!div class="nextstepaction"]
> [Próxima etapa](functional.md)

