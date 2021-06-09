---
title: Trabalhar com Serviços de consultoria da Microsoft
description: Preparação e etapas a seguir para trabalhar com o MCS para empacotar seus aplicativos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840881"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabalhar com Serviços de consultoria da Microsoft

Você pode se envolver com o Microsoft Consulting Services (MCS) para obter seus aplicativos empacotados para uso com Área de Trabalho Gerenciada da Microsoft. Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com MCS e escopo do projeto de empacotamento de aplicativos específico.

## <a name="roles-and-responsibilities"></a>Funções e responsabilidades

Para trabalhar com o empacotamento de aplicativos MCS, **você deve fornecer estes elementos:**

- Os arquivos do instalador de origem (por exemplo, setup.exe ou .msi).
- As instruções de instalação, especificando detalhes sobre como a instalação final deve ser. Por exemplo, deve haver um atalho da área de trabalho para o aplicativo? Qual deve ser a visibilidade do aplicativo? O aplicativo deve se conectar a um servidor e, em caso algum, qual deles? Para obter detalhes, consulte o modelo [de solicitação de empacotamento de aplicativos](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme necessário em seu ambiente.

**O MCS tratará dessas ações:**

- Verificar se o aplicativo é proibido ou restrito no ambiente Área de Trabalho Gerenciada da Microsoft ambiente.
- Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com Windows 10. Se o MCS descobrir um problema de compatibilidade, eles entregarão o aplicativo para o programa [de Garantia](/fasttrack/products-and-capabilities#app-assure) de Aplicativos para correção.
- Empacotando o aplicativo para sua especificação e testando a implantação do aplicativo usando Microsoft Intune.

## <a name="app-delivery-schedule"></a>Cronograma de entrega de aplicativos

Inicie o processo de empacotamento carregando as informações do aplicativo no portal Área de Trabalho Gerenciada da Microsoft. A equipe de empacotamento revisa novos envios toda quinta-feira. Após revisão e empacotamento, os aplicativos empacotados são entregues na sexta-feira seguinte. Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.

![calendar showing app inflow on a Thursday (the 21st in this example), media validation the next day, packaging on the following Monday (the 25th) and app delivery on the subsequent Friday (the 29th)](../../media/MCS-cal.png)

Você será notificado depois que o aplicativo tiver sido entregue. Nesse ponto, você tem 21 dias para realizar testes de aceitação e aprovar o trabalho no Área de Trabalho Gerenciada da Microsoft portal. Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal Área de Trabalho Gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.

## <a name="testing-accounts-and-environment"></a>Testar contas e ambiente

Para que a equipe de empacotamento conclua a migração para Microsoft Intune, recomendamos que você forneça determinadas permissões:

- Acesso aos Microsoft Intune de implantação de aplicativos do Microsoft Intune para o empacotador adicionar e atribuir o aplicativo
- Testar grupos, contas de usuário e licenças para que os empacotadores sejam capazes de testar os aplicativos

O MCS usará essas permissões para executar as seguintes ações:

- Garantir que o aplicativo funcione em máquina virtual configurada para Área de Trabalho Gerenciada da Microsoft
- Carregando o aplicativo para Microsoft Intune para implantação para seus usuários

Sem essas permissões, é possível que o MCS avance, mas eles não poderão carregar os aplicativos em seu ambiente.
