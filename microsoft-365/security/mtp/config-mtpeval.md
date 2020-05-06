---
title: Configurar os pilares de proteção contra ameaças da Microsoft para o ambiente de laboratório de avaliação
description: Configurar os pilares de proteção contra ameaças da Microsoft, o Office 365 ATP, o Azure ATP, o Microsoft Cloud app Security e o Microsoft defender ATP para seu ambiente de laboratório de avaliação
keywords: configurar a avaliação de proteção contra ameaças da Microsoft, configuração de avaliação de proteção contra ameaças da Microsoft, configurar os pilares de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049504"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a>Configurar os pilares de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/>Fase 1: preparar</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/>Fase 2: configuração</a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e pontos de extremidade integrados" />
      <br/>Fase 3: configurar o & integrado</a><br>
</td>


  </tr>
</table>

No momento, você está na fase de configuração.


A preparação é fundamental para qualquer implantação bem-sucedida. Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pilares de proteção contra ameaças da Microsoft
A proteção contra ameaças da Microsoft consiste em quatro pilares. Embora um pilar já possa fornecer um valor para a segurança da sua organização de rede, a habilitação dos quatro pilares de proteção contra ameaças da Microsoft dará à sua organização o mais valor.

![Of_page de imagem](../../media/mtp-eval-31.png) <br>

Esta seção orientará você a configurar:
-   Proteção Avançada contra Ameaças do Office 365
-   Proteção Avançada contra Ameaças do Azure 
-   Microsoft Cloud App Security
-   Proteção avançada contra ameaças do Microsoft Defender


## <a name="configure-office-365-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Office 365
>[!NOTE]
>Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Office 365. 

Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações. Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens. Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/. 

