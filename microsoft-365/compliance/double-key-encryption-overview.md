---
title: Visão geral e perguntas frequentes sobre Criptografia de Chave Dupla
description: Perguntas frequentes sobre a Criptografia de Chave Dupla do Microsoft 365.
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
# <a name="double-key-encryption-frequently-asked-questions"></a>Perguntas frequentes sobre Criptografia de Chave Dupla

Tem uma pergunta sobre como funciona a Criptografia de Chave Dupla? Verifique se há uma resposta aqui.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>O que é Criptografia de Chave Dupla do Microsoft 365 (DKE)?

A Criptografia de Chave Dupla do Microsoft 365 permite que os clientes protejam seus dados altamente confidenciais para atender a requisitos especializados. Ele ajuda os clientes a manter o controle total de suas chaves de criptografia. Ele usa duas chaves para proteger dados; uma chave em seu controle e uma segunda chave armazenada com segurança no Microsoft Azure. A exibição de dados protegidos com Criptografia de Chave Dupla requer acesso a ambas as chaves. Como a Microsoft pode acessar apenas uma dessas chaves, os dados protegidos permanecem inacessíveis para a Microsoft, garantindo que você tenha controle total sobre sua privacidade e segurança de dados.  

Você pode hospedar o serviço de Criptografia de Chave Dupla usado para solicitar sua chave, em um local de sua escolha (servidor de gerenciamento de chaves local ou na nuvem). Você mantém o serviço como faria com qualquer outro aplicativo. A Criptografia de Chave Dupla permite controlar o acesso ao serviço de Criptografia de Chave Dupla. Você pode armazenar seus dados altamente confidenciais no local ou movê-los para a nuvem. Você pode ter confiança em impedir o acesso de terceiros porque mantém o controle total da sua chave. A Criptografia de Chave Dupla permite que você armazene seus dados e chaves no mesmo local.

O DKE ajuda você a atender aos requisitos regulatórios em vários regulamentos e padrões, como o RGPD (Regulamento Geral sobre a Proteção de Dados), a Lei de Portabilidade e Responsabilidade do Seguro de Saúde (HIPAA), a Lei Gramm-Leach-Bliley (GLBA), a lei de localização de dados da Rússia – Lei Federal No. 242-FZ, Lei de Privacidade Federal da Austrália 1988 e Lei de Privacidade da Nova Zelândia 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Posso usar a Criptografia de Chave Dupla com a rotulagem de sensibilidade integrado do Microsoft Office?

Você precisará usar o cliente de rotulagem unificada da Proteção de Informações do Azure para proteger documentos com Criptografia de Chave Dupla. Atualmente, você não pode usar a rotulagem de sensibilidade integrado do Microsoft Office.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Quais aplicativos do Microsoft 365 posso usar com o DKE?

Você pode usar rótulos DKE para proteger documentos usando as versões da área de trabalho do Word, Excel e PowerPoint no Windows. Verifique se você está usando *.12711 ou posterior (versões da área de trabalho do Word, PowerPoint e Excel) no Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Qual é a diferença entre a Criptografia de Chave Dupla e a solução de espera existente (HYOK) ?

A Criptografia de Chave Dupla criptografa seus dados com duas chaves. Sua chave de criptografia está no seu controle e a segunda chave é armazenada no Microsoft Azure, permitindo que você mova seus dados criptografados para a nuvem. HYOK protege o conteúdo com apenas uma chave e a chave está sempre no local.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Os documentos criptografados com chave dupla podem ser compartilhados externamente?

Você pode compartilhar documentos criptografados com chave dupla com usuários em um locatário separado, desde que esses usuários:

- Ter a permissão necessária para acessar sua chave no serviço de Criptografia de Chave Dupla.

- Ter a permissão necessária para acessar sua chave no Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>O que acontece com documentos protegidos com HYOK?

A implantação da Criptografia de Chave Dupla não afetará sua configuração HYOK existente. No entanto, recomendamos que você comece a usar a Criptografia de Chave Dupla em paralelo com HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Posso executar a Criptografia de Chave Dupla em meu ambiente não mapeado para o ar da Microsoft?

O DKE não dá suporte a esses ambientes porque o serviço requer acesso ao Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Onde posso armazenar documentos com chave dupla criptografada?

Você pode armazenar documentos criptografados com chave dupla no local ou na nuvem. Na nuvem, você pode mover conteúdo criptografado para o SharePoint Online e o OneDrive for Business. Como a Microsoft não tem acesso à sua chave privada, os dados criptografados permanecem opacos para a Microsoft. Isso também significa que você não pode exibir os documentos criptografados online no Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>Em quais regiões e idiomas a Criptografia de Chave Dupla está disponível? A Criptografia de Chave Dupla está disponível em todo o mundo?

Os rótulos DKE são localizados nos mesmos idiomas que outros rótulos de sensibilidade na Proteção de Informações da Microsoft. A Criptografia de Chave Dupla está disponível em todo o mundo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Posso converter um rótulo não-DKE em um rótulo DKE?

Não. Você não pode adicionar DKE a um rótulo depois de criar. Em vez disso, você deve escolher Usar Criptografia **de Chave** Dupla e fornecer a URL do seu serviço de Criptografia de Chave Dupla ao criar o rótulo.

## <a name="how-do-i-roll-my-dke-keys"></a>Como rolar minhas teclas DKE?

Para obter instruções sobre como rolar (também chamado de girar ou teclas) a chave que você armazena no Azure, confira Operações para sua chave de locatário da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)

Consulte [Configurações de locatário e chave](double-key-encryption.md#tenant-and-key-settings) para obter informações sobre como criar uma nova chave para o serviço DKE.

Ao criar uma chave, você configura um nome e um GUID. Em seguida, se você girar uma tecla, manterá o registro antigo com o nome e o GUID, mas adicionará um novo registro com o mesmo nome, mas COM GUID diferente. A nova chave é definida como ativa para que a API de chave pública comece a revolvê-la para nova criptografia. Ambas as chaves estão disponíveis para descriptografia para que o novo conteúdo e o conteúdo antigo possam ser descriptografados.
