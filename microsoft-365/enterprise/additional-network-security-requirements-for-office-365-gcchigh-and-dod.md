---
title: Requisitos adicionais de segurança de rede para Office 365 GCC Alta e DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumo: Office 365 GCC Alta e DoD têm requisitos adicionais de segurança de rede'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926554"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos de segurança de rede adicionais para Office 365 GCC High e DOD

*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

Office 365 GCC High e DOD são ambientes de nuvem seguros para atender às necessidades do Governo dos Estados Unidos e seus fornecedores e prestadores de serviços.  Esses ambientes de nuvem têm restrições de rede adicionais em quais pontos de extremidade externos os serviços têm permissão para acessar.

GCC Clientes altos e do DOD que planejam usar identidades federadas ou coexistência híbrida podem exigir que a Microsoft permita acesso de entrada e/ou saída às implantações locais existentes.  Exemplos dessas atividades incluem:

* Uso de identidades federadas (com Serviços de Federação do Active Directory ou STS com suporte semelhante)
* Coexistência híbrida com uma implantação local Exchange Server ou Skype for Business local
* Migração do conteúdo do usuário existente de um sistema local

Para permitir que o serviço se comunique com  seus pontos de extremidade locais, você deve enviar um email para Office 365 engenharia para alterações na rede.

> [!WARNING]
> Todas as solicitações **têm** um SLA de três semanas e não podem ser aceleradas devido aos controles de segurança e conformidade necessários e pipelines de implantação.  Isso inclui solicitações de rede de integração iniciais, bem como quaisquer alterações depois que você tiver migrado para o serviço.  Certifique-se de que suas equipes de rede estão cientes dessa linha do tempo e inclua-a em seus ciclos de planejamento.

Envie um email para Office 365 Government Allow-List [solicitações](mailto:o365gwlt@microsoft.com) com as seguintes informações:

* **Para**: [Office 365 Government Allow-List solicitações](mailto:o365gwlt@microsoft.com)
* **From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant
* **Assunto de** email : Office 365 GCC Alta Solicitação de Rede - contoso.onmicrosoft.us (substitua pelo nome do locatário)

O corpo da mensagem deve incluir os seguintes dados:

* Seu Microsoft Online Services de locatário (por exemplo, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Uma lista de distribuição de email com a que a Microsoft se comunicará para comunicações em trânsito relacionadas a alterações na rede e/ou acompanhamento de sub-redes inválidas
* Indicar se você planeja usar Microsoft Teams coexistência híbrida com suas implantações locais
* Sistema de identidade federado acessível externamente URL (por exemplo, sts.contoso.com) e intervalo de endereços IP na notação CIDR (por exemplo, . 10.1.1.0/28)
* URL da lista de certificados PKI local e intervalo de endereços IP na notação CIDR
* Url acessível externamente e intervalo de endereços IP para Exchange Server implantação local na notação CIDR
* Url acessível externamente e intervalo de endereços IP para Skype for Business implantação local na notação CIDR

Por motivos de segurança e conformidade, tenha em mente as seguintes restrições em sua solicitação:

* Há uma limitação de quatro sub-redes por locatário
* As sub-redes devem estar na Notação CIDR (por exemplo, 10.1.1.0/28)
* Os intervalos de sub-rede não podem ser maiores do que /24
* Não **podemos acomodar** solicitações para permitir o acesso a serviços de nuvem comercial (serviços comerciais Office 365, Google G-Suite, Amazon Web Services, etc.)

Depois que sua solicitação for recebida e aprovada pela Microsoft, há um SLA de três semanas para implementação e não pode ser expedido.  Você receberá um reconhecimento inicial quando recebermos sua solicitação e um reconhecimento final depois que ela for concluída.
