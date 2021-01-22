---
title: Configurar pilares do Microsoft 365 Defender para o laboratório de avaliação ou ambiente piloto
description: Configure os pilares do Microsoft 365 Defender, como o Microsoft Defender para Office 365, o Microsoft Defender for Identity, o Microsoft Cloud App Security e o Microsoft Defender para Ponto de Extremidade, para seu laboratório de avaliação ou ambiente piloto.
keywords: configurar a avaliação da Proteção contra Ameaças da Microsoft, a configuração de avaliação da Proteção contra Ameaças da Microsoft, configurar o projeto piloto da Proteção contra Ameaças da Microsoft, configurar pilares da Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932233"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar pilares do Microsoft 365 Defender para seu laboratório de avaliação ou ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Criar um laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender e implantá-lo é um processo de três fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Preparar](prepare-mtpeval.md) |[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: Configurar](setup-mtpeval.md) |![Fase 3: Integração](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Integração | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Voltar ao manual piloto](mtp-pilot.md) |
|--|--|--|--|
|| |*Você está aqui!* | |

Você está atualmente na fase de configuração.

A preparação é fundamental para qualquer implantação bem-sucedida. Neste artigo, você será orientado sobre os pontos que você precisará considerar ao se preparar para implantar o Microsoft Defender para o Ponto de Extremidade.


## <a name="microsoft-365-defender-pillars"></a>Pilares do Microsoft 365 Defender
O Microsoft 365 Defender consiste em quatro pilares. Embora um pilar já possa agregar valor à segurança da sua organização de rede, a habilitação dos quatro pilares do Microsoft 365 Defender dará mais valor à sua organização.

