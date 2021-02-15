---
title: Ferramentas de avaliação de preparação
description: Explica as duas ferramentas, as verificações que são executados e o significado dos resultados
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1a00f7d5fb37cc9eea3f9454d473703084960864
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142928"
---
# <a name="readiness-assessment-tools"></a>Ferramentas de avaliação de preparação

Para a experiência mais tranquila possível ao se inscrever na Área de Trabalho Gerenciada da Microsoft, há configurações e outros parâmetros que você deve definir com antecedência e determinados requisitos de dispositivo e rede para atender. Uma ferramenta, acessada por meio do Portal de Administração da Área de Trabalho Gerenciada da Microsoft, verifica as configurações relacionadas ao gerenciamento. Outra ferramenta, que pode ser baixada, verifica requisitos de dispositivo individuais e configurações de rede. Você pode usar essas ferramentas para verificar essas configurações e receber etapas detalhadas para corrigir qualquer um que não seja correto.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Verificação da avaliação de preparação para download para dispositivos e rede

Para obter detalhes sobre como usar o verificador de avaliação de preparação para download, consulte o checker de [avaliação de preparação para download.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Ferramenta de avaliação de preparação online para configurações de gerenciamento

A ferramenta online verifica as configurações no Microsoft Endpoint Manager (especificamente, Microsoft Intune), Azure Active Directory (Azure AD) e Microsoft 365 para garantir que funcionarão com a Área de Trabalho Gerenciada da Microsoft. A Área de Trabalho Gerenciada da Microsoft mantém os dados associados a essas verificações por 12 meses após a última vez que você executar uma verificação em sua organização do Azure AD (locatário). Após 12 meses, nós o manteremos no formato não identificado. Você pode optar por excluir os dados que coletamos.

Qualquer pessoa com pelo menos a função Leitor Global ou Administrador do Intune poderá executar essa ferramenta, mas duas das verificações[(](readiness-assessment-fix.md#conditional-access-policies) políticas de acesso condicional e autenticação [multifator](readiness-assessment-fix.md#multifactor-authentication) exigem permissões adicionais.
 
A ferramenta de avaliação verifica estes itens:

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

|Cheque  |Descrição  |
|---------|---------|
|Perfil de implantação do Autopilot     | Verifica se a atribuição do perfil de implantação do Autopilot não se aplica a todos os dispositivos (o perfil não deve ser atribuído a nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft).        |
|Conectores de certificado     | Verifica o estado dos conectores de certificado para garantir que eles estão ativos   |
|Acesso condicional     | Verifica se as políticas de acesso condicional não estão atribuídas  a todos os usuários (as políticas de acesso condicional não devem ser atribuídas às contas de serviço da Área de Trabalho Gerenciada da Microsoft).)    |
|Políticas de conformidade do dispositivo     | Verifica se as políticas de conformidade do Intune  não estão atribuídas a todos os usuários (as políticas não devem ser atribuídas a nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft).    |
|Perfis de configuração do dispositivo     | Confirma se os perfis de configuração não estão atribuídos a todos os usuários ou a todos os dispositivos (os perfis de configuração não devem ser atribuídos a nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft).      |
|Restrições de tipo de dispositivo     | Verifica se os dispositivos Windows 10 em sua organização têm permissão para se inscrever no Intune        |
|Página status do registro     | Confirma se a Página de Status do Registro não está habilitada      |
|Registro do Intune     | Verifica se os dispositivos Windows 10 em sua organização do Azure AD são inscritos automaticamente no Intune         |
|Microsoft Store para empresas     | Confirma se a Microsoft Store para Empresas está habilitada e sincronizada com o Intune        |
|Autenticação de vários fatores | Verifica se a autenticação multifator não é aplicada às contas de serviço da Área de Trabalho Gerenciada da Microsoft.
|Scripts do PowerShell     | Verifica se os scripts do Windows PowerShell *não estão* atribuídos de uma maneira que direcionaria dispositivos da Área de Trabalho Gerenciada da Microsoft    |
|Região     | Verifica se sua região é suportada pela Área de Trabalho Gerenciada da Microsoft        |
|Linhas de base de segurança     | Verifica se o perfil de linha de base de segurança  não tem como alvo todos os usuários ou todos os dispositivos (as políticas de linha de base de segurança não devem direcionar nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft).       |
|Aplicativos do Windows     | Revise quais aplicativos você deseja atribuir aos dispositivos da Área de Trabalho Gerenciada da Microsoft      |
|Windows Hello para Empresas     | Verifica se o Windows Hello para Empresas está habilitado        |
|Anel de atualização do Windows 10     | Verifica se a política "anel de atualização do Windows 10" do Intune  não tem como alvo todos os usuários ou todos os dispositivos (a política não deve ter como alvo nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft).     |


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

|Cheque  |Descrição  |
|---------|---------|
|Assinaturas "Ad hoc" para Enterprise State Roaming     | Aconselha como verificar uma configuração que (se definida como "false") pode impedir que o Enterprise State Roaming funciona corretamente  |
|Roaming de Estado da Empresa     | Aconselha a verificar se o Enterprise State Roaming está habilitado       |
|Licenças     | Verifica se você obteve as [licenças necessárias](prerequisites.md#more-about-licenses)         |
|Autenticação de vários fatores     | Verifica se a autenticação multifator não é aplicada a todos os usuários (a autenticação multifator não deve ser aplicada acidentalmente às contas de serviço da Área de Trabalho Gerenciada da Microsoft).)|
|Nomes de contas de segurança   | Verifica se nenhum nome de usuário está em conflito com aqueles que a Área de Trabalho Gerenciada da Microsoft reserva para seu próprio uso        |
|Funções de administrador de segurança     | Confirma se os usuários com funções Leitor de Segurança, Operador de Segurança ou Leitor Global foram atribuídos a essas funções no Microsoft Defender para Ponto de Extremidade         |
|Padrões de segurança | Verifica se sua organização do Azure AD tem padrões de segurança habilitados no Azure Active Directory |
|Redefinição de senha por autoatendimento     | Confirma se a redefinição de senha de autoatendencial está habilitada        |
|Função de usuário padrão     | Verifica se os usuários são usuários padrão e não têm direitos de administrador local         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Configurações do Microsoft 365 Apps para empresas

|Cheque  |Descrição  |
|---------|---------|
|OneDrive for Business     | Verifica se o OneDrive for Business está usando configurações sem suporte.        |


Para cada verificação, a ferramenta relatará um dos quatro resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Aviso    | Siga as etapas na ferramenta para ter a melhor experiência com o registro e os usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.        |
|Não está pronto | *O registro falhará* se você não corrigir esses problemas. Siga as etapas na ferramenta para resolvê-las.        |
|Error | A função do Azure Active Director (AD) que você está usando não tem permissão suficiente para executar essa verificação. |

## <a name="after-enrollment"></a>Após o registro

Depois de concluir o registro na Área de Trabalho Gerenciada da Microsoft, lembre-se de voltar e ajustar determinadas configurações do Intune e do Azure AD. Para obter detalhes, consulte [Ajustar configurações após o registro.](../get-started/conditional-access.md)
