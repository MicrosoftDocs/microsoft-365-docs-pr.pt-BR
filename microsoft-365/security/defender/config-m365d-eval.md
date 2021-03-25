---
title: Configurar os pilares do Microsoft 365 Defender para o laboratório de avaliação ou o ambiente piloto
description: Configure os pilares do Microsoft 365 Defender, como o Microsoft Defender para Office 365 , o Microsoft Defender para Identidade, o Microsoft Cloud App Security e o Microsoft Defender para Ponto de Extremidade, para seu laboratório de avaliação ou ambiente piloto.
keywords: configurar a avaliação da Proteção contra Ameaças da Microsoft, a configuração de avaliação da Proteção contra Ameaças da Microsoft, configurar o projeto piloto da Proteção contra Ameaças da Microsoft, configurar os pilares da Proteção contra Ameaças da Microsoft, os pilares da Proteção contra Ameaças da Microsoft
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8bb80e032fd2eb4c618b60f4ab46829d5cf11b6d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199224"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar os pilares do Microsoft 365 Defender para seu laboratório de avaliação ou ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Criar um laboratório de avaliação do Microsoft 365 Defender ou um ambiente piloto e implantá-lo é um processo de três fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: Preparar](prepare-m365d-eval.md) |[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: Configurar](setup-m365deval.md) |![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Onboard | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Voltar ao playbook piloto](m365d-pilot.md) |
|--|--|--|--|
|| |*Você está aqui!* | |

No momento, você está na fase de configuração.

A preparação é fundamental para qualquer implantação bem-sucedida. Neste artigo, você será orientado sobre os pontos que você precisará considerar ao se preparar para implantar o Microsoft Defender para o Ponto de Extremidade.


## <a name="microsoft-365-defender-pillars"></a>Pilares do Microsoft 365 Defender
O Microsoft 365 Defender consiste em quatro pilares. Embora um pilar já possa fornecer valor para a segurança da sua organização de rede, a habilitação dos quatro pilares do Microsoft 365 Defender dará mais valor à sua organização.