![Imagem of_Microsoft solução do 365 Defender para usuários, Microsoft Defender for Identity, para pontos de extremidade do Microsoft Defender para Ponto de Extremidade, para aplicativos em nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Esta seção orientará você a configurar:
-   Obter o Microsoft Defender para Office 365
-   Microsoft Defender para Identidade? 
-   Microsoft Cloud App Security
-   Microsoft Defender para Ponto de Extremidade


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar o Microsoft Defender para Office 365

>[!NOTE]
>Ignore esta etapa se você já tiver habilitado o Defender para Office 365. 

Há um Módulo do PowerShell chamado *ORCA (Advanced Threat Protection Recommended Configuration Analyzer) do Office 365* que ajuda a determinar algumas dessas configurações. Quando executado como administrador em seu locatário, get-ORCAReport ajudará a gerar uma avaliação das configurações de higienização de mensagens, anti-spam e anti-phishing. Você pode baixar esse módulo de https://www.powershellgallery.com/packages/ORCA/ . 

1. Navegue até a Política de Gerenciamento de Ameaças do [Centro de Conformidade e Segurança & Office 365.](https://protection.office.com/homepage)  >    >  

   ![Imagem of_Office política de gerenciamento de ameaças do Centro de Conformidade & Segurança do 365](../../media/mtp-eval-32.png)
 
2. Clique **em Anti-phishing,** selecione **Criar** e preencher o nome e a descrição da política. Clique em **Avançar**.

   ![Imagem of_Office política anti-phishing do Centro de Conformidade e Segurança & do 365 365 onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite sua política anti-phishing avançada no Microsoft Defender para Office 365. Alterar **o limite de phishing avançado** para **2 - agressivo.**

3. Clique no menu **suspenso Adicionar** uma condição e selecione seu(s) domínio(s) como domínio do destinatário. Clique em **Avançar**.

   ![Imagem of_Office política anti-phishing do Centro de Conformidade e Segurança & do 365 365, onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. Revise suas configurações. Clique **em Criar esta política** para confirmar. 

   ![Imagem of_Office política anti-phishing do Centro de Conformidade e Segurança & do 365 365, onde você pode revisar suas configurações e clicar no botão criar esta política](../../media/mtp-eval-35.png)
 
5. Selecione **Anexos Seguros e** a opção Ativar **ATP para SharePoint, OneDrive e Microsoft Teams.**

   ![Imagem of_Office do Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio do destinatário aos seus domínios. Clique em **Salvar**.

   ![Imagem of_Office do Centro de Conformidade e Segurança & do 365 365, onde você pode criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. Em seguida, selecione a **política de Links** seguros e clique no ícone de lápis para editar a política padrão.

8. Certifique-se de que **a opção Não rastrear quando os** usuários clicam em links seguros não está selecionada, enquanto o restante das opções está selecionado. Consulte [as configurações de Links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obter detalhes. Clique em **Salvar**. 

   ![Imagem of_Office página do Centro de Conformidade e Segurança do 365 & 365, que mostra que a opção Não rastrear quando os usuários clicam em segurança não está selecionada](../../media/mtp-eval-38.png)

9. Em seguida, **selecione a política anti-malware,** selecione o padrão e escolha o ícone de lápis.

10. Clique **em Configurações e** selecione Sim e use o texto de notificação **padrão** para habilitar a Resposta de Detecção **de Malware.** Ativar o **Filtro de Tipos de Anexos** Comuns. Clique em **Salvar**.

    ![Imagem of_Office página do Centro de Conformidade e Segurança & do 365 365, que mostra que a resposta de detecção de malware está ificada com a notificação padrão e o filtro de tipos de anexo comuns está ligado](../../media/mtp-eval-39.png)
  
11. Navegue até a pesquisa de log de Auditoria de Pesquisa do Centro de Conformidade e Segurança & Office [365](https://protection.office.com/homepage)e a ligue  >    >   a Auditoria.

    ![Imagem of_Office do Centro de Conformidade e Segurança & do 365 365, onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. Integre o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade. Navegue até o Centro de Gerenciamento de Ameaças do & Centro de Conformidade e Segurança do [Office 365](https://protection.office.com/homepage)e selecione Microsoft Defender para Configurações de Ponto de Extremidade no canto superior direito  >    >    da tela. Na caixa de diálogo Conexão do Defender para Ponto de Extremidade, a turn on **Connect to Microsoft Defender for Endpoint**.

    ![Imagem of_Office do Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a conexão do Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar o Microsoft Defender para Identidade

>[!NOTE]
>Ignore esta etapa se você já tiver habilitado o Microsoft Defender para Identidade

1. Navegue até a Central de Segurança do [Microsoft 365](https://security.microsoft.com/info) > selecione **Mais Recursos do** Microsoft Defender para  >  **Identidade.**

   ![Imagem of_Microsoft da Central de Segurança do 365 onde há uma opção para abrir o Microsoft Defender para Identidade](../../media/mtp-eval-42.png)

2. Clique **em Criar** para iniciar o assistente do Microsoft Defender para Identidade. 

   ![Image of_Microsoft Defender for Identity wizard page where you should click Create button](../../media/mtp-eval-43.png)

3. Escolha **Fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory.**  

   ![Image of_Microsoft Defender for Identity welcome page](../../media/mtp-eval-44.png)

4. Insira suas credenciais locais do Active Directory. Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.

   ![Image of_Microsoft Defender for Identity Directory services page where you should put your credentials](../../media/mtp-eval-45.png)

5. Em seguida, escolha **Baixar a Instalação do Sensor** e transferir o arquivo para o controlador de domínio.

   ![Image of_Microsoft Defender for Identity page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)

6. Execute o Microsoft Defender para a Instalação do Sensor de Identidade e comece a seguir o assistente.

   ![Image of_Microsoft Defender for Identity page where you should click next to follow the Microsoft Defender for Identity sensor wizard](../../media/mtp-eval-47.png)
 
7. Clique **em Next** no tipo de implantação do sensor.

   ![Image of_Microsoft Defender for Identity page where you should click next to go to next page](../../media/mtp-eval-48.png)
 
8. Copie a tecla de acesso porque você precisa insira-a em seguida no Assistente.

   ![Imagem of_the de sensores em que você deve copiar a tecla de acesso que precisa inserir na próxima página do assistente de configuração do sensor de identidade do Microsoft Defender for Identity](../../media/mtp-eval-49.png)
 
9. Copie a tecla de acesso para o Assistente e clique em **Instalar.** 

   ![Image of_Microsoft Defender for Identity sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)

10. Parabéns, você configurou com êxito o Microsoft Defender for Identity em seu controlador de domínio.

    ![Imagem of_Microsoft conclusão da instalação do assistente do Sensor de Identidade do Defender para Identidade em que você deve clicar no botão Concluir](../../media/mtp-eval-51.png)
 
11. Na seção [Configurações do Microsoft Defender para](https://go.microsoft.com/fwlink/?linkid=2040449) Identidade, selecione **Microsoft Defender para Ponto de Extremidade **, em seguida, a alternância. Clique em **Salvar**. 

    ![Imagem of_the página de configurações do Microsoft Defender para Identidade na qual você deve ativar o Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-52.png)

>[!NOTE]
>O Windows Defender ATP foi renomeado como Microsoft Defender para Ponto de Extremidade. As alterações de marcação em todos os nossos portais estão sendo versões para consistência.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud App Security

>[!NOTE]
>Ignore esta etapa se você já tiver habilitado o Microsoft Cloud App Security. 

1. Navegue até a Central de Segurança do [Microsoft 365](https://security.microsoft.com/info)  >  **Mais recursos do** Microsoft Cloud App  >  **Security.**

   ![Imagem of_Microsoft Da Central de Segurança do 365, onde você pode ver o cartão do Aplicativo Microsoft Cloud e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. No prompt de informações para integrar o Microsoft Defender para Identidade, selecione **Habilitar o Microsoft Defender para integração de dados de identidade.**
  
   ![Image of_the information prompt to integrate Microsoft Defender for Identity where you should select the Enable Microsoft Defender for Identity data integration link](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se você não vir esse prompt, isso pode significar que a integração de dados do Microsoft Defender for Identity já foi habilitada. No entanto, se você não tiver certeza, entre em contato com o administrador de TI para confirmar. 

3. Vá para **Configurações,** a ligue o botão de alternância de integração do **Microsoft Defender para Identidade** e clique em **Salvar.** 

   ![Página of_the configurações da imagem em que você deve ativar o botão de alternância de integração do Microsoft Defender para Identidade e clicar em Salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para novas instâncias do Microsoft Defender para Identidade, essa alternância de integração é automaticamente ativado. Confirme se a integração com o Microsoft Defender for Identity foi habilitada antes de prosseguir para a próxima etapa.
 
4. Nas configurações de descoberta de nuvem, selecione **Microsoft Defender para integração** com o Ponto de Extremidade e habilita a integração. Clique em **Salvar**.

   ![Imagem of_the página do Microsoft Defender para Ponto de Extremidade em que a caixa de seleção bloquear aplicativos não selecionados no Microsoft Defender para integração com o Ponto de Extremidade está selecionada. Clique em Salvar.](../../media/mtp-eval-56.png)

5. Em Configurações de descoberta na nuvem, selecione Enriquecimento **de usuário** e habilita a integração com o Azure Active Directory.

   ![Imagem da seção de enriquecimento de usuário onde a caixa de seleção enriquecer identificadores de usuário descobertos com nomes de usuário do Azure Active Directory está marcada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar o Microsoft Defender para o Ponto de Extremidade

>[!NOTE]
>Ignore esta etapa se você já tiver habilitado o Microsoft Defender para Ponto de Extremidade.

1. Navegue até a Central de Segurança do [Microsoft 365](https://security.microsoft.com/info)  >  **mais recursos da** Central de Segurança do Microsoft  >  **Defender.** Clique em **Abrir**. 

   ![Imagem of_Microsoft Central de Segurança do Defender na página Central de Segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga o assistente do Microsoft Defender para Ponto de Extremidade. Clique em **Avançar**. 

   ![Imagem of_the assistente de boas-vindas da Central de Segurança do Microsoft Defender](../../media/mtp-eval-59.png)

3. Escolha com base no local de armazenamento de dados preferencial, na política de retenção de dados, no tamanho da organização e na aceitação dos recursos de visualização.

   ![Imagem of_the página para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização. Clique em próximo quando terminar de selecionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente. 

   Clique em **Avançar**. 

4. Clique **em Continuar** e ele provisiona o Microsoft Defender para o locatário do Ponto de Extremidade.

   ![Imagem of_the página solicitando que você clique no botão Continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint. Para simplificar, este guia usa o script local.

6. Clique **em Baixar pacote** e copie o script de integração para seus pontos de extremidade.

   ![Imagem of_page solicitando que você clique no botão Baixar pacote para copiar o script de integração para seu ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. No ponto de extremidade, execute o script de integração como Administrador e escolha Y. 

   ![Imagem of_the linha de comando onde você executar o script de integração e escolher Y para continuar](../../media/mtp-eval-63.png)

8. Parabéns, você integra seu primeiro ponto de extremidade.

   ![Imagem of_the comando em que você tem a confirmação de que você integra seu primeiro ponto de extremidade. Pressione qualquer tecla para continuar](../../media/mtp-eval-64.png)

9. Copie e copie o teste de detecção do assistente do Microsoft Defender para Ponto de Extremidade.

   ![Imagem of_the executar uma etapa de teste de detecção onde você deve clicar em Copiar para copiar o script de teste de detecção que você deve colar no prompt de comando](../../media/mtp-eval-65.png)

10. Copie o script do PowerShell para um prompt de comando com elevação e execute-o. 

    ![Imagem of_command prompt em que você deve copiar o script do PowerShell para um prompt de comando com elevação e execute-o](../../media/mtp-eval-66.png)

11. Selecione **Iniciar usando o Microsoft Defender para o Ponto de** Extremidade do Assistente.

    ![Imagem of_the prompt de confirmação do assistente em que você deve clicar em Iniciar usando o Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-67.png)
 
12. Visite a [Central de Segurança do Microsoft Defender.](https://securitycenter.windows.com/) Vá para **Configurações e** selecione **Recursos avançados.** 

    ![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)

13. Ativar a integração com **o Microsoft Defender para Identidade.**  

    ![Imagem of_Microsoft recursos avançados da Central de Segurança do Defender, alternância de opção do Microsoft Defender para Identidade que você precisa ativar](../../media/mtp-eval-69.png)

14. Ativar a integração com a **Inteligência contra Ameaças do Office 365.**

    ![Imagem of_Microsoft recursos avançados da Central de Segurança do Defender, alternância de opção de Inteligência contra Ameaças do Office 365 que você precisa ativar](../../media/mtp-eval-70.png)

15. Ativar a integração com **o Microsoft Cloud App Security**.

    ![Imagem of_Microsoft Recursos avançados da Central de Segurança do Defender, opção de alternância do Microsoft Cloud App Security que você precisa ativar](../../media/mtp-eval-71.png)

16. Role para baixo e **clique em Salvar preferências** para confirmar as novas integrações.

    ![Image of_Save preferences button that you need to click](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar o serviço Microsoft 365 Defender

>[!NOTE]
>A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos do Microsoft 365 Defender para todos os locatários qualificados. Confira este [artigo da Microsoft Tech Community sobre a qualificação de licença](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obter detalhes. 


Vá para [a Central de Segurança do Microsoft 365.](https://security.microsoft.com/homepage) Navegue **até Configurações** e selecione **Microsoft 365 Defender.**

![Imagem of_Microsoft de opção do 365 Defender na página configurações da Central de Segurança do Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obter uma orientação mais abrangente, consulte [Ativar o Microsoft 365 Defender.](mtp-enable.md) 

Parabéns! Você acabou de criar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender! Agora você pode se familiarizar com a interface do usuário do Microsoft 365 Defender! Veja o que você pode aprender com o seguinte guia interativo do Microsoft 365 Defender e saiba como usar cada painel para suas tarefas diárias de operação de segurança.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Em seguida, você pode simular um ataque e ver como os recursos entre produtos detectam, criam alertas e respondem automaticamente a um ataque sem arquivo em um ponto de extremidade.

## <a name="next-step"></a>Próxima etapa
|[Fase de simulação de ataque](mtp-pilot-simulate.md) | Execute a simulação de ataque para seu ambiente piloto do Microsoft 365 Defender.
|:-------|:-----|
