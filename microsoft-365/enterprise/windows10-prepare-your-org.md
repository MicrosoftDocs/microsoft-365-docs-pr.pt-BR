---
title: Preparar sua organização para Windows 10 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas que necessárias para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Implantação do Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 documentação, Windows 10 Enterprise,
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865213"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Etapa 1: Preparar sua organização para Windows 10 Enterprise

*Este artigo se aplica às versões E3 tanto o E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Antes de atualizar seus dispositivos para Windows 10 Enterprise, considere o seguinte:

- **Os domínios devem ser adicionados e verificados** <br>Com uma assinatura do Microsoft 365, você obtém um nome de domínio padrão que termina no onmicrosoft.com (por exemplo, contoso.onmicrosoft.com). A maioria das organizações preferem usar um ou mais dos domínios que possuem para terminam de seus endereços de email em seu próprio nome de domínio (como username@contoso.com). Para usar seu próprio domínio, você precisará adicioná-lo à Microsoft 365 e verificar se você é proprietário. É recomendável que você adicione e verifique se seus domínios agora para que fiquem prontos para ir sempre que você configurar os serviços Microsoft 365, como email e Skype para negócios.
- **Você não precisa adicionar usuários neste momento** <br>Para usar os serviços Microsoft 365 ou instalar produtos do Microsoft 365, os usuários precisam de contas no Microsoft 365 e que precisam de licenças de produto. Como adicionar usuários ao Microsoft 365 depende do número de usuários e se você possui atualmente do Active Directory local. Se você não tiver o Active Directory (ou você tenha o Active Directory, mas não deseja sincronizá-lo com o Microsoft 365), você pode adicionar usuários diretamente à Microsoft 365 e atribuir licenças, individualmente ou em massa.<br>Se você tiver o Active Directory local, você poderá [sincronizá-lo com o Microsoft 365](identity-azure-ad-connect-health.md) para criar contas de usuário no Windows Azure AD, o diretório em nuvem usado pelo Microsoft 365. Com este método, você pode criar contas para usuários e grupos de segurança que você pode usar para gerenciar permissões para recursos (como os conjuntos de sites do SharePoint Online ou documentos). Sincronizar seu Active Directory com o Microsoft 365 não atribuir licenças aos usuários.
- **Você não precisa licenciar usuários neste momento** <br>Antes que os usuários podem usar os serviços Microsoft 365 ou instale o software do portal do Microsoft 365, elas precisam licenças do produto. Como um administrador de gerenciamento global ou de usuário, você pode atribuir diretamente licenças de produtos no Microsoft 365 individualmente ou em massa. Você também pode usar o [licenciamento baseado no grupo](identity-group-based-licensing.md) automaticamente atribuir licenças quando usuários forem adicionados a um determinado grupo. 
- **Você instala o Office 365 ProPlus separadamente** <br>Obter uma licença do Microsoft 365 não instalar automaticamente Office 365 ProPlus em seus computadores clientes. Consulte [fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) para obter mais informações. 

## <a name="set-windows-diagnostics-data-level"></a>Definir nível de dados de diagnóstico do Windows

A Microsoft usa os dados de diagnóstico para ajudar a manter o Windows dispositivos seguro identificando tendências de malware e outras ameaças e para ajudar a melhorar a qualidade dos serviços do Windows e a Microsoft. Certifique-se de que o serviço de diagnóstico está habilitado em um nível mínimo de básica em todos os pontos de extremidade em sua organização. *Por padrão, esse serviço é habilitado e definido como o nível Avançado.* No entanto, é recomendável verificar e certifique-se de que estão recebendo dados. A definição de níveis por meio de diretivas substitui as configurações no nível do dispositivo. 

**Níveis de dados de diagnóstico de sistema operacional Windows 10**

Você pode configurar suas configurações de dados de diagnóstico de sistema operacional usando as ferramentas de gerenciamento que você estiver usando já, como a diretiva de grupo, MDM ou provisionamento do Windows. Você pode alterar também manualmente suas configurações usando o Editor do registro. A definição de seus níveis de dados de diagnóstico através de uma política de gerenciamento substitui quaisquer configurações de nível de dispositivo.

Use o valor apropriado na tabela a seguir ao configurar a política de gerenciamento.

| Nível | Dados coletados | Valor |
|:--- |:--- |:--- |
| Segurança | Somente dados de segurança. | 0 |
| Básica | Dados de segurança e sistema básico e dados de qualidade. | 1 |
| Avançado | Dados de segurança, sistema básico e dados de qualidade e ideias avançadas e dados de confiabilidade avançada. | 2 |
| Completo | Dados de segurança, sistema básico e dados de qualidade, ideias avançadas e dados de confiabilidade avançada e dados de diagnóstico completo. | 3 |

Você pode permitir que os dados de diagnóstico por meio de qualquer um desses métodos:

* **Microsoft Intune** - se você planeja usar Intune para gerenciar seus dispositivos, você pode criar uma política de configuração para permitir que os dados de diagnósticos definindo a política de sistema <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> . Para obter mais informações sobre como configurar políticas de configuração, consulte [Gerenciar configurações e recursos em seus dispositivos com Microsoft Intune políticas](https://aka.ms/intuneconfigpolicies).
* **Editor do registro** - você pode usar o Editor do registro para habilitar manualmente os dados de diagnóstico em cada dispositivo na sua organização. Como alternativa, você pode escrever um script para editar o registro. Se já existir uma política de gerenciamento, como a diretiva de grupo ou MDM, ele substituirá essa configuração do registro.
* **Diretiva de grupo** - se você não pretende registrar dispositivos no Intune, você pode usar um objeto de diretiva de grupo para definir o nível de dados de diagnóstico da sua organização.
* **Prompt de comando** - você pode definir os dados de diagnóstico do Windows 10 e o serviço a ser iniciado automaticamente com o prompt de comando. Este método é melhor se você estiver testando o serviço em apenas alguns dispositivos. Habilitando o serviço iniciar automaticamente com este comando não configurará o nível de dados de diagnóstico. Se você não tiver configurado um nível de dados de diagnóstico usando ferramentas de gerenciamento, o serviço funcionará com o padrão nível Avançado.

Consulte [Configurar o Windows de dados de diagnóstico em sua organização](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) para saber mais sobre dados de diagnóstico do Windows e como você poderá habilitá-lo com base no método que você escolher.

Como ponto de verificação provisório, você pode consultar os [critérios de saída](windows10-exit-criteria.md#crit-windows10-step1) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Implantar o Windows 10 Enterprise para dispositivos existentes como uma atualização in-loco](windows10-deploy-inplaceupgrade.md) |






