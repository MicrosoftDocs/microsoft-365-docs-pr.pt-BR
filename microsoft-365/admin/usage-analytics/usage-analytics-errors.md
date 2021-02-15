---
title: Solução de problemas da análise de uso do Microsoft 365
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Saiba como solucionar problemas com o aplicativo de modelo da Análise de Uso do Microsoft 365.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841430"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solução de problemas da análise de uso do Microsoft 365

Explore a lista de mensagens de erro a seguir para obter ajuda com os problemas mais comuns com a análise de uso do Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Não somo capazes de processar seu pedido. Você precisa primeiro assinar esses dados no Centro de administração do Microsoft 365

 **Código de erro:** 422 
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** Antes de se conectar ao aplicativo, você precisa assinar os dados do centro de administração do Microsoft 365. Se essa etapa não for feita primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID de locatário do Microsoft 365. 
  
 **Para corrigir esse erro:** Para assinar os dados, vá para o centro de administração Relatórios de uso e localize o painel de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página principal do painel. Selecione o botão **Iniciar** e, no painel Relatórios que é aberto, a acione e salve a análise de uso do **Microsoft 365** para a análise de uso do Power BI. 
  
## <a name="we-are-processing-your-data"></a>Estamos processando seus dados

 **Onde você verá esta mensagem:** No painel análise de uso do **Microsoft 365,** no **Painel** de uso do Centro de administração do Microsoft 365. 
  
 **Causa:** Quando [você](enable-usage-analytics.md) opta por ver dados no aplicativo de modelo do centro de administração do Microsoft 365, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem  não mudar para Seus dados estiver pronta após 3 dias, entre em contato com o suporte do [Microsoft 365 para empresas.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Não podemos processar seu pedido neste momento. Ainda estamos preparando os dados para sua organização

 **Código de erro:** 423 
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo da Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** Quando você [opta](enable-usage-analytics.md) por ver dados no aplicativo de modelo do centro de administração, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do locatário, essa etapa pode levar de duas horas a 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem  não mudar para Seus dados estiver pronta até três dias desde o início, entre em contato com o suporte do [Microsoft 365 para empresas.](../contact-support-for-business-products.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>O ID do locatário que você forneceu não está no formato correto

 **Código de erro:** 400 
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo da Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** A ID de locatário é um guid e deve estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se você inserir qualquer outra cadeia de caracteres na caixa de entrada do locatário, receberá esse erro. 
  
 **Para corrigir esse erro:** Vá para o centro de administração De uso de relatórios e localize o painel de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página principal do painel. A ID de locatário está listada noile. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo modelo. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>A ID do locatário fornecida não é reconhecida pelo nosso sistema

 **Código de erro:** 404 
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** A ID de locatário fornecida não é válida ou não existe. 
  
 **Para corrigir esse erro:** Vá para o centro de administração De uso de relatórios e localize o painel de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página principal do painel. A ID de locatário está listada noile. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo modelo. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Reinsira suas credenciais para fazer login no Power BI novamente

Código de erro: 302
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente. 
  
 **Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Você não tem a autorização certa para acessar esses dados. Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto

 **Código de erro:** 403 
  
 **Onde você verá esta mensagem:** No Power BI, quando você está se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados. 
  
 **Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um administrador  **global,** administrador do **Exchange,** administrador do Skype for **Business**, administrador do **SharePoint**, leitor **global** ou leitor de relatório para se conectar ao aplicativo de modelo. Consulte [Mais informações sobre funções](../add-users/about-admin-roles.md) de administrador. 
  
## <a name="refresh-failed"></a>Falha na atualização

 **Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização. 
  
 **Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não atualizadas nas configurações de conexão do aplicativo modelo fazendo com que o usuário veja erros de falha de atualização. 
  
 **Para corrigir esse erro:** No Power BI, encontre o conjuntos de dados correspondente ao aplicativo  de modelo da Análise de Uso do Microsoft 365, selecione a atualização do cronograma e forneça suas credenciais de administrador. 
  
Se isso não funcionar, limpe o cache e crie o aplicativo de modelo.
  
  