1. Navegue até a**política**de**Gerenciamento** > de ameaças do centro > de [conformidade & segurança do Office 365](https://protection.office.com/homepage).
![Of_page de imagem](../../media/mtp-eval-32.png) <br>
 
2. Clique em **anti-phishing ATP**, selecione **criar** e preencha o nome e a descrição da política. Clique em **Avançar**.
![Of_page de imagem](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Edite a política de anti-phishing avançada da ATP. Altere o **limite de phishing avançado** para **2-agressivo**.
<br>

3. Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário. Clique em **Avançar**.
![Of_page de imagem](../../media/mtp-eval-34.png) <br>
 
4. Revise suas configurações. Clique em **criar esta política** para confirmar. 
![Of_page de imagem](../../media/mtp-eval-35.png) <br>
 
5. Selecione **anexos seguros de ATP** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .  
![Of_page de imagem](../../media/mtp-eval-36.png) <br>

6. Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios. Clique em **Salvar**.
![Of_page de imagem](../../media/mtp-eval-37.png) <br>
 
7. Em seguida, selecione a política de **links seguros de ATP** e clique no ícone de lápis para editar a política padrão.

8. Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado. Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) para obter detalhes. Clique em **Salvar**. 
![Of_page de imagem](../../media/mtp-eval-38.png) <br>

9. Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.

10. Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**. Ativar o **filtro de tipos de anexo comuns** . Clique em **Salvar**.
<br>![Of_page de imagem](../../media/mtp-eval-39.png) <br>
  
11. Navegue até [Office 365 Security & centro](https://protection.office.com/homepage) > de conformidade**pesquisa** > **log de auditoria** pesquisa e ative a auditoria.  
![Of_page de imagem](../../media/mtp-eval-40.png) <br>

12. Integrar o Office 365 ATP com o Microsoft defender ATP. Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)de > **Gerenciamento** > **de** ameaças do centro de conformidade e selecione **configurações do WDATP** no canto superior direito da tela. Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.
![Of_page de imagem](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Azure
>[!NOTE]
>Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Azure


1. Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos** > **proteção avançada contra ameaças do Azure**.
![Of_page de imagem](../../media/mtp-eval-42.png) <br>

2. Clique em **criar** para iniciar o assistente de proteção avançada contra ameaças do Azure. 
<br>![Of_page de imagem](../../media/mtp-eval-43.png) <br>

3. Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.  
![Of_page de imagem](../../media/mtp-eval-44.png) <br>

4. Insira suas credenciais locais do Active Directory. Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.
![Of_page de imagem](../../media/mtp-eval-45.png) <br>

5. Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio. 
![Of_page de imagem](../../media/mtp-eval-46.png) <br>

6. Execute a configuração do sensor ATP do Azure e comece seguindo o assistente.
<br>![Of_page de imagem](../../media/mtp-eval-47.png) <br>
 
7. Clique em **Avançar** no tipo de implantação do sensor.
<br>![Of_page de imagem](../../media/mtp-eval-48.png) <br>
 
8. Copie a chave de acesso, pois será necessário inseri-la em seguida no assistente.
![Of_page de imagem](../../media/mtp-eval-49.png) <br>
 
9. Copie a chave de acesso no assistente e clique em **instalar**. 
<br>![Of_page de imagem](../../media/mtp-eval-50.png) <br>

10. Parabéns, você configurou com êxito a proteção avançada contra ameaças do Azure no seu controlador de domínio.
![Of_page de imagem](../../media/mtp-eval-51.png) <br>
 
11. Na seção Configurações de [ATP do Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione **Windows Defender ATP**e ative a opção de ativar. Clique em **Salvar**. 
![Of_page de imagem](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>O Windows Defender ATP foi remarcado como Microsoft defender ATP. As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud app Security
>[!NOTE]
>Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security. 

1. Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info) > **mais recursos** > **Microsoft Cloud app Security**.
![Of_page de imagem](../../media/mtp-eval-53.png) <br>

2. No prompt de informações para integrar o Azure ATP, selecione **habilitar a integração de dados ATP do Azure**. 
<br>![Of_page de imagem](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Se você não vir esse prompt, pode significar que sua integração de dados ATP do Azure já foi habilitada. No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar. 

3. Vá para **configurações**, ative a ativação da **integração do Azure ATP** e clique em **salvar**. 
![Of_page de imagem](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>Para novas instâncias ATP do Azure, esta integração alternada é automaticamente ativada. Confirme se a sua integração do Azure ATP foi habilitada antes de prosseguir para a próxima etapa.
 
4. Nas configurações de descoberta de nuvem, selecione **integração do Microsoft defender ATP**e habilite a integração. Clique em **Salvar**.
![Of_page de imagem](../../media/mtp-eval-56.png) <br>

5. Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário**e habilite a integração com o Azure Active Directory.
![Of_page de imagem](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Microsoft defender
>[!NOTE]
>Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Microsoft defender.

1. Navegue até a central de [segurança](https://security.microsoft.com/info) > da Microsoft 365**mais recursos** > **central de segurança do Microsoft defender**. Clique em **Abrir**. 
<br>![Of_page de imagem](../../media/mtp-eval-58.png) <br>
 
2. Siga o assistente de proteção avançada contra ameaças do Microsoft defender. Clique em **Avançar**. 
<br>![Of_page de imagem](../../media/mtp-eval-59.png) <br>

3. Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização. 
<br>![Of_page de imagem](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente. 
<br>

Clique em **Avançar**. 

4. Clique em **continuar** e ele provisionrá o locatário do Microsoft defender ATP.
<br>![Of_page de imagem](../../media/mtp-eval-61.png) <br>

5. Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender ATP. Para simplificar, este guia usa o script local.

6. Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.  
<br>![Of_page de imagem](../../media/mtp-eval-62.png) <br>

7. No ponto de extremidade, execute o script de integração como administrador e escolha Y.
<br>![Of_page de imagem](../../media/mtp-eval-63.png) <br>

8. Parabéns, você terá integrado seu primeiro ponto de extremidade.  
<br>![Of_page de imagem](../../media/mtp-eval-64.png) <br>

9. Copie-cole o teste de detecção do assistente do Microsoft defender ATP.
<br>![Of_page de imagem](../../media/mtp-eval-65.png) <br>

10. Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o. 
<br>![Of_page de imagem](../../media/mtp-eval-66.png) <br>

11. Selecione **começar a usar o Microsoft defender ATP** no assistente.
<br>![Of_page de imagem](../../media/mtp-eval-67.png) <br>
 
12. Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/). Vá até **configurações** e selecione **recursos avançados**. 
<br>![Of_page de imagem](../../media/mtp-eval-68.png) <br>

13. Ative a integração com a **proteção avançada contra ameaças do Azure**.  
<br>![Of_page de imagem](../../media/mtp-eval-69.png) <br>

14. Ative a integração com a **inteligência contra ameaças do Office 365**.
<br>![Of_page de imagem](../../media/mtp-eval-70.png) <br>

15. Ative a integração com **o Microsoft Cloud app Security**.
<br>![Of_page de imagem](../../media/mtp-eval-71.png) <br>

16. Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.
<br>![Of_page de imagem](../../media/mtp-eval-72.png) <br>

## <a name="next-steps"></a>Próximas etapas
[Ative a proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) e [gere um alerta de teste](generate-test-alert.md).
