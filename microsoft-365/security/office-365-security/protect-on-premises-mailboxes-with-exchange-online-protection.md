---
title: Proteger caixas de correio locais com o Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: Mesmo que você planeje hospedar algumas ou todas as suas caixas de correio no local, ainda poderá proteger as caixas de correio com o Exchange Online Protection (EOP). Para configurar conectores, você precisa ter uma conta de administrador global do Office 365 ou de administrador da empresa do Exchange (grupo de funções do Gerenciamento de Organização). Para obter informações sobre como as permissões do Office 365 se relacionam às permissões do Exchange, consulte Atribuindo funções de administrador no Office 365 operado pela 21Vianet. Se todas as suas caixas de correio do Exchange estiverem no local, siga estas etapas para configurar o serviço EOP.
ms.openlocfilehash: 787c01ff7d06943b51916675b9e30dc3f020d5e1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073596"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Proteger caixas de correio locais com o Exchange Online Protection

> [!NOTE]
> Este artigo aplica-se somente ao Office 365 operado pela 21Vianet na China. 
  
Mesmo que você planeje hospedar algumas ou todas as suas caixas de correio no local, ainda poderá proteger as caixas de correio com o Exchange Online Protection (EOP). Para configurar conectores, você precisa ter uma conta de administrador global do Office 365 ou de administrador da empresa do Exchange (grupo de funções do Gerenciamento de Organização). Para obter informações sobre como as permissões do Office 365 se relacionam às permissões do Exchange, consulte [atribuindo funções de administrador no Office 365 operado pela 21vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). Se todas as suas caixas de correio do Exchange estiverem no local, siga estas etapas para configurar o serviço EOP. 
  
## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: usar o centro de administração do Microsoft 365 para adicionar e verificar seu domínio

1. No centro de administração do Microsoft 365, navegue até configuração para adicionar seu domínio ao serviço.
    
2.  Siga as etapas no portal para adicionar os registros DNS aplicáveis ao seu provedor de Hospedagem de DNS, a fim de verificar a propriedade do domínio. 
    
> [!TIP]
> [Adicione seu domínio e seus usuários ao office 365 operado pela 21vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) e [crie registros DNS para o Office 365 ao gerenciar seus registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) são recursos úteis para referência à medida que você adiciona seu domínio ao serviço e configura o DNS. 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Etapa 2: Adicionar destinatários e configurar o tipo de domínio

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre o DBEB, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para obter instruções detalhadas, consulte [Create Required Connectors to set up Basic email flow by EOP](https://go.microsoft.com/fwlink/?LinkId=506780).
  
 Como saber se essa tarefa funcionou? 
  
 Use o Analisador de Conectividade Remota para executar um teste que verifica o fluxo de mensagens entre o serviço e o seu ambiente. Para obter mais informações, consulte a seção "usar o analisador de conectividade remota para testar a entrega de emails" em [Test Mail Flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Após configurar os conectores, espere 72 horas para permitir a propagação das atualizações dos registros de DNS. Depois disso, restrinja o tráfego SMTP da porta-25 de entrada em seu firewall ou servidores de email para aceitar emails somente dos datacenters do EOP, especificamente dos endereços IP listados em [URLs e intervalos de endereços IP do Office 365 operado pela 21vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.
  
> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceita na maioria das situações, o que fornece um pequeno atraso no caso de uma mensagem enviada com um anexo grande, por exemplo. 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: Usar o Shell para se certificar que spam é roteado para a pasta de email de lixo eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas [para garantir que o spam seja roteado para a pasta lixo eletrônico de cada usuário](https://go.microsoft.com/fwlink/?LinkId=506804). Se não quiser mover mensagens para a pasta de Lixo Eletrônico de cada usuário, você pode escolher outra ação editando suas políticas de filtro de conteúdo no centro de administração do Exchange. Para obter mais informações, consulte [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805). 
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: usar o centro de administração do Microsoft 365 para apontar o seu registro MX para o EOP

Siga as etapas de configuração de domínio do Office 365 para atualizar o registro MX do seu domínio, para que haja fluxo da EOP no seu email de entrada. Para obter mais informações, você pode fazer referência [a criar registros DNS para o Office 365 ao gerenciar seus registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).
  
Como saber se essa tarefa funcionou?
  
 Use o Analisador de Conectividade Remota para executar um teste que verifica o seu registro MX. Para obter mais informações, consulte a seção "usar o analisador de conectividade remota para testar seu registro MX e conector de saída" em [testar o fluxo de emails com o analisador de conectividade remota](https://go.microsoft.com/fwlink/?LinkId=506784). 
  
Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:
  
- No Analisador de Conectividade Remota, clique na guia **Office 365** e execute o teste **Email SMTP de Entrada** localizado em **Testes de Email da Internet**.
    
- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.
    
- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos comum: uma configuração híbrida com caixas de correio locais e na nuvem

Se você tiver caixas de correio do Exchange no local e uma ou mais caixas de correio na nuvem no Exchange Online, você tem uma configuração *híbrida* . Em uma configuração híbrida, recursos como compartilhamento de calendário de disponibilidade e roteamento de email funcionam juntos em seus ambientes locais e em nuvem. Você pode ter uma configuração híbrida no lugar enquanto faz a transição de caixas de correio para o Exchange Online. Um ambiente híbrido é configurado de forma diferente da proteção autônoma do EOP. 
  
Você pode escolher um cenário híbrido para aproveitar o email baseado em nuvem para a maioria dos seus funcionários. Você pode fazer isso enquanto também hospeda algumas caixas de correio no local; por exemplo, para seu departamento jurídico. 
  
Uma configuração híbrida pode ser complexa, mas tem vários benefícios. Para saber mais sobre como configurar cenários híbridos com o Exchange, confira [configurando recursos de implantação híbrida do Exchange com o Office 365 operado pela 21vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).
  

