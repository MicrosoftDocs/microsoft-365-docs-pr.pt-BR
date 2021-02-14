---
title: BitLocker para criptografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Saiba como o Office 365 usa a criptografia BitLocker, reduzindo o potencial de roubo de dados devido a computadores e discos perdidos ou roubados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033619"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) para Criptografia

Os servidores da Microsoft usam o BitLocker para criptografar as unidades de disco que contêm dados do cliente em repouso no nível do volume. A criptografia BitLocker é um recurso de proteção de dados integrado ao Windows. O BitLocker é uma das tecnologias usadas para proteger contra ameaças no caso de haver ameaças em outros processos ou controles (por exemplo, controle de acesso ou reciclagem de hardware) que podem levar alguém a obter acesso físico a discos que contêm dados do cliente. Nesse caso, o BitLocker elimina o potencial de roubo ou exposição de dados devido a computadores e discos perdidos, roubados ou desativados inadequadamente.

O BitLocker é implantado com criptografia AES (Advanced Encryption Standard) de 256 bits em discos que contêm dados do cliente no Exchange Online, no SharePoint Online e no Skype for Business. Os setores de disco são criptografados com uma Chave de Criptografia de Volume Completo (FVEK), que é criptografada com a Chave Mestra de Volume (VMK), que, por sua vez, está vinculada ao Trusted Platform Module (TPM) no servidor. A VMK protege diretamente o FVEK e, portanto, proteger a VMK se torna fundamental. A figura a seguir ilustra um exemplo da cadeia de proteção de chave do BitLocker para um determinado servidor (neste caso, usando um servidor Exchange Online).

A tabela a seguir descreve a cadeia de proteção de chave do BitLocker para um determinado servidor (neste caso, um servidor do Exchange Online).

| PROTETOR DE CHAVE | GRANULARITY | COMO É GERADO? | ONDE ELE ESTÁ ARMAZENADO? | PROTEÇÃO |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chave Externa AES de 256 bits | Por Servidor | BitLocker APIs | TPM ou Segredo Seguro | Lockbox /Access Control |
|  |  |  | Registro do servidor de caixa de correio | TPM criptografado |
| Senha Numérica de 48 dígitos | Por disco | BitLocker APIs | Active Directory | Lockbox /Access Control |
| Certificado X.509 como Agente de Recuperação de Dados (DRA) também chamado protetor de chave pública | Ambiente (por exemplo, multitenant do Exchange Online) | Microsoft CA | Sistema de com build | Nenhum usuário tem a senha completa para a chave privada. A senha está sob proteção física. |


O gerenciamento de chaves do BitLocker envolve o gerenciamento de chaves de recuperação que são usadas para desbloquear/recuperar discos criptografados em um datacenter da Microsoft. O Microsoft 365 armazena as chaves mestras em um compartilhamento seguro, acessível somente por pessoas que foram teladas e aprovadas. As credenciais para as chaves são armazenadas em um repositório seguro para dados de controle de acesso (o que chamamos de "repositório secreto"), que exige um alto nível de elevação e aprovações de gerenciamento para acessar usando uma ferramenta de elevação de acesso just-in-time.

O BitLocker oferece suporte a chaves que se enquadram em duas categorias de gerenciamento:

- Chaves gerenciadas pelo BitLocker, que geralmente têm curta duração e estão vinculadas ao tempo de vida de uma instância do sistema operacional instalada em um servidor ou em um determinado disco. Essas chaves são excluídas e redefinidas durante a reinstalação do servidor ou a formatação do disco.

- Chaves de recuperação do BitLocker, que são gerenciadas fora do BitLocker, mas usadas para descriptografia de disco. O BitLocker usa chaves de recuperação para o cenário em que um sistema operacional é reinstalado e discos de dados criptografados já existem. As chaves de recuperação também são usadas pelas sondas de monitoramento de Disponibilidade Gerenciada no Exchange Online, onde um respondente pode precisar desbloquear um disco.

Os volumes protegidos pelo BitLocker são criptografados com uma chave de criptografia de volume completa, que, por sua vez, é criptografada com uma chave mestra de volume. O BitLocker usa algoritmos compatíveis com FIPS para garantir que as chaves de criptografia nunca sejam armazenadas ou enviadas pela transmissão sem criptografia. A implementação do Microsoft 365 de proteção de dados em repouso do cliente não desvia da implementação padrão do BitLocker.
