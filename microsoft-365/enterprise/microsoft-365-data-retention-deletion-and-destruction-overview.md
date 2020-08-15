---
title: Retenção, Exclusão e Destruição de Dados no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Uma visão geral das políticas da Microsoft para o Microsoft 365 em relação à retenção, exclusão e destruição de dados.
ms.openlocfilehash: c522c1a1a4de46a4fc36bd87a031be8b47c5523d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687108"
---
# <a name="data-retention-deletion-and-destruction-in-microsoft-365"></a>Retenção, Exclusão e Destruição de Dados no Microsoft 365

A Microsoft tem uma política padrão de manipulação de dados para o Microsoft 365 que especifica por quanto tempo os dados do cliente são mantidos após a exclusão. Em geral, há dois cenários nos quais os dados do cliente são excluídos:

- **Exclusão ativa**: o locatário tem uma assinatura ativa e um usuário ou administrador exclui os dados ou os administradores excluem um usuário.
- **Exclusão passiva**: a assinatura do locatário termina.

## <a name="data-retention"></a>Retenção de dados

Para cada um desses cenários de exclusão, a tabela a seguir mostra o período máximo de retenção de dados, por categoria e classificação de dados:

| Categoria de dados | Classificação de dados | Descrição | Exemplos | Período de retenção |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Dados do cliente | Conteúdo do cliente| Conteúdo fornecido diretamente/criado por administradores e usuários <br><br> Inclui todos os textos, sons, vídeos, arquivos de imagem e software criados e armazenados nos data centers da Microsoft ao usar os serviços no Microsoft 365 | Exemplos de aplicativos do Microsoft 365 usados com mais frequência que permitem aos usuários criar dados incluem Word, Excel, PowerPoint, Outlook e OneNote <br><br> O conteúdo do cliente também inclui segredos de Propriedade do cliente/fornecidos (senhas, certificados, chaves de criptografia, chaves de armazenamento) | **Cenário de exclusão ativa:** no máximo 30 dias <br><br> **Cenário de exclusão passiva:** no máximo 180 dias |
| Dados do cliente | Informações de identificação do usuário final (EUII) | Dados que identificam ou podem ser usados para identificar o usuário de um serviço Microsoft. EUII não contém conteúdo do cliente | Nome de usuário ou nome de exibição (domínio \ nome_de_usuário) <br><br> Nome principal do usuário (name@domain) <br><br>  Endereços IP específicos do usuário | **Cenário de exclusão ativa:** no máximo 180 dias (apenas uma ação de administrador de locatário) <br><br> **Cenário de exclusão passiva:** no máximo 180 dias |
| Dados pessoais <br> (dados não incluídos nos dados do cliente) | Identificadores de pseudônimos do usuário final (EUPI) | Um identificador criado pela Microsoft ligado ao usuário de um serviço Microsoft. Quando combinado com outras informações, como uma tabela de mapeamento, EUPI identifica o usuário final <br><br> EUPI não contém informações carregadas ou criadas pelo cliente | GUIDs de usuário, PUIDs ou SIDs <br><br> IDs de sessão | **Cenário de exclusão ativa:** no máximo 30 dias <br><br> **Cenário de exclusão passiva:** no máximo 180 dias |

## <a name="subscription-retention"></a>Retenção de assinatura

No termo de uma assinatura ativa, um assinante pode acessar, extrair ou excluir dados do cliente armazenados no Microsoft 365. Se uma assinatura paga terminar ou for finalizada, a Microsoft manterá os dados do cliente armazenados no Microsoft 365 em uma conta de função limitada por 90 dias para habilitar o assinante a extrair os dados. Após o término do período de retenção de 90 dias, a Microsoft desabilita a conta e exclui os dados do cliente. Não mais de 180 dias após a expiração ou o encerramento de uma assinatura para a Microsoft 365, a Microsoft desabilita a conta e exclui todos os dados do cliente da conta. Quando o período de retenção máximo de qualquer dado tiver decorrido, os dados são renderizados de uma recuperação comercial.

Para uma avaliação gratuita, sua conta é movida para um status de cortesia por 30 dias na maioria dos países e regiões. Durante esse período de cortesia, você pode comprar o Microsoft 365. Se você decidir não comprar o Microsoft 365, poderá cancelar sua avaliação ou deixar que o período de cortesia expire, e as informações e dados da sua conta serão excluídos.

## <a name="expedited-deletion"></a>Exclusão acelerada

Para qualquer assinatura, um assinante pode entrar em contato com o suporte da Microsoft e solicitar o provisionamento acelerado de assinatura. Nesse processo, todos os dados do usuário são excluídos três dias após o administrador inserir o código de bloqueio fornecido pela Microsoft. Isso inclui dados no SharePoint Online e no Exchange Online em retenção ou armazenados em caixas de correio inativas.

Para obter mais informações sobre o provisionamento acelerado, confira [cancelar sua assinatura](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription).

## <a name="related-links"></a>Links relacionados

- [Destruição de dados](microsoft-365-data-destruction.md)

- [Imutabilidade no Office 365](microsoft-365-data-immutability.md)
- [Exclusão de dados do Exchange Online](microsoft-365-exchange-online-data-deletion.md)
- [Exclusão de dados do SharePoint Online](microsoft-365-sharepoint-online-data-deletion.md)
- [Exclusão de dados do Skype for Business ](microsoft-365-skype-data-deletion.md)
