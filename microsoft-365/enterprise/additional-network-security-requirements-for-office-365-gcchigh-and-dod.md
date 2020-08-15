---
title: Requisitos adicionais de segurança de rede para o Office 365 GCC High e DoD
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
description: 'Resumo: o Office 365 GCC High e o DoD têm requisitos de segurança de rede adicionais'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687209"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos adicionais de segurança de rede para o Office 365 GCC High e DOD

*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

O Office 365 GCC High e o DOD são ambientes de nuvem seguros para atender às necessidades do governo dos Estados Unidos e de seus fornecedores e prestadores de atendimento.  Esses ambientes de nuvem têm restrições de rede adicionais nas quais os pontos de extremidade externos podem acessar os serviços.

Os clientes do GCC High e do DOD que planejam usar identidades federadas ou a coexistência híbrida podem exigir que a Microsoft permita o acesso de entrada e saída às suas implantações locais existentes.  Exemplos dessas atividades incluem:

* Uso de identidades federadas (com os serviços de Federação do Active Directory ou STS com suporte semelhante)
* Coexistência híbrida com uma implantação local do Exchange Server ou do Skype for Business
* Migração de conteúdo de usuário existente de um sistema local

Para permitir que o serviço se comunique com seus pontos de extremidade locais, você **deve** enviar um email para o Office 365 Engineering for Network Changes.

> [!WARNING]
> Todas as solicitações têm um SLA de **três semanas** e não podem ser expedidas devido aos controles de conformidade e segurança necessários e a pipelines de implantação.  Isso inclui solicitações de rede de integração inicial, bem como qualquer alteração após você ter migrado para o serviço.  Certifique-se de que suas equipes de rede estejam cientes dessa linha do tempo e inclua-as nos ciclos de planejamento.

Envie um email para a [lista branca de rede governamental do Office 365](mailto:o365gwlt@microsoft.com) com as seguintes informações:

* **Para**: [lista branca de rede governamental do Office 365](mailto:o365gwlt@microsoft.com)
* **De**: um administrador de locatários-o email de envio **deve** corresponder a um contato de administrador global em seu locatário
* **Assunto do email**: solicitação de rede alta do Office 365 GCC-contoso.onmicrosoft.us (substitua isso pelo nome do seu locatário)

O corpo da mensagem deve incluir os seguintes dados:

* Seu nome de locatário do Microsoft Online Services (ou seja, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Uma lista de distribuição de email com a qual a Microsoft se comunicará para comunicações em andamento relacionadas a alterações de rede e/ou acompanhamento de sub-redes inválidas
* Indicar se você planeja usar a coexistência híbrida do Microsoft Teams com suas implantações locais
* URL acessível externamente do sistema de identidade federada (por exemplo, sts.contoso.com) e intervalo de endereços IP em notação CIDR (por exemplo, 10.1.1.0/28)
* URL da lista de certificados revogados de PKI local e intervalo de endereços IP na notação CIDR
* URL e intervalo de endereços IP acessíveis externamente para a implantação local do Exchange Server na notação CIDR
* URL e intervalo de endereços IP acessíveis externamente para a implantação local do Skype for Business em notação CIDR

Por motivos de segurança e conformidade, tenha em mente as seguintes restrições em sua solicitação:

* Há quatro limitações de sub-rede por locatário
* As sub-redes devem estar na notação CIDR (por exemplo, 10.1.1.0/28)
* Os intervalos de sub-rede não podem ser maiores que/24
* **Não é possível** acomodar solicitações para permitir o acesso aos serviços de nuvem comercial (comercial 365, Google G-Suite, serviços da Amazon, etc.)

Após a solicitação ser recebida e aprovada pela Microsoft, há um SLA de três semanas para implementação e não pode ser acelerado.  Você receberá uma confirmação inicial quando recebermos sua solicitação e uma confirmação final após a conclusão.
