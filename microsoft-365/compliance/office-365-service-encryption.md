---
title: Criptografia de Serviço
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: Entenda a resiliência de dados no Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058544"
---
# <a name="service-encryption"></a>Criptografia de Serviço

Além de usar criptografia em nível de volume, o Exchange Online, o Microsoft Teams, o SharePoint Online e o OneDrive for Business também usam a Criptografia de Serviço para criptografar dados do cliente. A Criptografia de Serviço permite duas opções de gerenciamento de chaves:

## <a name="microsoft-managed-keys"></a>Chaves gerenciadas pela Microsoft
A Microsoft gerencia todas as chaves criptográficas, incluindo as chaves raiz para criptografia de serviço. Essa opção está habilitada por padrão para Exchange Online, SharePoint Online, OneDrive for Business. As chaves gerenciadas pela Microsoft fornecem criptografia de serviço padrão, a menos que você decida fazer a integração usando a Chave do Cliente. Se, posteriormente, você decidir parar de usar a Chave do Cliente sem seguir o caminho de limpeza dos dados, os dados permanecerão criptografados usando as chaves gerenciadas pela Microsoft. Seus dados são sempre criptografados nesse nível padrão no mínimo. 

## <a name="customer-key"></a>Chave de Cliente
Você fornece chaves raiz usadas com criptografia de serviço e gerencia essas chaves usando o Azure Key Vault. A Microsoft gerencia todas as outras chaves. Essa opção é chamada de Chave do Cliente e está disponível atualmente para Exchange Online, SharePoint Online e OneDrive for Business. (Anteriormente conhecido como Criptografia Avançada com BYOK. Confira [Aumentar a transparência e o controle para clientes do Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.)

A criptografia de serviço oferece vários benefícios:

- Fornece uma camada adicional de proteção sobre o BitLocker.

- Fornece separação de administradores do sistema operacional Windows do acesso aos dados de aplicativo armazenados ou processados pelo sistema operacional.

- Inclui uma opção de Chave do Cliente que permite que os serviços de vários locatários forneçam gerenciamento de chaves por locatário.

- Aprimora a capacidade do Microsoft 365 de atender às demandas dos clientes que têm requisitos de conformidade específicos em relação à criptografia.

Usando a Chave do Cliente, você pode gerar suas próprias chaves criptográficas usando um HSM (Módulo de Serviço de Hardware) local ou AZure Key Vault (AKV). Independentemente de como você gera a chave, use a AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365. Depois que suas chaves são armazenadas no AKV, elas podem ser usadas como raiz de um dos chaves que criptografam seus dados ou arquivos de caixa de correio.

Outro benefício da Chave do Cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados. Se você quiser remover dados do Office 365, por exemplo, se quiser encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, poderá fazer isso e usar a Chave do Cliente como um controle técnico. A remoção de dados garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados. A Chave do Cliente também é complementar ao Sistema de Proteção de Dados do Cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.

Para saber como configurar a Chave de Cliente do Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluindo Sites de Equipe e OneDrive for Business, confira estes artigos:

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Compreender a chave de disponibilidade](customer-key-availability-key-understand.md)
