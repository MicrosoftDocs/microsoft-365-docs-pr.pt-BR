---
title: Requisitos de segurança de rede adicionais para o Office 365 GCC High e DoD
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
description: 'Resumo: Office 365 GCC High e DoD têm requisitos de segurança de rede adicionais'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687209"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos de segurança de rede adicionais para Office 365 GCC High e DOD

*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

O Office 365 GCC High e o DOD são ambientes de nuvem seguros para atender às necessidades do Governo dos Estados Unidos e de seus fornecedores e prestadores de serviços.  Esses ambientes de nuvem têm restrições de rede adicionais sobre quais pontos de extremidade externos os serviços têm permissão para acessar.

Os clientes GCC High e DOD que planejam usar identidades federadas ou a co-existência híbrida podem exigir que a Microsoft permita o acesso de entrada e/ou saída às suas implantações locais existentes.  Exemplos dessas atividades incluem:

* Uso de identidades federadas (com Serviços de Federação do Active Directory ou STS com suporte semelhante)
* Coexistência híbrida com uma implantação local do Exchange Server ou do Skype for Business
* Migração de conteúdo de usuário existente de um sistema local

Para permitir que o serviço se comunique com  seus pontos de extremidade locais, você deve enviar um email para a engenharia do Office 365 para alterações na rede.

> [!WARNING]
> Todas as solicitações têm **um** SLA de três semanas e não podem ser expedidas devido aos controles de segurança e conformidade necessários e pipelines de implantação.  Isso inclui solicitações de rede de integração iniciais, bem como quaisquer alterações depois que você migrou para o serviço.  Certifique-se de que suas equipes de rede estão cientes dessa linha do tempo e inclua-a em seus ciclos de planejamento.

Envie um email para a lista [branca do Office 365 Government Network](mailto:o365gwlt@microsoft.com) com as seguintes informações:

* **Para**: Lista [branca de rede do Office 365 Government](mailto:o365gwlt@microsoft.com)
* **De:** um administrador de locatários - o email de envio **deve** corresponder a um contato do Administrador Global em seu locatário
* **Assunto do email**: Solicitação de Alta Rede do Office 365 GCC - contoso.onmicrosoft.us (substitua pelo nome do locatário)

O corpo da mensagem deve incluir os seguintes dados:

* Seu nome de locatário do Microsoft Online Services (ou seja, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Uma lista de distribuição de email com a que a Microsoft se comunicará para comunicações em trânsito relacionadas a alterações na rede e/ou acompanhamento de sub-redes inválidas
* Indicar se você planeja usar a cooperação híbrida do Microsoft Teams com suas implantações locais
* URL externamente acessível do sistema de identidade federado (por exemplo, sts.contoso.com) e intervalo de endereços IP na notação CIDR (por exemplo, 10.1.1.0/28)
* URL da Lista de Certificados Revogados de PKI local e intervalo de endereços IP na notação CIDR
* URL acessível externamente e intervalo de endereços IP para implantação local do Exchange Server em notação CIDR
* URL acessível externamente e intervalo de endereços IP para implantação local do Skype for Business em notação CIDR

Por motivos de segurança e conformidade, tenha em mente as seguintes restrições em sua solicitação:

* Há uma limitação de quatro sub-redes por locatário
* As sub-redes devem estar em Notação CIDR (por exemplo, 10.1.1.0/28)
* Os intervalos de sub-rede não podem ser maiores que /24
* Não **é possível** acomodar solicitações para permitir o acesso a serviços de nuvem comerciais (Office 365 comercial, Google G-Suite, Amazon Web Services, etc.)

Depois que sua solicitação for recebida e aprovada pela Microsoft, haverá um SLA de três semanas para implementação e não poderá ser expedido.  Você receberá uma confirmação inicial quando recebermos sua solicitação e uma confirmação final depois que ela for concluída.
