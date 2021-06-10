---
title: Configurar seu laboratório de avaliação Microsoft 365 Defender ou o ambiente piloto
description: O Microsoft 365 de Segurança do Access configura seu ambiente de laboratório de avaliação do Microsoft 365 Defender
keywords: Microsoft 365 Configuração de avaliação do Defender, Microsoft 365 configuração piloto do Defender, Microsoft 365 Defender, Microsoft 365 de laboratório de avaliação do Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935420"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Configurar seu ambiente de laboratório de Microsoft 365 de avaliação do Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender 


Criar um Microsoft 365 de avaliação do Defender ou um ambiente piloto e implantá-lo é um processo de três fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: Preparar](prepare-m365d-eval.md) |![Fase 2: Configurar](../../media/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Integrar](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: Integrar](config-m365d-eval.md) | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Voltar ao playbook piloto](m365d-pilot.md) |
|--|--|--|--|
||*Você está aqui!*  | | |


No momento, você está na fase de configuração. Tome as etapas iniciais para acessar Microsoft 365 Centro de Segurança e, em seguida, configurar seu laboratório de avaliação ou ambiente piloto.

Inscreva-se em uma assinatura Office 365 ou Azure Active Directory para gerar um *locatário .onmicrosoft.com* que você pode usar para se inscrever na sua licença Microsoft 365 E5 de usuário. 

>[!NOTE]
>Se você já tiver uma assinatura Office 365 ou Azure Active Directory existente, poderá ignorar as etapas de avaliação Office 365 E5 ou criação de locatário piloto.

Nesta fase, você será guiado para:
- Criar um Office 365 de avaliação do E5
- Habilitar Microsoft 365 assinatura de avaliação


## <a name="create-an-office-365-e5-trial-tenant"></a>Criar um Office 365 de avaliação do E5
>[!NOTE]
>Se você já tiver uma assinatura de Office 365 ou Azure Active Directory existente, poderá ignorar as etapas de criação de locatários de avaliação Office 365 E5.

1. Vá para o portal [de produtos Office 365 E5 e](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) selecione **avaliação gratuita.**

   ![Página de avaliação gratuita of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo). Clique **em Configurar conta**.

   ![Página de configuração de registro de avaliação do Of_Office 365 E5](../../media/mtp-eval-10.png)

3. Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.  

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 solicitando o nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > O país ou a região que você definir aqui determina a região do data center que seu Office 365 será hospedado.
  
4. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Clique **em Enviar Código de Verificação**. 

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 solicitando preferência de verificação](../../media/mtp-eval-12.png)

5. De definir o nome de domínio personalizado para seu locatário e clique em **Próximo**.

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)
 
6. Configurar a primeira identidade, que será um Administrador Global para o locatário. Preencha Nome **e** **Senha**. Clique **em Inscrever-se**.

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)

7. Clique **em Ir para a Instalação** para concluir o provisionamento Office 365 locatário de avaliação do E5.

   ![Imagem da Office 365 de configuração de registro de avaliação do E5 solicitando que clique em Ir botão Configurar](../../media/mtp-eval-15.png)

8. Conexão seu domínio corporativo para o Office 365 locatário. [Opcional] Escolha **Conexão um domínio que você já possui** e digite seu nome de domínio. Clique em **Avançar**.

   ![Imagem of_Office página de Instalação do 365 E5 em que você deve personalizar sua assinatura e email](../../media/mtp-eval-16.png)
 
9. Adicione um registro TXT ou MX para validar a propriedade do domínio. Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **Verificar**.

   ![Página of_Office de configuração do 365 E5 em que você deve adicionar um TXT de registro MX para verificar seu domínio](../../media/mtp-eval-17.png)
 
10. [Opcional] Crie mais contas de usuário para seu locatário. Você pode ignorar esta etapa clicando em **Next**.

    ![Página of_Office de configuração do 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)
 
11. [Opcional] Baixe Office aplicativos. Clique **em Próximo** para ignorar esta etapa. 

    ![Página of_Office 365 E5 em que você pode instalar seus aplicativos Office aplicativos](../../media/mtp-eval-19.png)

12. [Opcional] Migrar mensagens de email. Novamente, você pode ignorar esta etapa.

    ![Imagem of_Office 365 E5 onde você pode definir se deve migrar mensagens de email ou não](../../media/mtp-eval-20.png)
 
13. Escolha serviços online. Selecione **Exchange** e clique em **Próximo**. 

    ![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)

14. Adicione registros MX, CNAME e TXT ao seu domínio. Quando concluído, selecione **Verificar**.

    ![Imagem of_Office 365 E5 aqui você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)
 
15. Parabéns, você concluiu o provisionamento do seu Office 365 locatário.

    ![Página de confirmação de conclusão da instalação of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar Microsoft 365 assinatura de avaliação

>[!NOTE]
>Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por um mês. Consulte [Try or Buy an M365 subscription para](../../commerce/try-or-buy-microsoft-365.md) obter detalhes.

1. No [Microsoft 365 Admin Center,](https://admin.microsoft.com/)clique **em Cobrança** e navegue até Serviços **de Compra.**

2. Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita.** 

   ![Página de avaliação gratuita do Of_Microsoft 365 E5](../../media/mtp-eval-24.png)

3. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Depois de decidir, digite o número de telefone, selecione **Texto-me** ou **Chame-me** dependendo de sua seleção.

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita solicitando detalhes de contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)
 
4. Insira o código de verificação e clique em **Iniciar sua avaliação gratuita.**

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita onde você pode preencher o código de verificação enviado pelo sistema para provar que não é um robô](../../media/mtp-eval-26.png)

5. Clique **em Tentar agora** para confirmar sua Microsoft 365 E5 avaliação.

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita onde você deve relógio o botão Tentar agora para iniciar](../../media/mtp-eval-27.png)
 
6. Vá para o centro **de administração Microsoft 365**  >  **Usuários**  >  **ativos**. Selecione sua conta de usuário, selecione **Gerenciar licenças de** produto e, em seguida, troque a licença de Office 365 E5 para **Microsoft 365 E5**. Clique em **Salvar**.

   ![Página do Centro de Administração do Of_Microsoft 365 onde você pode selecionar Microsoft 365 E5 licença](../../media/mtp-eval-28.png)
 
7. Selecione a conta de administrador global novamente e clique em Gerenciar nome **de usuário**.

   ![Página of_Microsoft centro de administração do 365 onde você pode selecionar Conta e gerenciar nome de usuário](../../media/mtp-eval-29.png)

8. [Opcional] Altere o domínio *de onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores. Clique em **Salvar alterações**.

   ![Página of_Microsoft centro de administração do 365 onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Próxima etapa
|[Fase 3: Configurar o & Onboard](config-m365d-eval.md) | Configure cada pilar Microsoft 365 Defender para seu laboratório de avaliação do Microsoft 365 Defender ou ambiente piloto e aborde seus pontos de extremidade.
|:-------|:-----|
