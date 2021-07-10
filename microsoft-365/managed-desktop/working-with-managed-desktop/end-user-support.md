---
title: Obter suporte do usuário para Área de Trabalho Gerenciada da Microsoft
description: Como os usuários podem obter ajuda com o serviço e dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362601"
---
# <a name="getting-help-for-users"></a>Obter ajuda para usuários

Se você atingiu o ponto [](../service-description/user-support.md) no fluxo de trabalho em que precisa solicitar acesso ou escalonamento de dispositivos elevados para a Microsoft, siga estas etapas:
 
>[!NOTE]
>Essas opções de suporte não estão disponíveis para dispositivos no grupo Teste.

## <a name="elevation-requests"></a>Solicitações de elevação

Antes de solicitar acesso elevado a um dispositivo, é melhor revisar quais ações são mais adequadas.

- **As ações típicas** são para as quais esse processo se destina e seria executado rotineiramente durante a solução de problemas com Área de Trabalho Gerenciada da Microsoft dispositivos. Os exemplos incluem:
    - Elevar os solução de problemas do sistema integrado, o prompt de comando ou Windows PowerShell
    - Solução de problemas de aplicativos de linha de negócios
    - Usar uma solução alternativa para corrigir algo que deve funcionar pelo design (como a ativação do BitLocker ou o tempo do sistema não atualizando)
    - Elevar o Gerenciador de Dispositivos para fazer coisas como atualizar drivers, desinstalar um dispositivo ou verificar novas alterações

- **As ações que não são recomendadas** incluem o seguinte:
    - Instalar softwares ou navegadores
    - Instalar drivers fora das configurações Windows, incluindo os para periféricos
    - Instalando .msi ou .exe arquivos
    - Instalando Windows recursos

- **As ações que não são suportadas** incluem o seguinte:
    - Instalar softwares ou recursos que conflitam com Área de Trabalho Gerenciada da Microsoft ou operações de gerenciamento ou segurança
    - Desabilitar um recurso Windows que é necessário para Área de Trabalho Gerenciada da Microsoft, como o BitLocker
    - Modificando configurações gerenciadas por sua organização

### <a name="to-request-elevation"></a>Para solicitar elevação

1. Vá para o portal em [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e entre com suas credenciais Azure Active Directory de usuário.
2. Selecione **Nova solicitação de elevação**.
3. Forneça estes detalhes:
    - **ID do tíquete de** suporte do seu próprio sistema de tíquetes de suporte.
    - **Nome do** dispositivo : insira o número de série do dispositivo e selecione o dispositivo no menu.
    - **Categoria**: selecione a categoria que melhor se ajusta ao seu problema. Se nenhuma opção parecer próxima, selecione **Outro** e forneça mais informações nos campos **Título** e **Plano de ação.** É melhor selecionar uma categoria, se possível.
    - **Subcategoria**: selecione o que melhor se encaixa no problema. Se nenhuma opção parecer próxima, selecione **Outro** e forneça uma breve descrição em **Title**. Em **Plano de ação,** forneça as etapas de solução de problemas que você planeja tomar depois que a elevação for concedida.
4. Selecione **Enviar**.


## <a name="escalation-requests"></a>Solicitações de escalonamento


Se você precisar [escalar um](../service-description/user-support.md#escalation-portal) problema para a Microsoft, siga estas etapas:

1. Vá para o portal em [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e entre com suas credenciais Azure Active Directory de usuário.
2. Selecione **Solicitações de Escalonamento** e selecione **Nova solicitação de escalonamento.**
3. Forneça estes detalhes:
    - **Categoria**: selecione a categoria que melhor se ajusta ao seu problema.
    - **Título:** forneça uma descrição muito breve.
    - **Descrição**: adicione quaisquer detalhes adicionais que podem ajudar nossa equipe a entender o problema. Se precisar anexar arquivos, você pode fazer isso voltando à solicitação depois de enviar.
    - **Principais informações de contato**: Forneça informações sobre como entrar em contato com a principal pessoa responsável por trabalhar com nossa equipe.
4. Selecione **Enviar**.
5. Revisite o tíquete no mesmo portal para interagir com nossa equipe.

> [!NOTE]
> Somente problemas de Severidade C podem ser escalonados por esse caminho. Para outros problemas, contate o administrador de IT para arquivar a solicitação por meio do portal de administração.