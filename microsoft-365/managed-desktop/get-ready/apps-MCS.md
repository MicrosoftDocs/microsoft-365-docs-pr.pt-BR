---
title: Trabalhar com Serviços de consultoria da Microsoft
description: preparação e etapas a seguir para trabalhar com MCS para empacotar seus aplicativos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, MCS, empacotamento
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841418"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabalhar com Serviços de consultoria da Microsoft

Você pode se envolver com os Serviços de Consultoria da Microsoft (MCS) para obter seus aplicativos empacotados para uso com a Área de Trabalho Gerenciada da Microsoft. Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com MCS e escopo do seu projeto de empacotamento de aplicativo específico.

## <a name="roles-and-responsibilities"></a>Funções e responsabilidades

Para trabalhar com o empacotamento de aplicativos MCS, **você deve fornecer estes elementos:**

- Os arquivos do instalador de origem (por exemplo, setup.exe ou .msi).
- As instruções de instalação, especificando detalhes sobre a aparência da instalação final. Por exemplo, deve haver um atalho da área de trabalho para o aplicativo? Qual deve ser a visibilidade do aplicativo? O aplicativo deve se conectar a um servidor e, em caso sim, qual deles? Para obter detalhes, consulte o modelo [de solicitação de empacotamento de aplicativo.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme necessário em seu ambiente.

**O MCS cuidará dessas ações:**

- Verificar se o aplicativo é proibido ou restrito no ambiente da Área de Trabalho Gerenciada da Microsoft.
- Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com o Windows 10. Se o MCS descobrir um problema de compatibilidade, eles entregarão o aplicativo ao programa Desktop [App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) para correção.
- Empacotando o aplicativo à sua especificação e testando a implantação do aplicativo usando o Microsoft Intune.

## <a name="app-delivery-schedule"></a>Cronograma de entrega do aplicativo

Inicie o processo de empacotamento carregando as informações do aplicativo no portal da Área de Trabalho Gerenciada da Microsoft. A equipe de empacotamento revisa novos envios toda quinta-feira. Após a revisão e o empacotamento, os aplicativos empacotados serão entregues na sexta-feira seguinte. Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.

![calendário mostrando o fluxo de aplicativo em uma quinta-feira (dia 21 neste exemplo), validação de mídia no dia seguinte, empacotamento na segunda-feira seguinte (dia 25) e entrega de aplicativo na sexta-feira subsequente (dia 29)](../../media/MCS-cal.png)

Você será notificado depois que o aplicativo tiver sido entregue. Nesse ponto, você tem 21 dias para executar testes de aceitação e aprovar o trabalho no portal da Área de Trabalho Gerenciada da Microsoft. Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal da Área de Trabalho Gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.

## <a name="testing-accounts-and-environment"></a>Testando contas e ambiente

Para que a equipe de empacotamento conclua a migração para o Microsoft Intune, recomendamos que você forneça determinadas permissões:
 
-   Acesso aos recursos de Implantação de Aplicativo do Microsoft Intune para o empacotador adicionar e atribuir o aplicativo 
-   Grupos de teste, contas de usuário e licenças para que os empacotadores sejam capazes de testar os aplicativos

O MCS usará essas permissões para executar as seguintes ações:
 
-   Garantir que o aplicativo funcione em uma máquina virtual configurada para a Área de Trabalho Gerenciada da Microsoft
-   Carregar o aplicativo no Microsoft Intune para implantação para seus usuários

Sem essas permissões, é possível que o MCS avance, mas eles não poderão carregar os aplicativos em seu ambiente.


