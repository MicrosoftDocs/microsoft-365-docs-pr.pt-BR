---
title: Solução de problemas da análise de uso do Microsoft 365
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
description: Saiba como solucionar problemas com o aplicativo de modelo análise de uso do Microsoft 365.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580733"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solução de problemas da análise de uso do Microsoft 365

Explore a lista a seguir de mensagens de erro para obter ajuda com os problemas mais comuns com a análise de uso do Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Não somo capazes de processar seu pedido. Você precisa assinar primeiro esses dados do Centro de administração do Microsoft 365

 **Código de Erro:** 422 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** Antes de se conectar ao aplicativo, você precisa assinar os dados do centro de administração do Microsoft 365. Se essa etapa não for feita primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID de locatário do Microsoft 365. 
  
 **Para corrigir esse erro:** Para assinar os dados, vá para o centro de administração Relatórios Uso e localize o pacote de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página principal do painel. Selecione o **botão Iniciar** e, em seguida, no painel Relatórios que é aberto, a opção Disponibilizar dados para a análise de uso do **Microsoft 365** para a configuração do Power BI e **Salvar**. 
  
## <a name="we-are-processing-your-data"></a>Estamos processando seus dados

 **Onde você verá esta mensagem:** No pacote análise de uso do **Microsoft 365** no painel **Uso** no centro de administração do Microsoft 365. 
  
 **Causa:** Quando você [opta](enable-usage-analytics.md) por ver dados no aplicativo de modelo do Centro de administração do Microsoft 365, o sistema do Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas. 
  
 **Para corrigir isso:** Basta ter paciência, mas se a mensagem não mudar para **Seus dados** estão prontos após 3 dias, contate o [Microsoft 365 para suporte comercial](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Não podemos processar seu pedido neste momento. Ainda estamos preparando os dados para sua organização

 **Código de erro:** 423 
  
 **Onde você verá esta mensagem:** No Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** Quando você [opta por ver](enable-usage-analytics.md) dados no aplicativo de modelo do centro de administração, o sistema do Microsoft 365 começa a gerar dados de uso histórico para sua organização. Dependendo do tamanho do locatário, essa etapa pode levar entre duas horas e 48 horas. 
  
 **Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **Seus** dados estão prontos até 3 dias desde o início, contate o [Microsoft 365 para suporte comercial.](../contact-support-for-business-products.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>O ID do locatário que você forneceu não está no formato correto

 **Código de erro:** 400 
  
 **Onde você verá esta mensagem:** No Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** A ID do locatário é um guid e deve estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se você inserir qualquer outra cadeia de caracteres na caixa de entrada do locatário, receberá esse erro. 
  
 **Para corrigir esse erro:** Vá para o centro de administração Relatórios uso e localize o pacote de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página do painel principal. A ID do locatário está listada no azulejo. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>A ID do locatário fornecida não é reconhecida pelo nosso sistema

 **Código de erro:** 404 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** A ID de locatário fornecida não é válida ou não existe. 
  
 **Para corrigir esse erro:** Vá para o centro de administração Relatórios uso e localize o pacote de análise de uso do \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 na página do painel principal. A ID do locatário está listada no azulejo. Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Reinsira suas credenciais para fazer login no Power BI novamente

Código de erro: 302
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente. 
  
 **Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Você não tem a autorização certa para acessar esses dados. Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto

 **Código de erro:** 403 
  
 **Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso do Microsoft 365 ou ao chamar diretamente as APIs de Relatório do Microsoft 365. 
  
 **Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados. 
  
 **Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um administrador  **global,** administrador do **Exchange,** administrador do Skype for **Business,** administrador do **SharePoint,** leitor **global** ou leitor de relatório para se conectar ao aplicativo de modelo. Consulte [Sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações. 
  
## <a name="refresh-failed"></a>Falha na atualização

 **Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização. 
  
 **Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não atualizadas nas configurações de conexão do aplicativo de modelo fazendo com que o usuário veja erros de falha de atualização. 
  
 **Para corrigir esse erro:** No Power BI, encontre o conjuntos de dados correspondente ao aplicativo de modelo análise de uso do Microsoft 365, **selecione** agendar atualização e fornecer suas credenciais de administrador. 
  
Se isso não funcionar, limpe o cache e re-crie o aplicativo de modelo.
  
  
