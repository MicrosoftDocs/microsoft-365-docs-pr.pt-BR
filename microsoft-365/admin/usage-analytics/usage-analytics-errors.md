---
title: Solução de problemas Microsoft 365 análise de uso
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Saiba como solucionar problemas com o aplicativo de modelo de análise de uso Microsoft 365 uso.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293730"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solução de problemas Microsoft 365 análise de uso

Explore a lista a seguir de mensagens de erro para obter ajuda com os problemas mais comuns com Microsoft 365 análise de uso.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Não somo capazes de processar seu pedido. Você precisa primeiro se inscrever para esses dados do centro de administração Microsoft 365 local

 **Código de Erro:** 422 
  
 **Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** Antes de se conectar ao aplicativo, você precisa assinar os dados do Microsoft 365 de administração. Se essa etapa não for feita primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID Microsoft 365 locatário. 
  
 **Para corrigir esse erro:** Para assinar os dados, vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de uso \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> na página principal do painel. Selecione o botão **Iniciar** e, em seguida, no  painel Relatórios que é aberto, a opção Disponibilizar dados para Microsoft 365 análise de uso para Power BI configuração e **Salvar**. 
  
## <a name="we-are-processing-your-data"></a>Estamos processando seus dados

 **Onde você verá esta mensagem:** No Microsoft 365 **de análise** de uso no painel **Uso** no Microsoft 365 de administração. 
  
 **Causa:** Quando você [opta por](enable-usage-analytics.md) ver dados no aplicativo de modelo do centro de administração Microsoft 365, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **Seus dados** estão prontos após 3 dias, entre em contato Microsoft 365 suporte [para empresas.](../../business-video/get-help-support.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Não podemos processar seu pedido neste momento. Ainda estamos preparando os dados para sua organização

 **Código de erro:** 423 
  
 **Onde você verá esta mensagem:** Em Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** Quando você [opta por ver](enable-usage-analytics.md) dados no aplicativo de modelo do centro de administração, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do locatário, essa etapa pode levar entre duas horas e 48 horas. 
  
 **Para corrigir isso:** Basta ter paciência, mas se a  mensagem não mudar para Seus dados estão prontos até 3 dias desde o início, entre em contato Microsoft 365 [suporte para empresas.](../../business-video/get-help-support.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>O ID do locatário que você forneceu não está no formato correto

 **Código de erro:** 400 
  
 **Onde você verá esta mensagem:** Em Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** A ID do locatário é um guid e deve estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se você inserir qualquer outra cadeia de caracteres na caixa de entrada do locatário, receberá esse erro. 
  
 **Para corrigir esse erro:** Vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso na página principal do painel. A ID do locatário está listada no azulejo. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>A ID do locatário fornecida não é reconhecida pelo nosso sistema

 **Código de erro:** 404 
  
 **Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** A ID de locatário fornecida não é válida ou não existe. 
  
 **Para corrigir esse erro:** Vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso na página principal do painel. A ID do locatário está listada no azulejo. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Reinsira suas credenciais para fazer login no Power BI novamente

Código de erro: 302
  
 **Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente. 
  
 **Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Você não tem a autorização certa para acessar esses dados. Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto

 **Código de erro:** 403 
  
 **Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting. 
  
 **Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados. 
  
 **Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um administrador  **global,** um administrador do **Exchange,** um administrador do **Skype for Business,** um administrador do **SharePoint,** um leitor **global** ou um leitor de relatório para se conectar ao aplicativo de modelo. Consulte [Sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
## <a name="refresh-failed"></a>Falha na atualização

 **Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização. 
  
 **Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não atualizadas nas configurações de conexão do aplicativo de modelo fazendo com que o usuário veja erros de falha de atualização. 
  
 **Para corrigir esse erro:** Em Power BI, encontre o conjuntos de dados correspondente ao aplicativo de  modelo de análise de uso Microsoft 365, selecione agendar atualização e fornecer suas credenciais de administrador. 
  
Se isso não funcionar, limpe o cache e re-crie o aplicativo de modelo.
  
  
