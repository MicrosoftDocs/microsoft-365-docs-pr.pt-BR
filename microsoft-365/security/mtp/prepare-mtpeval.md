---
title: Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
description: Preparar o desligamento de pessoas, cronogramas, considerações de ambiente e ordem de adoção ao configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection
keywords: MTP Trial Prep, implantar, preparar, acionista, linha do tempo, ambiente, ponto de extremidade, servidor, gerenciamento, adoção
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
ms.openlocfilehash: da0fd99aaa533c6e4f65b5b279adcd9a4b648c9c
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049622"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-environment"></a>Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/>Fase 1: preparar</a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection" />
      <br/>Fase 2: configuração</a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Configure cada pilar de proteção contra ameaças da Microsoft e integração de seus pontos de extremidade" />
      <br/>Fase 3: configurar o & integrado</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

Você está atualmente na fase de preparação.


A preparação é fundamental para qualquer implantação bem-sucedida. Esta seção orientará você sobre o que você precisa considerar ao se preparar para criar um ambiente de laboratório de avaliação para sua implantação do Microsoft Threat Protection.

## <a name="prerequisites"></a>Pré-requisitos
Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar a proteção contra ameaças da Microsoft. Confira os requisitos mínimos para a [proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), [Microsoft defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud app Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Participantes e aprovação
A seção a seguir serve para identificar todos os participantes envolvidos no projeto e que talvez precisem ser desligados, revisados ou permaneçam informados, mesmo para uma avaliação ou prova de conceito de execução seca.

>[!NOTE]
>Nem todas as organizações podem ter a maturidade da organização de segurança para ter essas funções. Nesse caso, consulte sua equipe de liderança no responsabilidades de revisão e aprovação.

Adicione participantes à tabela abaixo, conforme apropriado para sua organização.

-   Portanto = aprovação neste projeto

-   R = revise este projeto e forneça a entrada

-   I = informamos este projeto

| Nome                 | Role                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Insira o nome e o email | **Diretor de segurança de informações (ciso)** *um representante executivo que atua como patrocinador dentro da organização para a nova implantação de tecnologia.*                                                  | Então     |
| Insira o nome e o email | **Chefe do CDOC (Cyber Defense Operations Center)** *um representante da equipe do CDOC responsável por definir como essa alteração está alinhada com os processos da equipe de operações de segurança do cliente.*       | Então     |
| Insira o nome e o email | **Arquiteto de segurança** *um representante da equipe de segurança responsável por definir como essa alteração é alinhada à arquitetura de segurança principal na organização.*                         | R      |
| Insira o nome e o email | **Arquiteto de área de trabalho** *um representante da equipe de ti encarregado de definir como essa alteração é alinhada à arquitetura principal de local de trabalho na organização.*                             | R      |
| Insira o nome e o email | **Analista de segurança** *um representante da equipe do CDOC que pode fornecer informações sobre os recursos de detecção, a experiência do usuário e a utilidade geral dessa alteração de uma perspectiva de operações de segurança.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar o Azure Active Directory
Pule esta etapa se você já tiver habilitado a sincronização entre o Active Directory e o Active Directory do Azure no local. Analise a documentação de práticas recomendadas existentes no Azure Active Directory. As etapas a seguir são otimizadas para avaliar a proteção contra ameaças da Microsoft.

1. Vá para o portal [do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure ad Connect**. 
![Imagem da página do portal do Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Clique em **baixar** do **Microsoft Azure Active Directory Connect** e transfira-o para o seu controlador de domínio.
![Imagem da página de download do Azure active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. No controlador de domínio, siga o assistente do Azure Active Directory Connect. Leia os termos de licença e o aviso de privacidade e marque a caixa de seleção se você concordar. Clique em **Continuar**.
![Imagem da página de boas-vindas do Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Navegue até **configurações expressas**.
![Imagem da página de configurações Express](../../media/mtp-eval-4.png) <br>

5. Insira suas credenciais de administrador global. Clique em **Avançar**.
![Imagem da conexão com a página do Azure AD onde você deve inserir suas credenciais de administrador global](../../media/mtp-eval-5.png) <br>

6. Insira as credenciais de administrador corporativo dos serviços de domínio do Active Directory. Clique em **Avançar**.
![Imagem da conexão com a página do AD DS onde você deve inserir suas credenciais](../../media/mtp-eval-6.png) <br>

7. Clique em **instalar** para confirmar a configuração.
![Imagem da página de confirmação de configuração](../../media/mtp-eval-7.png) <br>

8. Parabéns, você configurou com êxito o Azure Active Directory Connect.
![Imagem de uma página de conexão do Azure Active Directory configurada com êxito](../../media/mtp-eval-8.png) <br>

Agora você pode [Adicionar usuários e grupos ao Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) e [Configurar uma política Sam-R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Ordem de configuração
A tabela abaixo indica a ordem que a Microsoft recomenda para configurar os componentes de proteção contra ameaças da Microsoft para sua implantação de ambiente de laboratório de avaliação.

| Componente                               | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificação da ordem de configuração |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Proteção Avançada contra Ameaças do Office 365| O Office 365 ATP salvaguarda sua organização contra ameaças mal-intencionadas que foram causadas por mensagens de email, links (URLs) e ferramentas de colaboração. <br> [Saiba Mais.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                   |
|Proteção Avançada contra Ameaças do Azure|O Azure ATP usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações maliciosas mal-intencionadas direcionadas para sua organização. <br> [Saiba mais](https://docs.microsoft.com/azure-advanced-threat-protection/).| duas |
|Microsoft Cloud App Security| O Microsoft Cloud app Security é um CASB (agente de segurança de acesso à nuvem) que opera em várias nuvens. Ele oferece visibilidade avançada, controle sobre a viagem de dados e análises sofisticadas para identificar e combater o ciberataques em todos os seus serviços de nuvem. <br> [Saiba mais](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3D                   |
|Proteção avançada contra ameaças do Microsoft Defender | Os recursos de detecção e resposta de ponto de extremidade da ATP do Microsoft Defender fornecem detecções avançadas de ataques quase em tempo real e acionáveis. Os analistas de segurança podem priorizar alertas de maneira eficaz, obter visibilidade de todo o escopo de uma violação e executar ações de resposta para remediar ameaças. <br> [Saiba Mais.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Próxima etapa
|||
|:-------|:-----|
|![Fase 2: configuração](../../media/setup.png) <br>[Fase 2: configuração](setup-mtpeval.md) | Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft

