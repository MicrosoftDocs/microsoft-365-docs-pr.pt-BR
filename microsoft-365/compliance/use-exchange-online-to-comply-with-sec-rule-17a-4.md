---
title: Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma 17a-4 da SEC
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: A Cohasset Associates comprovou que, quando o Exchange Online e o Centro de Conformidade e Segurança são configurados conforme recomendado, eles atendem aos requisitos de armazenamento relevantes das normas 1.31(c)-(d) da CFTC, 4511 da FINRA e 17a-4 da SEC. A avaliação está disponível para baixar.
ms.openlocfilehash: 33db33589df60b52c4598c52d593b9a6fe4c9c10
ms.sourcegitcommit: 5de17ee0d88a8bec6c8b54bc576a9517ab6d0066
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41122420"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma 17a-4 da SEC

Caso a organização precise atender aos padrões regulamentares para retenção de dados, o Centro de Conformidade e Segurança do Office 365 fornece recursos para gerenciar o ciclo de vida dos dados no Exchange Online. Isso inclui a capacidade de reter, auditar, pesquisar e exportar os dados. Essas funcionalidades são adequadas para atender às necessidades da maioria das organizações.

No entanto, algumas organizações em setores altamente regulamentados estão sujeitas a requisitos regulamentares mais rigorosos. Por exemplo, instituições financeiras, como bancos ou corretoras, estão sujeitas à norma 17a-4 estabelecida pela SEC (Comissão de Títulos e Câmbio dos Estados Unidos). A norma 17a-4 tem requisitos específicos para armazenamento de dados eletrônicos, inclusive vários aspectos do gerenciamento de registros, como duração, formato, qualidade, disponibilidade e responsabilidade da retenção de registros.

Para ajudar essas organizações a entender melhor como aproveitar o Centro de Conformidade e Segurança para atender às obrigações regulamentares do Exchange Online, especificamente em relação aos requisitos da norma 17a-4, lançamos uma avaliação em parceria com a Cohasset Associates.

A Cohasset Associates comprovou que, quando o Exchange Online e o Centro de Conformidade e Segurança são configurados conforme recomendado, eles atendem aos requisitos de armazenamento relevantes das normas 1.31(c)-(d) da CFTC, 4511 da FINRA e 17a-4 da SEC. Visamos esse conjunto de normas porque elas representam a orientação mais normativa globalmente para retenção de registros por instituições financeiras.

## <a name="download-the-cohasset-assessment"></a>Baixar a avaliação da Cohasset

[Baixe a avaliação da Cohasset aqui](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Página de título da avaliação baixável da Cohasset Associates](media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>Esta avaliação foi feita especificamente para o Exchange Online

Observe que esta foi feita especificamente para o Exchange Online. Ela não inclui outros serviços do Office 365, como SharePoint Online ou OneDrive for Business. No entanto, estamos planejando o suporte para esses serviços visando atender à norma 17a-4 da SEC.

É importante entender que o Skype for Business e o Teams também armazenam dados no Exchange Online. Portanto, a avaliação abrange as mensagens do Skype for Business, bem como as mensagens de canal e chat do Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>O uso do Bloqueio de Preservação é fundamental para a configuração recomendada

Os setores altamente regulamentados são sempre obrigados a armazenar comunicações eletrônicas para atender ao requisito de WORM (gravar uma vez, ler muitas). Este requisito estabelece uma solução de armazenamento na qual um registro deve ser:

- Retido por um período de retenção obrigatório, que não pode ser reduzido, mas apenas aumentado.
- Imutável, o que significa que não é possível substituir, apagar ou alterar o registro durante o período de retenção obrigatório.

No Exchange Online, quando uma [política de retenção](retention-policies.md) é aplicada à caixa de correio do usuário, todo o conteúdo do usuário será retido com base nos critérios da política. Na verdade, se um usuário tentar excluir ou modificar um email, o programa manterá uma cópia do email em um local seguro e oculto na caixa de correio do usuário, antes que a alteração seja feita. As políticas de retenção podem garantir que uma organização retenha as comunicações eletrônicas, embora essas políticas sejam passíveis de modificação.

Ao aplicar o Bloqueio de Preservação em uma política de retenção, a empresa garante que a política não seja modificada. De fato, após aplicar o Bloqueio de Preservação a uma política de retenção, as seguintes ações serão restritas:

- O período de retenção da política pode apenas ser aumentado, mas não reduzido.
- É possível adicionar usuários à política, mas não é possível removê-los.
- A política de retenção não pode ser excluída por um administrador.

O Bloqueio de Preservação pode ajudar na conformidade com os requisitos regulamentares da norma 17a-4 da SEC.

## <a name="how-to-set-up-preservation-lock"></a>Como configurar o Bloqueio de Preservação

É possível bloquear uma política de retenção usando o PowerShell. Para saber mais, confira [Como bloquear uma política de retenção](retention-policies.md#locking-a-retention-policy).

## <a name="known-limitations"></a>Limitações conhecidas

No momento, há algumas limitações no Exchange Online:

- A auditoria em nível de item não está disponível para caixas de correio de Grupo do Office 365.
- As comunicações encadeadas não estão disponíveis para mensagens de canal e chat do Teams.
- As curtidas não são retidas para mensagens de canal e chat do Teams.
