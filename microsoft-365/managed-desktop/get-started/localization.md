---
title: Localize a experiência do usuário
description: Como localizar dispositivos para usuários
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445919"
---
# <a name="localize-the-user-experience"></a>Localize a experiência do usuário

Os usuários de dispositivos da Área de Trabalho Gerenciada da Microsoft podem selecionar o idioma de sua escolha durante o processo de instalação (a "experiência fora da caixa") ou posteriormente.

## <a name="during-setup-the-out-of-box-experience"></a>Durante a instalação (a "experiência fora da caixa")

Durante o processo de conclusão da instalação, os usuários podem selecionar o idioma de sua escolha. Essa seleção afeta esses atributos:

- Recursos de idioma do Windows 10:
    - Idioma de exibição
    - Idioma do teclado
    - Recursos relacionados ao idioma sob demanda

- Recursos de idioma do Microsoft 365 Apps for Enterprise:
    - Idioma de exibição
    - Revisa e ferramentas de autoria

> [!NOTE]
> Os usuários só podem obter recursos relacionados ao idioma sob demanda selecionando o idioma durante o processo de instalação.

## <a name="after-completing-setup"></a>Depois de concluir a instalação

Os usuários podem selecionar o idioma de sua escolha para o Windows 10 e o Microsoft 365 Apps para Empresas a qualquer momento após a conclusão do processo de instalação. Especificamente:

- Recursos de idioma do Windows 10:
    - Idioma de exibição
    - Idioma do teclado

- Recursos de idioma do Microsoft 365 Apps for Enterprise:
    - Idioma de exibição
    - Revisa e ferramentas de autoria

Para disponibilizar os idiomas com suporte para o Microsoft 365 Apps for Enterprise para os usuários, adicione os usuários ao grupo Moderno **Workplace-Office-Language_Packs.** [](#supported-languages) Os idiomas estarão disponíveis no Portal da Empresa do Intune.


## <a name="supported-languages"></a>Idiomas compatíveis

Para novos dispositivos, o fabricante deve fornecer imagens de dispositivo que incluam os idiomas necessários. Se a imagem do fabricante incluir idiomas diferentes daqueles fornecidos na lista de idiomas com suporte, ele ainda terá suporte do serviço.

Se você estiver reutilando dispositivos existentes, talvez seja necessário trabalhar com seu representante de conta da Microsoft para obter imagens apropriadas. Para obter mais informações, consulte [Imagens do dispositivo](../service-description/device-images.md).

A [imagem universal](../service-description/device-images.md#universal-image) fornecida pela Área de Trabalho Gerenciada da Microsoft inclui esses idiomas e para o Windows 10:

- Inglês (US, GB, AU, CA, IN)
- Espanhol (Espanha, México)
- Japonês
- Francês (França, Canadá)
- Alemão
- Português (Brasil)
- Italiano
- Chinese Simplified
- Holandês  
- Sueco
- Dinamarquês  
- Finlandês 
- Russo 
- Norueguês (Bokmål)
- Coreano
- Chinese Traditional
- Polonês
- Turco
- Árabe
- Hebraico
- Português (Portugal)
- Tcheco
- Húngaro
- Tailandês
- Indonésio
- Grego
- Eslovaco
- Vietnamita
- Esloveno
- Croata
- Romeno
- Lituano
- Búlgaro
- Sérvio (alfabeto latino)
- Letão
- Ucraniano
- Estoniano

O Microsoft 365 Apps for Enterprise pode dar suporte a uma lista ligeiramente diferente.

Se os usuários precisarem de um idioma diferente dos listados aqui, arquivar uma solicitação de [suporte](../working-with-managed-desktop/admin-support.md) usando o [portal administrador](access-admin-portal.md).

## <a name="languages-for-support-and-operations"></a>Idiomas para suporte e operações

### <a name="user-support"></a>Suporte ao usuário
A Área de Trabalho Gerenciada da Microsoft oferece suporte somente em inglês. Se os usuários escolherem outro idioma no aplicativo Obter Ajuda, eles receberão suporte dos canais de suporte gerais da Microsoft, em vez de suportar diretamente da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Obter ajuda para usuários](../working-with-managed-desktop/end-user-support.md).

Se os usuários precisarem de suporte em outros idiomas, você precisará fornecer isso por meio de fontes de suporte que não são da Microsoft ou de sua própria organização.

### <a name="admin-support-and-operations"></a>Suporte e operações do administrador
A Área de Trabalho Gerenciada da Microsoft fornece suporte ao administrador somente em inglês. Isso inclui o portal de administração e todas as comunicações com as Operações de Área de Trabalho Gerenciadas da Microsoft. Você deve presumir que todas as interações e interfaces relacionadas ao administrador estarão em inglês, a menos que especificado de outra forma.