![Solução do Image of_Microsoft 365 Defender para usuários, Microsoft Defender for Identity, para pontos de extremidade Microsoft Defender para Ponto de Extremidade, para aplicativos de nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Esta seção o orientará a configurar:
-   Microsoft Defender para Office 365
-   Microsoft Defender para Identidade? 
-   Microsoft Cloud App Security
-   Microsoft Defender para Ponto de Extremidade


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar o Microsoft Defender para Office 365

>[!NOTE]
>Ignore esta etapa se você já habilitar o Defender para Office 365. 

Há um Módulo do PowerShell chamado *ORCA (Advanced Threat Protection Recommended Configuration Analyzer) do Office 365* que ajuda a determinar algumas dessas configurações. Quando executado como administrador em seu locatário, get-ORCAReport ajudará a gerar uma avaliação das configurações anti-spam, anti-phish e outras configurações de higienização de mensagens. Você pode baixar esse módulo de https://www.powershellgallery.com/packages/ORCA/ . 

1. Navegue [até Office 365 Security & Política](https://protection.office.com/homepage)de gerenciamento de ameaças do Centro  >  **de**  >  **Conformidade.**

   ![Página of_Office de política de gerenciamento de ameaças do Centro de Conformidade & Segurança 365](../../media/mtp-eval-32.png)
 
2. Clique **em Anti-phishing,** selecione **Criar** e preencher o nome e a descrição da política. Clique em **Avançar**.

   ![Imagem of_Office página de política anti-phishing do Centro de Conformidade e Segurança & do 365 365 onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite sua política anti-phishing avançada no Microsoft Defender para Office 365. Alterar **o Limite Avançado de Phishing** para **2 - Agressivo**.

3. Clique no **menu suspenso Adicionar uma** condição e selecione seu domínio(s) como domínio de destinatário. Clique em **Avançar**.

   ![Página of_Office política anti-phishing do Centro de Conformidade e Segurança do 365 36 & 5 onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. Revise suas configurações. Clique **em Criar essa política** para confirmar. 

   ![Image of_Office 365 Security & Página de política anti-phishing do Centro de Conformidade onde você pode revisar suas configurações e clicar no botão criar essa política](../../media/mtp-eval-35.png)
 
5. Selecione **Anexos Seguros** e selecione a opção **Ativar ATP para SharePoint, OneDrive e Microsoft Teams.**

   ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios. Clique em **Salvar**.

   ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. Em seguida, selecione **a política Links Seguros** e clique no ícone de lápis para editar a política padrão.

8. Certifique-se de que **a opção Não rastrear quando os** usuários clicarem em links seguros não estiver selecionada, enquanto o restante das opções estiver selecionado. Consulte [Configurações de Links Seguros](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) para obter detalhes. Clique em **Salvar**. 

   ![Imagem of_Office página do Centro de Conformidade e Segurança & do 365 365 que mostra que a opção Não rastrear quando os usuários clicam em segurança não está selecionada](../../media/mtp-eval-38.png)

9. Em seguida, selecione **a política Anti-malware,** selecione o padrão e escolha o ícone de lápis.

10. Clique **em Configurações** e selecione **Sim e use o** texto de notificação padrão para habilitar a Resposta de Detecção de **Malware.** Ativar o **Filtro de Tipos de Anexo** Comum. Clique em **Salvar**.

    ![Página of_Office Centro de Conformidade e Segurança do 365 36 & 5 que mostra que a resposta de detecção de malware está ativeda com a notificação padrão e o filtro de tipos de anexo comum está ligado](../../media/mtp-eval-39.png)
  
11. Navegue [até Office 365 Security & pesquisa](https://protection.office.com/homepage)de log de Auditoria de Pesquisa do Centro de Conformidade e a adoencie a  >    >   Auditoria.

    ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. Integre o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade. Navegue [até Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat management Explorer e selecione Microsoft Defender for  >    >   **Endpoint Settings** no canto superior direito da tela. Na caixa de diálogo Conexão do Defender para Ponto de Extremidade, a ligue Conectar-se ao **Microsoft Defender para Ponto de Extremidade**.

    ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a conexão do Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar o Microsoft Defender para Identidade

>[!NOTE]
>Ignore esta etapa se você já habilitar o Microsoft Defender para Identidade

1. Navegue até o Centro de Segurança do [Microsoft 365](https://security.microsoft.com/info) > selecione **Mais Recursos** do Microsoft Defender  >  **para Identidade**.

   ![Página of_Microsoft Centro de Segurança do 365 em que há uma opção para abrir o Microsoft Defender para Identidade](../../media/mtp-eval-42.png)

2. Clique **em Criar** para iniciar o assistente do Microsoft Defender para Identidade. 

   ![Página do assistente of_Microsoft Defender para Identidade onde você deve clicar em Criar botão Criar](../../media/mtp-eval-43.png)

3. Escolha **Fornecer um nome de usuário e uma senha para se conectar à sua floresta do Active Directory.**  

   ![Página de of_Microsoft de boas-vindas do Defender para Identidade](../../media/mtp-eval-44.png)

4. Insira suas credenciais locais do Active Directory. Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.

   ![Página de of_Microsoft do Defender para Diretório de Identidade onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. Em seguida, **escolha Baixar a Instalação do Sensor** e transferir o arquivo para o controlador de domínio.

   ![Imagem of_Microsoft página Defender para Identidade onde você pode selecionar Baixar Instalação do Sensor](../../media/mtp-eval-46.png)

6. Execute a Instalação do Microsoft Defender para Sensor de Identidade e comece a seguir o assistente.

   ![Imagem of_Microsoft página Defender para Identidade onde você deve clicar ao lado para seguir o assistente do sensor do Microsoft Defender for Identity](../../media/mtp-eval-47.png)
 
7. Clique **em Próximo** no tipo de implantação do sensor.

   ![Imagem of_Microsoft página Defender para Identidade onde você deve clicar ao lado para ir para a próxima página](../../media/mtp-eval-48.png)
 
8. Copie a chave de acesso porque você precisa insiá-la em seguida no Assistente.

   ![Página of_the sensores de imagem onde você deve copiar a chave de acesso que você precisa inserir na próxima página assistente de instalação do sensor de identidade do Microsoft Defender for Identity](../../media/mtp-eval-49.png)
 
9. Copie a chave de acesso para o Assistente e clique em **Instalar**. 

   ![Página of_Microsoft assistente do sensor defender para identidade onde você deve fornecer a chave de acesso e clicar no botão instalar](../../media/mtp-eval-50.png)

10. Parabéns, você configurou com êxito o Microsoft Defender para Identidade no controlador de domínio.

    ![Conclusão of_Microsoft instalação do assistente do sensor defender for Identity onde você deve clicar no botão concluir](../../media/mtp-eval-51.png)
 
11. Na seção [Configurações](https://go.microsoft.com/fwlink/?linkid=2040449) do Microsoft Defender para Identidade, selecione **Microsoft Defender para Ponto de Extremidade **e, em seguida, acione a alternância. Clique em **Salvar**. 

    ![Página of_the configurações de identidade do Microsoft Defender para a qual você deve ativar a alternância do Microsoft Defender para o Ponto de Extremidade](../../media/mtp-eval-52.png)

> [!NOTE]
> Windows Defender ATP foi renomeada como Microsoft Defender para Ponto de Extremidade. Alterações de marcação em todos os nossos portais estão sendo roladas para consistência.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud App Security

> [!NOTE]
> Ignore esta etapa se você já habilitar o Microsoft Cloud App Security. 

1. Navegue até o Centro de [Segurança do Microsoft 365 Mais](https://security.microsoft.com/info)Recursos  >  **Microsoft** Cloud App  >  **Security**.

   ![Página of_Microsoft Centro de Segurança do 365 onde você pode ver o cartão do Microsoft Cloud App e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. No prompt de informações para integrar o Microsoft Defender para Identidade, selecione **Habilitar a integração de dados do Microsoft Defender para Identidade.**
  
   ![Prompt of_the informações de imagem para integrar o Microsoft Defender for Identity onde você deve selecionar o link Habilitar o Microsoft Defender para Identidade de integração de dados](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se você não vir esse prompt, pode significar que a integração de dados do Microsoft Defender for Identity já foi habilitada. No entanto, se você não tiver certeza, entre em contato com o administrador de TI para confirmar. 

3. Vá para **Configurações**, a opção Integração do **Microsoft Defender para Identidade** e clique em **Salvar**. 

   ![Página of_the configurações de imagem em que você deve ativar a alternância de integração do Microsoft Defender for Identity e clique em salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para novas instâncias do Microsoft Defender para Identidade, essa alternância de integração é automaticamente ativado. Confirme se a integração com o Microsoft Defender for Identity foi habilitada antes de prosseguir para a próxima etapa.
 
4. Nas configurações de descoberta na nuvem, selecione **Integração do Microsoft Defender para Ponto de Extremidade** e habilita a integração. Clique em **Salvar**.

   ![Imagem of_the página do Microsoft Defender para Ponto de Extremidade onde a caixa de seleção bloquear aplicativos não selecionados em Integração do Microsoft Defender para Ponto de Extremidade está selecionada. Clique em salvar.](../../media/mtp-eval-56.png)

5. Em Configurações de descoberta na nuvem, selecione **Enriquecimento de usuário** e habilita a integração com o Azure Active Directory.

   ![Seção Imagem de enriquecimento do usuário em que a caixa de seleção enriquecer identificadores de usuário descobertos com nomes de usuário do Azure Active Directory está selecionada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar o Microsoft Defender para Ponto de Extremidade

>[!NOTE]
>Ignore esta etapa se você já habilitar o Microsoft Defender para Ponto de Extremidade.

1. Navegue até o Centro de [Segurança do Microsoft 365 Mais](https://security.microsoft.com/info)Recursos  >  **Centro** de Segurança do  >  **Microsoft Defender.** Clique em **Abrir**. 

   ![Opção of_Microsoft Centro de Segurança do Defender na página Centro de Segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga o assistente do Microsoft Defender para Ponto de Extremidade. Clique em **Avançar**. 

   ![Página of_the assistente de boas-vindas do Centro de Segurança do Microsoft Defender](../../media/mtp-eval-59.png)

3. Escolha com base em seu local de armazenamento de dados preferencial, política de retenção de dados, tamanho da organização e aceitação para recursos de visualização.

   ![Página of_the imagem para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização. Clique em próximo quando terminar de selecionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente. 

   Clique em **Avançar**. 

4. Clique **em Continuar** e ele provisiona seu locatário do Microsoft Defender para Ponto de Extremidade.

   ![Imagem of_the página solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. A integração de seus pontos de extremidade por meio de Políticas de Grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft Defender para Ponto de Extremidade. Para simplificar, este guia usa o script local.

6. Clique **em Baixar pacote** e copie o script de integração para seus pontos de extremidade.

   ![Imagem of_page solicitando que você clique no botão Baixar pacote para copiar o script de integração para seu ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. No ponto de extremidade, execute o script de integração como Administrador e escolha Y. 

   ![Linha of_the de comando de imagem onde você executar o script de integração e escolher Y para prosseguir](../../media/mtp-eval-63.png)

8. Parabéns, você integra seu primeiro ponto de extremidade.

   ![Image of_the commandline em que você tem a confirmação de que você integra seu primeiro ponto de extremidade. Pressione qualquer tecla para continuar](../../media/mtp-eval-64.png)

9. Copie o teste de detecção do assistente do Microsoft Defender para Ponto de Extremidade.

   ![Imagem of_the executar uma etapa de teste de detecção em que você deve clicar em Copiar para copiar o script de teste de detecção que você deve colar no prompt de comando](../../media/mtp-eval-65.png)

10. Copie o script do PowerShell para um prompt de comando elevado e execute-o. 

    ![Prompt of_command imagem em que você deve copiar o script do PowerShell para um prompt de comando elevado e execute-o](../../media/mtp-eval-66.png)

11. Selecione **Iniciar usando o Microsoft Defender para Ponto de** Extremidade no Assistente.

    ![Prompt de of_the de confirmação do assistente em que você deve clicar em Iniciar usando o Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-67.png)
 
12. Visite o [Centro de Segurança do Microsoft Defender.](https://securitycenter.windows.com/) Vá para **Configurações** e selecione **Recursos avançados.** 

    ![Menu Of_Microsoft Configurações do Centro de Segurança do Defender em que você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. Ativar a integração com **o Microsoft Defender para Identidade.**  

    ![Recursos avançados do Centro de Segurança do Defender of_Microsoft imagem, alternância de opção do Microsoft Defender for Identity que você precisa ativar](../../media/mtp-eval-69.png)

14. Ativar a integração com o **Office 365 Threat Intelligence**.

    ![Recursos avançados of_Microsoft Centro de Segurança do Defender, opção de Inteligência de Ameaças do Office 365 que você precisa ativar](../../media/mtp-eval-70.png)

15. Ativar a integração com **o Microsoft Cloud App Security**.

    ![Recursos avançados do Centro de Segurança do Defender of_Microsoft Imagem, opção De segurança do Aplicativo na Nuvem da Microsoft que você precisa ativar](../../media/mtp-eval-71.png)

16. Role para baixo e **clique em Salvar preferências** para confirmar as novas integrações.

    ![Botão de of_Save de preferências de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar o serviço Microsoft 365 Defender

>[!NOTE]
>A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos do Microsoft 365 Defender para todos os locatários qualificados. Confira este [artigo do Microsoft Tech Community sobre qualificação de licença para](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) obter detalhes. 


Vá para o Centro de Segurança do [Microsoft 365.](https://security.microsoft.com/homepage) Navegue **até Configurações** e selecione **Microsoft 365 Defender**.

![Captura de tela of_Microsoft opção Do Defender 365 na página Configurações do Centro de Segurança do Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obter uma orientação mais abrangente, consulte [Ativar o Microsoft 365 Defender](m365d-enable.md). 

Parabéns! Você acabou de criar seu laboratório de avaliação do Microsoft 365 Defender ou um ambiente piloto! Agora você pode se familiarizar com a interface do usuário do Microsoft 365 Defender! Veja o que você pode aprender com o guia interativo do Microsoft 365 Defender a seguir e saiba como usar cada painel para suas tarefas de operação de segurança diárias.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Em seguida, você pode simular um ataque e ver como os recursos entre produtos detectam, criam alertas e respondem automaticamente a um ataque sem arquivo em um ponto de extremidade.

## <a name="next-step"></a>Próxima etapa

- [Gerar um alerta de teste](generate-test-alert.md) - Execute uma simulação de ataque em seu laboratório de avaliação do Microsoft 365 Defender.