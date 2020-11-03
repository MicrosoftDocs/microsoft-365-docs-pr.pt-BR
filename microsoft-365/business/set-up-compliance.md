---
title: Aumentar a proteção contra ameaças para o Microsoft 365 Business Premium
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
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurar recursos de conformidade para evitar a perda de dados e ajudar a manter a segurança de informações confidenciais de seus clientes.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841164"
---
# <a name="set-up-compliance-features"></a>Configure os recursos de conformidade

O Microsoft 365 Business Premium vem com recursos para proteger seus dados e dispositivos e ajudar você a manter a segurança de informações confidenciais de seus clientes.

## <a name="set-up-dlp-features"></a>Configurar recursos de DLP

Consulte [criar uma política de DLP a partir de um modelo](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) para obter um exemplo de como configurar uma política de proteção contra a perda de dados pessoais. 
  
A DLP vem com vários modelos de política prontos para uso para várias localidades diferentes. Por exemplo, dados financeiros da Austrália, ato de informações pessoais do Canadá, dados financeiros dos EUA e assim por diante. Veja o [que os modelos de política de DLP incluem](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) para uma lista completa. Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar a retenção de email com o arquivamento do Exchange Online

 Os recursos de licença de **arquivamento do Exchange Online** ajudam a manter os padrões de conformidade e regulamentação ao preservar o conteúdo de email para descoberta eletrônica. Isso também ajuda a reduzir o risco se houver uma ação judicial e oferece uma maneira de recuperar dados após uma violação de segurança ou quando você precisar recuperar itens excluídos. Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que você deseja preservar.
  
**Retenção de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando a caixa de correio de um usuário em retenção de litígio. 
    
Para colocar uma caixa de correio em retenção de litígio, no centro de administração:
    
1. No painel de navegação à esquerda, vá para usuários ativos do **usuário** \> **Active users** .
    
2. Selecione um usuário cuja caixa de correio você deseja colocar em retenção de litígio. No painel usuário, expanda **configurações de email** e ao lado de **mais configurações** , escolha **Editar propriedades do Exchange** .
    
3. Na página caixa de correio do usuário, escolha * * recursos de caixa de correio * * no painel de navegação esquerdo e, em seguida, escolha o link **habilitar** em **retenção de litígio** .
    
4. Na caixa de diálogo **retenção de litígio** , é possível especificar a duração da retenção de litígio no campo duração da **retenção de litígio** . Deixe o campo vazio se você quiser colocar uma retenção infinita. Você também pode adicionar notas e direcionar o proprietário da caixa de correio para um site que pode ser necessário para explicar mais sobre a retenção de litígio. \>**Salvar** .
    
**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção. Para saber mais, confira [visão geral das políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>Configurar rótulos de confidencialidade

Os rótulos de confidencialidade vêm com o plano 1 do Windows Information Protection (AIP) e ajudam você a classificar e, opcionalmente, proteger seus documentos e emails, aplicando rótulos. Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou usando uma combinação em que os usuários recebem recomendações.

Para configurar rótulos de sensibilidade, exiba o vídeo [criar e gerenciar rótulos de confidencialidade](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .



### <a name="install-the-azure-information-protection-client-manually"></a>Instalar o cliente de proteção de informações do Azure manualmente

Para instalar manualmente o cliente AIP:

1. Baixe **AzinfoProtection_UL.exe** do [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Você pode verificar se a instalação funcionou exibindo um documento do Word e certificando-se de que a opção de **sensibilidade** esteja disponível na guia **página inicial** .
<br/>![Menu suspenso proteção de guia em um documento do Word.](../media/word-sensitivity.png)

Para obter mais informações, consulte [instalar o cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
