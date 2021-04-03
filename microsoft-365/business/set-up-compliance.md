---
title: Aumentar a proteção contra ameaças para o Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Configurar recursos de conformidade para evitar perda de dados e ajudar a manter as informações confidenciais de seus clientes e seus clientes seguros.
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579945"
---
# <a name="set-up-compliance-features"></a>Configure os recursos de conformidade

O Microsoft 365 Business Premium vem com recursos para proteger seus dados e dispositivos e ajudá-lo a manter suas informações confidenciais e de seus clientes seguros.

## <a name="set-up-dlp-features"></a>Configurar recursos DLP

Consulte [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data. 
  
A DLP vem com muitos modelos de política prontos para uso para muitas localidades diferentes. Por exemplo, Dados Financeiros da Austrália, Lei de Informações Pessoais do Canadá, Dados Financeiros dos EUA e assim por diante. Consulte [O que os modelos de política DLP incluem](../compliance/what-the-dlp-policy-templates-include.md) para uma lista completa. Todos esses modelos podem ser habilitados de forma semelhante ao exemplo do modelo PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar a retenção de email com Arquivamento do Exchange Online

 **Arquivamento do Exchange Online** de licença ajudam a manter padrões de conformidade e regulamentação, preservando o conteúdo de email para Descoberta Eletrônico. Ele também ajuda a reduzir seu risco se houver uma ação judicial e fornece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos. Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que deseja preservar.
  
**Litígio em espera:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando toda a caixa de correio de um usuário em espera de litígio. 
    
Para colocar uma caixa de correio em espera de litígio, no Centro de administração:
    
1. Na nav esquerda, vá para **Usuários** \> **Usuários ativos**.
    
2. Selecione um usuário cuja caixa de correio você deseja colocar em espera de litígio. No painel do usuário, expanda **Configurações de email** e, ao lado de **Mais** configurações, escolha Editar propriedades **do Exchange**.
    
3. Na página de caixa de correio do usuário, escolha ** recursos de caixa de correio ** na nav esquerda e escolha o link **Habilitar** em **responsabilidade de litígio.**
    
4. Na caixa **de diálogo de** hold de litígio, você pode especificar a duração da hold de litígio no campo Duração de 1/24/04/2016.  Deixe o campo vazio se quiser colocar uma ressalção infinita. Você também pode adicionar anotações e direcionar o proprietário da caixa de correio para um site, talvez seja preciso explicar mais sobre a hold de litígio. \>**Salvar**.
    
**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar por um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção. Para saber mais, confira [Visão geral das políticas de retenção.](../compliance/retention.md)

## <a name="set-up-sensitivity-labels"></a>Configurar rótulos de sensibilidade

Os rótulos de sensibilidade vêm com o Plano 1 da Proteção de Informações do Azure (AIP) e ajudam você a classificar e, opcionalmente, proteger seus documentos e emails aplicando rótulos. Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente pelos usuários ou usando uma combinação em que os usuários receberão recomendações.

Para configurar rótulos de sensibilidade, veja o vídeo [criar e gerenciar rótulos de sensibilidade.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>Instalar manualmente o cliente de Proteção de Informações do Azure

Para instalar manualmente o cliente AIP:

1. Baixe **AzinfoProtection_UL.exe** centro de [download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. Você pode verificar se a instalação funcionou exibindo um documento do Word e verificando se a opção **Sensibilidade** está disponível na **guia** Página Base.
<br/>![Guia de proteção listada em um documento do Word.](../media/word-sensitivity.png)

Para obter mais informações, consulte [Install the client](/azure/information-protection/infoprotect-tutorial-step3).