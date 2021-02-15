---
title: Aumentar a proteção contra ameaças do Microsoft 365 Business Premium
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
description: Configurar recursos de conformidade para evitar a perda de dados e ajudar a manter suas informações confidenciais e de seus clientes seguras.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841164"
---
# <a name="set-up-compliance-features"></a>Configure os recursos de conformidade

O Microsoft 365 Business Premium vem com recursos para proteger seus dados e dispositivos e ajudar você a manter suas informações confidenciais e de seus clientes seguras.

## <a name="set-up-dlp-features"></a>Configurar recursos de DLP

Consulte [Criar uma política de DLP a](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) partir de um modelo para ver um exemplo de como configurar uma política para proteger contra a perda de dados pessoais. 
  
A DLP vem com muitos modelos de política prontos para uso para muitas localidades diferentes. Por exemplo, Dados Financeiros da Austrália, Ato de Informações Pessoais do Canadá, Dados Financeiros dos EUA e assim por diante. Veja [o que os modelos de política de DLP incluem](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) para uma lista completa. Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo de PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar a retenção de email com o Arquivamento do Exchange Online

 **Os recursos de licença** do Arquivamento do Exchange Online ajudam a manter os padrões de conformidade e regulamentação, preservando o conteúdo de email para a Descoberta Eletrônico. Ele também ajuda a reduzir o risco se houver um processo e fornece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos. Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que você deseja preservar.
  
**Hold de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando toda a caixa de correio do usuário em espera de litígio. 
    
Para colocar uma caixa de correio em espera de litígio, no Centro de administração:
    
1. In the left nav, go to **Users** \> **Active users**.
    
2. Selecione um usuário cuja caixa de correio você deseja colocar em espera de litígio. No painel do usuário, **expanda configurações de** email e, ao lado de **Mais configurações,** escolha **Editar propriedades do Exchange.**
    
3. Na página da caixa de correio para o usuário, escolha ** recursos de caixa de correio ** no **nav** esquerdo e, em seguida, escolha o link Habilitar em responsabilidade **de litígio**.
    
4. Na caixa **de diálogo de** espera de litígio, você pode especificar a duração da espera de litígio no campo de duração de espera **de** litígio. Deixe o campo vazio se quiser colocar uma espera infinita. Você também pode adicionar anotações e direcionar o proprietário da caixa de correio a um site que talvez seja preciso explicar mais sobre a espera de litígio. \>**Salvar**.
    
**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar por um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção. Para saber mais, consulte [Visão geral das políticas de retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

## <a name="set-up-sensitivity-labels"></a>Configurar rótulos de sensibilidade

Os rótulos de sensibilidade vêm com o Plano 1 da Proteção de Informações do Azure (AIP) e ajudam a classificar e, opcionalmente, proteger seus documentos e emails aplicando rótulos. Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou usando uma combinação na qual os usuários têm recomendações.

Para configurar rótulos de sensibilidade, veja [o vídeo criar e gerenciar rótulos de sensibilidade.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>Instalar o cliente da Proteção de Informações do Azure manualmente

Para instalar manualmente o cliente AIP:

1. Baixe **AzinfoProtection_UL.exe** centro [de download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. Você pode verificar se a instalação funcionou visualizando  um documento do Word e verificando se a opção Sensibilidade está disponível na **guia** Página Home.
<br/>![Guia de proteção em um documento do Word.](../media/word-sensitivity.png)

Para obter mais informações, consulte [Instalar o cliente.](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)
