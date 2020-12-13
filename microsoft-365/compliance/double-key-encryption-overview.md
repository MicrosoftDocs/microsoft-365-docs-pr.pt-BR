---
title: Visão geral e perguntas frequentes sobre criptografia de chave dupla
description: Perguntas frequentes sobre a criptografia de chave dupla para o Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663056"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Perguntas frequentes sobre a criptografia de duas teclas

Tem uma dúvida sobre como funciona a criptografia de chave dupla? Verifique se há uma resposta aqui.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>O que é criptografia de duas teclas para o Microsoft 365 (DKE)?

A chave dupla de criptografia para o Microsoft 365 permite aos clientes proteger seus dados altamente confidenciais para atender a requisitos especializados. Ele ajuda os clientes a manter controle total de suas chaves de criptografia. Ele usa duas chaves para proteger os dados; uma chave no controle e uma segunda chave armazenada com segurança no Microsoft Azure. A exibição de dados protegidos por chave dupla de criptografia exige acesso às duas chaves. Como a Microsoft pode acessar apenas uma dessas chaves, os dados protegidos permanecem inacessíveis à Microsoft, garantindo que você tenha total controle sobre a privacidade e a segurança dos dados.  

Você pode hospedar o serviço de criptografia de chave dupla usado para solicitar sua chave, em um local de sua escolha (servidor de gerenciamento de chaves local ou na nuvem). Você mantém o serviço como faria com qualquer outro aplicativo. A criptografia de chave dupla permite controlar o acesso ao serviço de criptografia de chave dupla. Você pode armazenar seus dados altamente confidenciais no local ou movê-los para a nuvem. Você pode ter certeza de como evitar o acesso de terceiros, pois mantém total controle da sua chave. A criptografia de chave dupla permite armazenar dados e chaves no mesmo local.

O DKE ajuda você a atender aos requisitos normativos de várias regulamentações e padrões como o RGPD (regulamentação de proteção de dados), o Health Insurance Portability and Accountability Act (HIPAA), The Gramm-Leach-Bliley Act (GLBA), lei de localização de dados da Rússia-legislação federal 242-FZ, Federal Privacy Act 1988 e a lei de privacidade da Nova Zelândia 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Posso usar a criptografia de duas teclas com o rótulo de confidencialidade interno do Microsoft Office?

Você precisará usar o cliente de rotulação unificada de proteção de informações do Azure para proteger documentos com criptografia de chave dupla. No momento, não é possível usar o rótulo de confidencialidade interno do Microsoft Office.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>O que os aplicativos da Microsoft 365 podem usar com o DKE?

Você pode usar os rótulos do DKE para proteger documentos usando as versões da área de trabalho do Word, Excel e PowerPoint no Windows. Certifique-se de que você está usando *. 12711 ou posterior (versões de área de trabalho do Word, PowerPoint e Excel) no Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Como a criptografia de duas teclas é diferente da solução existente de posse de sua própria chave (HYOK)?

A criptografia de chave dupla criptografa seus dados com duas chaves. Sua chave de criptografia está no seu controle e a segunda é armazenada no Microsoft Azure, permitindo que você mova seus dados criptografados para a nuvem. O HYOK protege o conteúdo com apenas uma chave e a chave está sempre no local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Os documentos criptografados com chave dupla podem ser compartilhados externamente?

Você pode compartilhar documentos criptografados de chave dupla com usuários em um locatário separado, desde que estes usuários:

- Ter a permissão necessária para acessar sua chave no serviço de criptografia de chave dupla.

- Ter a permissão necessária para acessar sua chave no Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>O que acontece com os documentos que são protegidos com o HYOK?

A implantação da chave de criptografia dupla não afetará a configuração do HYOK existente. No entanto, recomendamos que você comece a usar a criptografia de chave dupla paralelamente com o HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Posso executar a criptografia de duas teclas em meu ambiente que não seja do Microsoft Air-gapped?

O DKE não dá suporte a esses ambientes porque o serviço requer acesso ao Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Onde posso armazenar documentos criptografados com chave dupla?

Você pode armazenar documentos criptografados de chave dupla no local ou na nuvem. Na nuvem, você pode mover conteúdo criptografado para o SharePoint Online e o OneDrive for Business. Como a Microsoft não tem acesso à sua chave privada, os dados criptografados permanecem opacos para a Microsoft. Isso também significa que você não pode exibir os documentos criptografados online no Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>Quais regiões e idiomas tem a criptografia de chave dupla disponível em? A criptografia de chave dupla está disponível em todo o mundo?

Os rótulos do DKE são localizados nos mesmos idiomas que outros rótulos de confidencialidade na proteção de informações da Microsoft. A chave dupla de criptografia está disponível em todo o mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Posso converter um rótulo não DKE em um rótulo DKE?

Não. Não é possível adicionar DKE a um rótulo depois de criá-lo. Em vez disso, você deve escolher **usar criptografia de chave dupla** e fornecer a URL do serviço de criptografia de chave dupla ao criar o rótulo.

## <a name="how-do-i-roll-my-dke-keys"></a>Como faço para rolar minhas chaves do DKE?

Para obter instruções sobre a reversão (também chamada de rotação ou rechaveamento) da chave armazenada no Azure, consulte [operações da chave do locatário de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).

Confira [definições de locatário e chave](double-key-encryption.md#tenant-and-key-settings) para obter informações sobre como criar uma nova chave para o serviço DKE.

Ao criar uma chave, você configura um nome e um GUID. Em seguida, se você girar uma tecla, você mantém o registro antigo com o nome e o GUID, mas adiciona um novo registro com o mesmo nome, mas GUIDs diferentes. A nova chave é definida como ativa para que a API da chave pública comece a retorná-la para nova criptografia. Ambas as chaves estão disponíveis para descriptografia, de forma que o novo conteúdo e o conteúdo antigo possam ser descriptografados.
