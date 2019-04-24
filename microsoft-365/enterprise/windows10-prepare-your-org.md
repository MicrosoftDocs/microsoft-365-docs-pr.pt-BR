---
title: Preparar sua organização para o Windows 10 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas de que você precisa para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, implantação
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 9b09f21c71f578c45a71149cedfd67a8ea9104e6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289395"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Etapa 1: preparar sua organização para o Windows 10 Enterprise

*Este artigo aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Antes de atualizar seus dispositivos para o Windows 10 Enterprise, considere o seguinte:

- **Seus domínios devem ser adicionados e verificados** <br>
  Com uma assinatura do Microsoft 365, você obtém um nome de domínio padrão que termina no onmicrosoft.com (por exemplo, contoso.onmicrosoft.com). A maioria das organizações prefere usar um ou mais domínios que eles possuem para que seus endereços de email sejam encerrados em seu próprio nome de domínio (como username@contoso.com). Para usar seu próprio domínio, é necessário adicioná-lo ao Microsoft 365 e verificar se você é o proprietário dele. Recomendamos que você adicione e verifique seus domínios agora para que eles estejam prontos sempre que você configurar os serviços do Microsoft 365, como email e Skype for Business.
- **Você não precisa adicionar usuários no momento** <br>
  Para usar os serviços do Microsoft 365 ou instalar produtos da Microsoft 365, os usuários precisam de contas no Microsoft 365 e precisam de licenças de produto. O modo como você adiciona usuários à Microsoft 365 depende do número de usuários e se você tem atualmente o Active Directory no local. Se você não tiver o Active Directory (ou se tiver o Active Directory, mas não quiser sincronizá-lo para o Microsoft 365), poderá adicionar usuários diretamente ao Microsoft 365 e atribuir licenças, individualmente ou em massa. <br>
  Se você tiver o Active Directory local, poderá [sincronizá-lo com o microsoft 365](identity-azure-ad-connect.md#identity-sync) para criar contas de usuário no Azure AD, o diretório de nuvem usado pelo Microsoft 365. Com esse método, você pode criar contas para usuários e grupos de segurança que você usa para gerenciar permissões para recursos (como conjuntos de sites ou documentos do SharePoint Online). A sincronização do seu Active Directory com o Microsoft 365 não atribuirá licenças aos usuários.
- **Você não precisa licenciar usuários no momento** <br>
  Para que os usuários possam usar os serviços do Microsoft 365 ou instalar software do portal do Microsoft 365, eles precisam de licenças de produto. Como administrador global ou de gerenciamento de usuários, você pode atribuir diretamente licenças de produtos no Microsoft 365 individualmente ou em massa. Você também pode usar o [Licenciamento baseado em grupo](identity-self-service-group-management.md#identity-group-license) para atribuir licenças automaticamente quando os usuários são adicionados a um determinado grupo. 
- **Você instala o Office 365 proPlus separadamente** <br>
  A obtenção de uma licença do Microsoft 365 não instala automaticamente o Office 365 proPlus em seus computadores cliente. Consulte a [fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) para obter mais informações. 

## <a name="set-windows-diagnostics-data-level"></a>Definir nível de dados de diagnóstico do Windows

A Microsoft usa dados de diagnóstico para ajudar a manter os dispositivos Windows seguros identificando tendências de malware e outras ameaças, e para nos ajudar a melhorar a qualidade dos serviços do Windows e da Microsoft. Você deve garantir que o serviço de diagnóstico esteja habilitado em um nível mínimo de básico em todos os pontos de extremidade da sua organização. *Por padrão, esse serviço é habilitado e definido como o nível avançado.* No enTanto, é uma boa prática verificar e garantir que eles estejam recebendo dados do sensor. A configuração de níveis por meio de políticas substitui as configurações no nível do dispositivo. 

**Níveis de dados de diagnóstico do sistema operacional Windows 10**

Você pode definir as configurações de dados de diagnóstico do sistema operacional usando as ferramentas de gerenciamento que você já está usando, como política de grupo, MDM ou provisionamento do Windows. Você também pode alterar manualmente suas configurações usando o editor do registro. A configuração dos níveis de dados de diagnóstico por meio de uma política de gerenciamento substitui qualquer configuração de nível de dispositivo.

Use o valor apropriado na tabela abaixo ao configurar a política de gerenciamento.

| Nível | Dados coletados | Valor |
|:--- |:--- |:--- |
| Segurança | Somente dados de segurança. | ,0 |
| Básica | Dados de segurança e dados básicos de sistema e de qualidade. | 1 |
| Metarquivo | Dados de segurança, dados básicos de sistema e de qualidade, e ideias aprimoradas e dados avançados de confiabilidade. | duas |
| Inteiro | Dados de segurança, dados básicos de sistema e de qualidade, informações aprimoradas e dados de confiabilidade avançados e dados de diagnóstico completo. | 3D |

Você pode habilitar os dados de diagnóstico através de qualquer um destes métodos:

* **Microsoft Intune** – se você planeja usar o Intune para gerenciar seus dispositivos, é possível criar uma política de configuração para habilitar os dados de diagnóstico, configurando a política de sistema do <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> . Para obter mais informações sobre como configurar políticas de configuração, consulte [gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune](https://aka.ms/intuneconfigpolicies).
* **Editor do registro** -você pode usar o editor do registro para habilitar manualmente os dados de diagnóstico em cada dispositivo da sua organização. Como alternativa, você pode escrever um script para editar o registro. Se uma política de gerenciamento já existir, como política de grupo ou MDM, ela substituirá essa configuração do registro.
* **Política de grupo** -se você não planeja registrar dispositivos no Intune, você pode usar um objeto de política de grupo para definir o nível de dados de diagnóstico da sua organização.
* **Prompt de comando** -você pode configurar os dados de diagnóstico e o serviço do Windows 10 para que iniciem automaticamente com o prompt de comando. Esse método é melhor se você estiver testando o serviço em apenas alguns dispositivos. Habilitar o serviço para iniciar automaticamente com este comando não irá configurar o nível de dados de diagnóstico. Se você não configurou um nível de dados de diagnóstico usando ferramentas de gerenciamento, o serviço funcionará com o nível avançado padrão.

ConFira [configurar os dados de diagnóstico do Windows em sua organização](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) para saber mais sobre os dados de diagnóstico do Windows e como habilitá-lo com base no método escolhido.

Como ponto de verificação provisório, é possível conferir os [Critérios de saída](windows10-exit-criteria.md#crit-windows10-step1) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Implantar o Windows 10 Enterprise para dispositivos existentes como uma atualização in-loco](windows10-deploy-inplaceupgrade.md) |






