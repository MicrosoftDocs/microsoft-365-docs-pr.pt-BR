---
title: Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
description: Acessar o centro de segurança do Microsoft 365 e configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection
keywords: Configuração de avaliação do Microsoft Threat Protection, experimente a proteção contra ameaças da Microsoft, configuração do laboratório de avaliação de proteção contra ameaças da Microsoft
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049610"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft 

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft 


Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Prepare seu laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/>Fase 1: preparar</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/>Fase 2: configuração</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configure cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade" />
      <br/>Fase 3: configurar o & integrado</a><br>
</td>


  </tr>
</table>

Você está atualmente na fase de configuração. Execute as etapas iniciais para acessar o centro de segurança do Microsoft 365 e configure seu ambiente de laboratório de avaliação.

Inscreva-se para uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *. onmicrosoft.com* que você pode usar para se inscrever na sua licença do Microsoft 365 e5. 

>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.

Nesta fase, você será orientado a:
- Criar um locatário de avaliação do Office 365 e5
- Habilitar a assinatura de avaliação do Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Criar um locatário de avaliação do Office 365 e5
>[!NOTE]
>Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.

1. Vá para o [portal de produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita**.
![Of_page de imagem](../../media/mtp-eval-9.png) <br>
  
2. Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo). Clique em **configurar conta**.
![Of_page de imagem](../../media/mtp-eval-10.png) <br> 

3. Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.  
<br>![Of_page de imagem](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>O país ou a região definida aqui determina a região do Data Center em que o Office 365 será hospedado.
  
4. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Clique em **enviar código de verificação**. 
![Of_page de imagem](../../media/mtp-eval-12.png) <br>

5. Defina o nome de domínio personalizado para o seu locatário e clique em **Avançar**.
<br>![Of_page de imagem](../../media/mtp-eval-13.png) <br>
 
6. Configure a primeira identidade que será um administrador global do locatário. Insira o **nome** e a **senha**. Clique em **inscrever-se**.
![Of_page de imagem](../../media/mtp-eval-14.png) <br>
c
7. Clique em **ir para configuração** para concluir o provisionamento do locatário de avaliação do Office 365 e5.
<br>![Of_page de imagem](../../media/mtp-eval-15.png) <br>

8. Conecte seu domínio corporativo ao locatário do Office 365. Opcion Escolha **conectar um domínio que você já possui** e digite o nome do seu domínio. Clique em **Avançar**.
<br>![Of_page de imagem](../../media/mtp-eval-16.png) <br>
 
9. Será necessário adicionar um registro TXT ou MX para validar a propriedade do domínio. Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **verificar**.
<br>![Of_page de imagem](../../media/mtp-eval-17.png) <br>
 
10. Opcion Criar mais contas de usuário para o locatário. Você pode ignorar essa etapa clicando em **Avançar**.
![Of_page de imagem](../../media/mtp-eval-18.png) <br>
 
11. Opcion Baixar aplicativos do Office. Clique em **Avançar** para ignorar esta etapa. 
<br>![Of_page de imagem](../../media/mtp-eval-19.png) <br>

12. Opcion Migrar mensagens de email. Novamente, você pode ignorar esta etapa.
<br>![Of_page de imagem](../../media/mtp-eval-20.png) <br>
 
13. Escolha serviços online. Selecione **Exchange** e clique em **Avançar**. 
<br>![Of_page de imagem](../../media/mtp-eval-21.png) <br>

14. Adicione registros MX, CNAME e TXT ao seu domínio. Quando concluído, selecione **verificar**.
<br>![Of_page de imagem](../../media/mtp-eval-22.png) <br>
 
15. Parabéns, você concluiu o provisionamento do seu locatário do Office 365.
<br>![Of_page de imagem](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar a assinatura de avaliação do Microsoft 365

>[!NOTE]
>Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por mês. Consulte [tentar ou comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.

1. No [centro de administração do Microsoft 365](https://admin.microsoft.com/), clique em **cobrança** e navegue até **serviços de compra**.

2. Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita**. 
![Of_page de imagem](../../media/mtp-eval-24.png) <br>

3. Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada. Depois de decidir, insira o número de telefone, selecione o **texto me** ou **telefonar para mim** , dependendo da seleção.
![Of_page de imagem](../../media/mtp-eval-25.png) <br>
 
4. Insira o código de verificação e clique em **iniciar sua avaliação gratuita**. 
<br>![Of_page de imagem](../../media/mtp-eval-26.png) <br>

5. Clique em **tentar agora** para confirmar sua avaliação do Microsoft 365 e5.
<br>![Of_page de imagem](../../media/mtp-eval-27.png) <br>
 
6. Vá para o **Centro** > **Users** > de administração do Microsoft 365 usuários**ativos**. Selecione sua conta de usuário, selecione **gerenciar licenças de produto**e troque a licença do Office 365 E5 para a **Microsoft 365 E5**. Clique em **Salvar**.
![Of_page de imagem](../../media/mtp-eval-28.png) <br>
 
7. Selecione a conta de administrador global novamente e, em seguida, clique em **gerenciar nome de usuário**.
<br>![Of_page de imagem](../../media/mtp-eval-29.png) <br>

8. Opcion Altere o domínio de *onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores. Clique em **Salvar alterações**.
<br>![Of_page de imagem](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Próxima etapa
||| |:-------|:-----| config-onboard. png) <br>[Fase 3: configurar & integrada](config-mtpeval.md) | Configure cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade.
