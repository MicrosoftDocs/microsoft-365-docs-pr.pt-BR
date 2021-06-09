---
title: BitLocker para Criptografia
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
description: Saiba como o Office 365 usa BitLocker criptografia, reduzindo o potencial de roubo de dados devido a computadores e discos perdidos ou roubados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033619"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) para Criptografia

Os servidores Microsoft usam BitLocker para criptografar as unidades de disco que contêm dados do cliente em repouso no nível de volume. BitLocker criptografia é um recurso de proteção de dados que é integrado a Windows. BitLocker é uma das tecnologias usadas para proteger contra ameaças caso haja falhas em outros processos ou controles (por exemplo, controle de acesso ou reciclagem de hardware) que podem levar alguém a obter acesso físico a discos que contenham dados do cliente. Nesse caso, o BitLocker elimina o potencial de roubo ou exposição de dados devido a computadores e discos perdidos, roubados ou desmantelados inadequadamente.

o BitLocker é implantado com criptografia avançada de 256 bits (AES) em discos que contêm dados do cliente no Exchange Online, SharePoint Online e Skype for Business. Os setores de disco são criptografados com uma Chave de Criptografia de Volume Total (FVEK), que é criptografada com a VMK (Chave Mestre de Volume), que, por sua vez, está vinculada ao Módulo de Plataforma Confiável (TPM) no servidor. O VMK protege diretamente o FVEK e, portanto, proteger o VMK torna-se crítico. A figura a seguir ilustra um exemplo da cadeia de proteção BitLocker chave para um determinado servidor (nesse caso, usando um Exchange Online servidor).

A tabela a seguir descreve a cadeia BitLocker chave de proteção de um determinado servidor (nesse caso, um servidor Exchange Online servidor).

| PROTETOR DE TECLAS | GRANULARITY | COMO É GERADO? | ONDE ELE É ARMAZENADO? | PROTECTION |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chave Externa do AES de 256 bits | Por Servidor | BitLocker APIs | TPM ou Segredo Cofre | Lockbox / Access Control |
|  |  |  | Registro do Servidor de Caixa de Correio | TPM criptografado |
| Senha Numérica de 48 dígitos | Por Disco | BitLocker APIs | Active Directory | Lockbox / Access Control |
| Certificado X.509 como Agente de Recuperação de Dados (DRA) também chamado de Protetor de Chave Pública | Ambiente (por exemplo, Exchange Online multitenente) | Microsoft CA | Sistema de com build | Nenhum usuário tem a senha completa da chave privada. A senha está sob proteção física. |


BitLocker gerenciamento de chaves envolve o gerenciamento de chaves de recuperação usadas para desbloquear/recuperar discos criptografados em um datacenter da Microsoft. Microsoft 365 armazena as chaves mestras em um compartilhamento seguro, acessível apenas por indivíduos que foram exibidos e aprovados. As credenciais das chaves são armazenadas em um repositório seguro para dados de controle de acesso (o que chamamos de "repositório secreto"), que exige um alto nível de elevação e aprovações de gerenciamento para acessar usando uma ferramenta de elevação de acesso just-in-time.

BitLocker suporta chaves que se enquadram em duas categorias de gerenciamento:

- BitLocker chaves gerenciadas, geralmente de curta duração e vinculadas ao tempo de vida de uma instância do sistema operacional instalada em um servidor ou a um determinado disco. Essas chaves são excluídas e redefinidas durante a reinstalação do servidor ou a formatação de disco.

- BitLocker de recuperação, que são gerenciadas fora do BitLocker, mas usadas para descriptografia de disco. BitLocker usa chaves de recuperação para o cenário no qual um sistema operacional é reinstalado e discos de dados criptografados já existem. As chaves de recuperação também são usadas por sondas de monitoramento de Disponibilidade Gerenciada Exchange Online onde um respondente pode precisar desbloquear um disco.

BitLocker são criptografados com uma chave de criptografia de volume total, que, por sua vez, é criptografada com uma chave mestra de volume. BitLocker usa algoritmos compatíveis com FIPS para garantir que as chaves de criptografia nunca sejam armazenadas ou enviadas pelo fio de forma clara. A Microsoft 365 implementação do data-at-rest-protection do cliente não se desvia da implementação BitLocker padrão.
