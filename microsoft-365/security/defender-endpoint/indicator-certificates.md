---
title: Criar indicadores com base em certificados
ms.reviewer: ''
description: Crie indicadores com base em certificados que definem a detecção, a prevenção e a exclusão de entidades.
keywords: ioc, certificado, certificados, gerenciar, permitido, bloqueado, bloquear, limpar, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845445"
---
# <a name="create-indicators-based-on-certificates"></a>Criar indicadores com base em certificados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Você pode criar indicadores para certificados. Alguns casos de uso comuns incluem:

- Cenários quando você precisa implantar tecnologias de bloqueio, como regras de redução de superfície de ataque e acesso controlado a pastas, mas precisa permitir comportamentos de aplicativos assinados adicionando o certificado na lista de autorizações. [](attack-surface-reduction.md) [](controlled-folders.md)
- Bloqueando o uso de um aplicativo assinado específico em toda a sua organização. Ao criar um indicador para bloquear o certificado do aplicativo, Windows Defender AV impedirá execuções de arquivo (bloquear e remediar) e a Investigação Automatizada e Correção se comportará da mesma forma.


### <a name="before-you-begin"></a>Antes de começar

É importante entender os seguintes requisitos antes da criação de indicadores para certificados:

- Esse recurso estará disponível se sua organização usar Windows Defender Antivírus e a proteção baseada em nuvem estiver habilitada. Para obter mais informações, consulte [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.
- Com suporte em máquinas Windows 10, versão 1703 ou posterior, Windows 2016 e 2019.
- As definições de proteção contra vírus e ameaças devem estar atualizadas.
- No momento, esse recurso dá suporte à inserção de . CER ou . Extensões de arquivo PEM.

>[!IMPORTANT]
> - Um certificado folha válido é um certificado de assinatura que tem um caminho de certificação válido e deve ser encadeado à Autoridade de Certificação Raiz (CA) confiável pela Microsoft.  Como alternativa, um certificado personalizado (auto-assinado) pode ser usado desde que ele seja confiável pelo cliente (o certificado de AC raiz é instalado sob a Máquina Local 'Autoridades de Certificação Raiz Confiáveis').
>- Os filhos ou pai dos IOCs de certificado de permitir/bloquear não estão incluídos na funcionalidade IoC de permitir/bloquear, apenas certificados folha são suportados.
>- Os certificados assinados pela Microsoft não podem ser bloqueados.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Crie um indicador para certificados na página de configurações:

>[!IMPORTANT]
> Pode levar até 3 horas para criar e remover um IoC de certificado.

1. No painel de navegação, selecione **Configurações**  >  **Indicadores**.  

2. Selecione a **guia Certificado.**

3. Selecione **Adicionar indicador**.

4. Especifique os seguintes detalhes:
   - Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.
   - Ação - Especifique a ação a ser tomada e forneça uma descrição.
   - Escopo - Definir o escopo do grupo de máquinas.

5. Revise os detalhes na guia Resumo e clique em **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados
- [Criar indicadores](manage-indicators.md)
- [Criar indicadores para arquivos](indicator-file.md)
- [Criar indicadores para IPs e URLs/domínios](indicator-ip-domain.md)
- [Gerenciar indicadores](indicator-manage.md)
