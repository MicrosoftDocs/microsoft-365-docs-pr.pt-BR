---
title: Configurar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender
description: Acessar a Central de Segurança do Microsoft 365 e configurar seu ambiente de laboratório de avaliação do Microsoft 365 Defender
keywords: Configuração de avaliação da Proteção contra Ameaças da Microsoft, configuração piloto da Proteção contra Ameaças da Microsoft, experimentar a Proteção contra Ameaças da Microsoft, configuração do laboratório de avaliação da Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932977"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Configurar seu ambiente de laboratório de avaliação do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender 


Criar um laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender e implantá-lo é um processo de três fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Preparar](prepare-mtpeval.md) |![Fase 2: Configurar](../../media/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Integração](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: Integração](config-mtpeval.md) | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Voltar ao manual piloto](mtp-pilot.md) |
|--|--|--|--|
||*Você está aqui!*  | | |


Você está atualmente na fase de configuração. Tome as etapas iniciais para acessar a Central de Segurança do Microsoft 365 e, em seguida, configurar seu laboratório de avaliação ou ambiente piloto.

Inscreva-se em uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *.onmicrosoft.com* que você pode usar para se inscrever em sua licença do Microsoft 365 E5. 

>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de avaliação ou criação de locatário piloto do Office 365 E5.

Nesta fase, você será orientado a:
- Criar um locatário de avaliação do Office 365 E5
- Habilitar a assinatura de avaliação do Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Criar um locatário de avaliação do Office 365 E5
>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, ignore as etapas de criação do locatário de avaliação do Office 365 E5.

1. Vá para o [portal do produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **Avaliação gratuita.**

   ![Imagem of_Office de avaliação gratuita do 365 E5](../../media/mtp-eval-9.png)
  
2. Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo). Clique **em Configurar conta.**

   ![Imagem of_Office de configuração de registro de avaliação do 365 E5](../../media/mtp-eval-10.png)

3. Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.  

   ![Imagem of_Office de configuração de registro de avaliação do 365 E5 solicitando nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > O país ou região definida aqui determina a região do data center que seu Office 365 será hospedado.
  
4. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Clique **em Enviar Código de Verificação.** 

   ![Imagem of_Office de configuração de registro de avaliação do 365 E5 solicitando a preferência de verificação](../../media/mtp-eval-12.png)

5. De definir o nome de domínio personalizado para seu locatário e clique em **Próximo.**

   ![Imagem of_Office de configuração de registro de avaliação do 365 E5 onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)
 
6. Configurar a primeira identidade, que será um Administrador Global para o locatário. Preencha Nome **e** **Senha.** Clique **em Inscrever-se.**

   ![Imagem of_Office de configuração de registro de avaliação do 365 E5 onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)

7. Clique **em Ir para a Instalação** para concluir o provisionamento de locatário de avaliação do Office 365 E5.

   ![Imagem da página de configuração de registro de avaliação do Office 365 E5 solicitando clicar no botão Configurar](../../media/mtp-eval-15.png)

8. Conecte seu domínio corporativo ao locatário do Office 365. [Opcional] Escolha **Conectar um domínio que você já possui** e digite seu nome de domínio. Clique em **Avançar**.

   ![Imagem of_Office da Instalação do 365 E5 na qual você deve personalizar sua inscrição e email](../../media/mtp-eval-16.png)
 
9. Adicione um registro TXT ou MX para validar a propriedade do domínio. Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **Verificar.**

   ![Imagem of_Office de instalação do 365 E5 em que você deve adicionar um TXT de registro MX para verificar seu domínio](../../media/mtp-eval-17.png)
 
10. [Opcional] Crie mais contas de usuário para seu locatário. You can skip this step by clicking **Next**.

    ![Imagem of_Office de instalação do 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)
 
11. [Opcional] Baixe os aplicativos do Office. Clique **em Next** para ignorar esta etapa. 

    ![Imagem of_Office 365 E5 onde você pode instalar seus aplicativos do Office](../../media/mtp-eval-19.png)

12. [Opcional] Migrar mensagens de email. Novamente, você pode ignorar esta etapa.

    ![Imagem of_Office 365 E5 onde você pode definir se deve migrar mensagens de email ou não](../../media/mtp-eval-20.png)
 
13. Escolha serviços online. Selecione **Exchange** e clique em **Próximo**. 

    ![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)

14. Adicione registros MX, CNAME e TXT ao seu domínio. Quando concluir, selecione **Verificar**.

    ![Imagem of_Office 365 E5 aqui, você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)
 
15. Parabéns, você concluiu o provisionamento do seu locatário do Office 365.

    ![Imagem of_Office de confirmação de conclusão da instalação do 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar a assinatura de avaliação do Microsoft 365

>[!NOTE]
>Inscrever-se para uma avaliação oferece 25 licenças de usuário para usar por um mês. Confira [Experimentar ou Comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.

1. No Centro de Administração do [Microsoft 365,](https://admin.microsoft.com/)clique **em Cobrança** e navegue até **Comprar serviços.**

2. Selecione **o Microsoft 365 E5 e clique em** Iniciar **avaliação gratuita.** 

   ![Imagem of_Microsoft de avaliação gratuita do 365 E5](../../media/mtp-eval-24.png)

3. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Depois de decidir, digite o número de telefone, selecione **Texto-me** ou **Ligue-me** dependendo da sua seleção.

   ![Imagem of_Microsoft página iniciar avaliação gratuita do 365 E5 solicitando detalhes do contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)
 
4. Insira o código de verificação e clique **em Iniciar sua avaliação gratuita.**

   ![Imagem of_Microsoft página iniciar avaliação gratuita do 365 E5 onde você pode preencher o código de verificação do sistema enviado para provar que você não é um robô](../../media/mtp-eval-26.png)

5. Clique **em Experimentar agora** para confirmar sua avaliação do Microsoft 365 E5.

   ![Imagem of_Microsoft página iniciar avaliação gratuita do 365 E5 onde você deve relógio o botão Experimentar agora para iniciar](../../media/mtp-eval-27.png)
 
6. Vá para usuários ativos do Centro de Administração **do Microsoft 365.**  >    >   Selecione sua conta de usuário, selecione **Gerenciar licenças** de produto e, em seguida, troque a licença do Office 365 E5 para o **Microsoft 365 E5.** Clique em **Salvar**.

   ![Imagem of_Microsoft página do Centro de administração do 365 onde você pode selecionar a licença do Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. Selecione a conta de administrador global novamente e clique em Gerenciar nome **de usuário.**

   ![Imagem of_Microsoft página do Centro de Administração do 365 onde você pode selecionar Conta e Gerenciar nome de usuário](../../media/mtp-eval-29.png)

8. [Opcional] Altere o domínio *de onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores. Clique em **Salvar alterações**.

   ![Imagem of_Microsoft página do Centro de administração do 365 onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Próxima etapa
|[Fase 3: Configurar o & Onboard](config-mtpeval.md) | Configure cada pilar do Microsoft 365 Defender para seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender e a integração de seus pontos de extremidade.
|:-------|:-----|
