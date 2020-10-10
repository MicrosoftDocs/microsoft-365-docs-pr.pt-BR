---
title: Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto
description: Acessar o centro de segurança do Microsoft 365 e configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
keywords: Configuração de avaliação do Microsoft Threat Protection, configuração do piloto do Microsoft Threat Protection, experimente proteção contra ameaças da Microsoft, configuração do laboratório de avaliação de proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 53ff0842e73e275bf4a8fa8b18c1d08ad70a64ec
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418128"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft 


A criação de um laboratório de avaliação de proteção contra ameaças da Microsoft ou ambiente piloto e sua implantação é um processo de três fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar o laboratório de avaliação da proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/>Fase 1: preparar </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/>Fase 2: configuração </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
Configure cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou para o ambiente piloto e a integração dos pontos de extremidade" />
      <br/>Fase 3: configurar o & integrado </a><br>
</td>


  </tr>
</table>

Você está atualmente na fase de configuração. Execute as etapas iniciais para acessar o centro de segurança do Microsoft 365 e configure seu laboratório de avaliação ou ambiente piloto.

Inscreva-se para uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *. onmicrosoft.com* que você pode usar para se inscrever na sua licença do Microsoft 365 e5. 

>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de avaliação do Office 365 E5 ou de criação do locatário piloto.

Nesta fase, você será orientado a:
- Criar um locatário de avaliação do Office 365 e5
- Habilitar a assinatura de avaliação do Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Criar um locatário de avaliação do Office 365 e5
>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.

1. Vá para o [portal de produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita**.

   ![Página de avaliação gratuita de imagem of_Office 365 e5](../../media/mtp-eval-9.png)
  
2. Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo). Clique em **configurar conta**.

   ![Página de configuração de registro de avaliação 365 E5 de imagem of_Office](../../media/mtp-eval-10.png)

3. Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.  

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação para solicitar o nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > O país ou a região definida aqui determina a região do Data Center em que o Office 365 será hospedado.
  
4. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Clique em **enviar código de verificação**. 

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação solicitando preferência de verificação](../../media/mtp-eval-12.png)

5. Defina o nome de domínio personalizado para o seu locatário e clique em **Avançar**.

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)
 
6. Configure a primeira identidade, que será um administrador global para o locatário. Insira o **nome** e a **senha**. Clique em **inscrever-se**.

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)

7. Clique em **ir para configuração** para concluir o provisionamento do locatário de avaliação do Office 365 e5.

   ![Imagem da página de configuração do registro de avaliação do Office 365 E5 solicitando o clique no botão configuração do Go](../../media/mtp-eval-15.png)

8. Conecte seu domínio corporativo ao locatário do Office 365. Opcion Escolha **conectar um domínio que você já possui** e digite o nome do seu domínio. Clique em **Avançar**.

   ![Página de configuração de imagem of_Office 365 E5 onde você deve personalizar sua entrada e email](../../media/mtp-eval-16.png)
 
9. Adicione um registro TXT ou MX para validar a propriedade do domínio. Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **verificar**.

   ![Página de imagem of_Office 365 E5 onde você deve adicionar um TXT do registro MX para verificar seu domínio](../../media/mtp-eval-17.png)
 
10. Opcion Criar mais contas de usuário para o locatário. Você pode ignorar essa etapa clicando em **Avançar**.

    ![Página de configuração de imagem of_Office 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)
 
11. Opcion Baixar aplicativos do Office. Clique em **Avançar** para ignorar esta etapa. 

    ![Página de imagem of_Office 365 E5 onde você pode instalar seus aplicativos do Office](../../media/mtp-eval-19.png)

12. Opcion Migrar mensagens de email. Novamente, você pode ignorar esta etapa.

    ![Image of_Office 365 E5 onde você pode definir se deseja migrar mensagens de email ou não](../../media/mtp-eval-20.png)
 
13. Escolha serviços online. Selecione **Exchange** e clique em **Avançar**. 

    ![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)

14. Adicionar registros MX, CNAME e TXT ao seu domínio. Quando concluído, selecione **verificar**.

    ![Imagem of_Office 365 E5 aqui você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)
 
15. Parabéns, você concluiu o provisionamento do seu locatário do Office 365.

    ![Página de confirmação de conclusão da instalação da of_Office 365 e5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar a assinatura de avaliação do Microsoft 365

>[!NOTE]
>Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por mês. Consulte [tentar ou comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.

1. No [centro de administração do Microsoft 365](https://admin.microsoft.com/), clique em **cobrança** e navegue até **serviços de compra**.

2. Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita**. 

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita](../../media/mtp-eval-24.png)

3. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Depois de decidir, insira o número de telefone, selecione o **texto me** ou **telefonar para mim** , dependendo da seleção.

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita solicitando detalhes do contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)
 
4. Insira o código de verificação e clique em **iniciar sua avaliação gratuita**.

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você pode preencher o código de verificação o sistema enviado para provar que você não é um robô](../../media/mtp-eval-26.png)

5. Clique em **tentar agora** para confirmar sua avaliação do Microsoft 365 e5.

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você deve registrar o botão experimentar agora para iniciar](../../media/mtp-eval-27.png)
 
6. Vá para o **centro de administração do Microsoft 365**  >  **usuários**  >  **ativos**. Selecione sua conta de usuário, selecione **gerenciar licenças de produto**e troque a licença do Office 365 E5 para a **Microsoft 365 E5**. Clique em **Salvar**.

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar a licença do Microsoft 365 e5](../../media/mtp-eval-28.png)
 
7. Selecione a conta de administrador global novamente e, em seguida, clique em **gerenciar nome de usuário**.

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar Account e gerenciar username](../../media/mtp-eval-29.png)

8. Opcion Altere o domínio de *onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores. Clique em **Salvar alterações**.

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Próxima etapa
|![Fase 3: configurar o & integrado](../../media/config-onboard.png) <br>[Fase 3: configurar o & integrado](config-mtpeval.md) | Configure cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou para o ambiente piloto e integração dos pontos de extremidade.
|:-------|:-----|
