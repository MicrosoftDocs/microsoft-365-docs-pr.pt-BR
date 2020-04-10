---
title: Solucionando problemas de análise de uso do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Saiba como solucionar problemas com o aplicativo de modelo de análise de uso do Microsoft 365.
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212144"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solucionando problemas de análise de uso do Microsoft 365

Explore a seguinte lista de mensagens de erro para obter ajuda com os problemas mais comuns com a análise de uso do Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Não somo capazes de processar seu pedido. Você deve primeiro inscrever-se nesses dados do centro de administração do Microsoft 365

 **Código de erro:** 422 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** Antes de poder se conectar ao aplicativo, você precisa inscrever-se nos dados do centro de administração do Microsoft 365. Se esta etapa não for executada primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID de locatário do Microsoft 365. 
  
 **Para corrigir esse erro:** Para inscrever-se nos dados, acesse o \> **Centro** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Administração e localize</a> o bloco de análise de uso do Microsoft 365 na página principal do painel. Selecione o **botão introdução** **e,** em seguida, no painel **relatórios** que é aberto, ative a configuração **disponibilizar dados para análise de uso do Microsoft 365 para Power bi** .
  
## <a name="we-are-processing-your-data"></a>Estamos processando seus dados

 **Onde você verá esta mensagem:** No bloco de **análise de uso do microsoft 365** , no painel de **uso** do centro de administração do Microsoft 365. 
  
 **Causa:** Quando você [optar por ver dados no aplicativo de modelo](enable-usage-analytics.md) do centro de administração do Microsoft 365, o sistema Microsoft 365 começará a gerar dados de uso históricos para sua organização. Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **seus dados estiver pronta** após 3 dias, [entre em contato com o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Não podemos processar seu pedido neste momento. Ainda estamos preparando os dados para sua organização

 **Código de erro:** 423 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** Quando você [optar por ver dados no aplicativo de modelo](enable-usage-analytics.md) a partir do centro de administração, o sistema Microsoft 365 começa a gerar dados de uso históricos para sua organização. Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **seus dados estiver pronta** até 3 dias desde o início, [entre em contato com o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>O ID do locatário que você forneceu não está no formato correto

 **Código de erro:** 400 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** A ID do locatário é um guid e tem que estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se você inserir qualquer outra sequência na caixa de entrada do locatário, você receberá esse erro. 
  
 **Para corrigir esse erro:** Vá para \> o centro de administração de **relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> e localize o bloco de análise de uso do Microsoft 365 na página de painel principal. A ID do locatário está listada no bloco. Você pode copiá-lo daqui e colá-lo na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>A ID do locatário fornecida não é reconhecida pelo nosso sistema

 **Código de erro:** 404 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** A ID do locatário fornecida não é válida ou não existe. 
  
 **Para corrigir esse erro:** Vá para \> o centro de administração de **relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> e localize o bloco de análise de uso do Microsoft 365 na página de painel principal. A ID do locatário está listada no bloco. Você pode copiá-lo daqui e colá-lo na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Reinsira suas credenciais para fazer login no Power BI novamente

Código de erro: 302
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente. 
  
 **Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Você não tem a autorização certa para acessar esses dados. Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto

 **Código de erro:** 403 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365. 
  
 **Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados. 
  
 **Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um **administrador global**, **administrador do Exchange**, **administrador do Skype for Business**, administrador **do SharePoint**, **leitor global** ou **leitor de relatórios** para se conectar ao aplicativo de modelo. Consulte [sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
## <a name="refresh-failed"></a>Falha na atualização

 **Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização. 
  
 **Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não são atualizadas nas configurações de conexão do aplicativo de modelo que fazem com que o usuário veja erros de falha na atualização. 
  
 **Para corrigir esse erro:** No Power BI, encontre o conjunto de um correspondente ao aplicativo de modelo de análise de uso do Microsoft 365, selecione **agendar atualização** e forneça suas credenciais de administrador. 
  
Se isso não funcionar, limpe o cache e recrie o aplicativo de modelo.
  
  
