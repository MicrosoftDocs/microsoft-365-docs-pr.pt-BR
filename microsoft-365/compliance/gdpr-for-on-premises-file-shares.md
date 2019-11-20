---
title: RGPD para compartilhamentos de arquivos locais
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Saiba mais sobre como atender aos requisitos de RGPD em compartilhamentos de arquivos no Windows Server local.
ms.openlocfilehash: 1b57bff104539691ca53c3c90dc676b7c0769743
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749609"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a>RGPD para compartilhamentos de arquivos no Windows Server local

A abordagem básica recomendada para compartilhamentos de arquivos é a seguinte:

-   Use a Proteção de Informações do Azure para identificar os dados confidenciais.

-   Use o verificador da Proteção de Informações do Azure para encontrar dados.

A abordagem recomendada para compartilhamentos de arquivos inclui estas etapas:

1.  **Instale e configure o verificador da Proteção de Informações do Azure.**

    -   Decida quais tipos de dados confidenciais usar.

    -   Especifique pastas locais e compartilhamentos de rede a serem usados.

2.  **Execute um ciclo de descoberta.**

    -   Execute o verificador no modo de descoberta e valide os resultados.

    -   Se necessário, otimize as condições e os tipos de informações confidenciais.

    -   Avalie o impacto esperado de aplicar rótulos automaticamente.

3.  **Execute o verificador da Proteção de Informações do Azure para aplicar rótulos a documentos qualificados**.

4.  **Para a proteção:**

    -   Configure regras de prevenção contra a perda de dados do Exchange para proteger documentos com o rótulo desejado.

    -   Certifique-se de usar permissões para limitar quem pode acessar os arquivos.

5.  **Para monitorar, integre os registros do Windows Server com uma ferramenta SIEM.**

    -   Para localizar dados pessoais para solicitações de titulares de dados, use o verificador da Proteção de Informações do Azure. Você também pode configurar a pesquisa do SharePoint Server para rastrear compartilhamentos de arquivos.

Confira mais informações sobre como usar o verificador da Proteção de Informações do Azure para localizar e rotular dados pessoais.O Microsoft GDPR Data Discovery Toolkit se encontra em [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>).

Confira informações sobre como configurar o verificador para utilizar condições e os tipos de informações confidenciais para prevenção contra perda de dados (DLP) do Office 365 em [Como configurar as condições de classificação automática e recomendada para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Observe que os novos tipos de informações confidenciais do Office 365 não estarão disponíveis imediatamente para uso com o verificador e que tipos de informações confidenciais personalizadas não podem ser usadas com o verificador.
