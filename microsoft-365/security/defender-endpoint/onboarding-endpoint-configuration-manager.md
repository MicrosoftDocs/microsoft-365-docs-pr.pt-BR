---
title: Integração usando o Microsoft Endpoint Configuration Manager
description: Saiba como integrar o Microsoft Defender para Ponto de Extremidade usando o Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 31c946ccad84aca3b2fc86c95655cea9e66e182f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186396"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Integração usando o Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Este artigo faz parte do guia implantação e age como um exemplo de método de integração. 

No tópico [Planejamento,](deployment-strategy.md) havia vários métodos fornecidos para os dispositivos de integração ao serviço. Este tópico aborda a arquitetura de co-gerenciamento. 

![Imagem da arquitetura nativa da nuvem ](images/co-management-architecture.png)
 *Diagrama de arquiteturas de ambiente*


Embora o Defender para Ponto de Extremidade suporte à integração de vários pontos de extremidade e ferramentas, este artigo não os abrange. Para obter informações sobre a integração geral usando outras ferramentas e métodos de implantação com suporte, consulte [Onboarding overview](onboarding.md).



Este tópico orienta os usuários em:
- Etapa 1: Integrando dispositivos Windows ao serviço 
- Etapa 2: Configurando o Defender para recursos do Ponto de Extremidade

Essas diretrizes de integração orientarão você pelas seguintes etapas básicas que você precisa seguir ao usar o Microsoft Endpoint Configuration Manager:
- **Criando uma coleção no Microsoft Endpoint Configuration Manager**
- **Configurando o Microsoft Defender para recursos de ponto de extremidade usando o Microsoft Endpoint Configuration Manager**

>[!NOTE]
>Somente dispositivos Windows são abordados nesta implantação de exemplo. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Etapa 1: Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Criação de coleção
Para a integração de dispositivos Windows 10 com o Microsoft Endpoint Configuration Manager, a implantação pode direcionar uma coleção existente ou uma nova coleção pode ser criada para testes. 

A integração usando ferramentas como política de grupo ou método manual não instala nenhum agente no sistema. 

No console do Microsoft Endpoint Configuration Manager, o processo de integração será configurado como parte das configurações de conformidade no console.

Qualquer sistema que receber essa configuração necessária manterá essa configuração enquanto o cliente do Configuration Manager continuar a receber essa política do ponto de gerenciamento. 

Siga as etapas abaixo para os pontos de extremidade de integração usando o Microsoft Endpoint Configuration Manager.

1. No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview Device \> \> Collections**.            

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager1](images/configmgr-device-collections.png)

2. Clique com **o botão direito do mouse em Conjunto de Dispositivos** e selecione Criar Coleção de **Dispositivos**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager2](images/configmgr-create-device-collection.png)

3. Forneça uma **coleção Name** and **Limiting**, em seguida, selecione **Next**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager3](images/configmgr-limiting-collection.png)

4. Selecione **Adicionar Regra** e escolha Regra de **Consulta**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager4](images/configmgr-query-rule.png)

5.  Clique **em Próximo** no Assistente de Associação **Direta** e clique em **Editar instrução De consulta**.

     ![Imagem do Assistente do Microsoft Endpoint Configuration Manager5](images/configmgr-direct-membership.png)

6. Selecione **Critérios** e escolha o ícone de estrela.

     ![Imagem do Assistente do Microsoft Endpoint Configuration Manager6](images/configmgr-criteria.png)

7. Mantenha o tipo de critério como valor simples **,** escolha  onde como Sistema Operacional **-** número de com build , operador maior ou igual a e **valor 14393** e clique em **OK**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager7](images/configmgr-simple-value.png)

8. Selecione **Próximo** e **Fechar**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager8](images/configmgr-membership-rules.png)

9. Selecione **Avançar**.

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager9](images/configmgr-confirm.png)


Depois de concluir essa tarefa, agora você tem uma coleção de dispositivos com todos os pontos de extremidade do Windows 10 no ambiente. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Etapa 2: Configurar o Microsoft Defender para recursos do Ponto de Extremidade 
Esta seção orienta você na configuração dos seguintes recursos usando o Microsoft Endpoint Configuration Manager em dispositivos Windows:

- [**Detecção e resposta do terminal.**](#endpoint-detection-and-response)
- [**Proteção de última geração**](#next-generation-protection)
- [**Redução da superfície do ataque.**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Detecção e resposta do terminal.
#### <a name="windows-10"></a>Windows 10
De dentro do Centro de Segurança do Microsoft Defender, é possível baixar a política '.onboarding' que pode ser usada para criar a política no System Center Configuration Manager e implantar essa política em dispositivos Windows 10.

1. Em um Portal do Centro de Segurança do Microsoft Defender, selecione [Configurações e, em seguida, Integrando](https://securitycenter.windows.com/preferences2/onboarding).



2. Em Método deployment, selecione a versão suportada do **Microsoft Endpoint Configuration Manager**.

    ![Imagem do Assistente de integração do Microsoft Defender para Ponto de Extremidade10](images/mdatp-onboarding-wizard.png)

3. Selecione **Baixar pacote**.

    ![Imagem do Assistente de integração do Microsoft Defender para Ponto de Extremidade11](images/mdatp-download-package.png)

4. Salve o pacote em um local acessível.
5. No Microsoft Endpoint Configuration Manager, navegue até: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.

6. Clique com o botão direito do **mouse em Políticas do Microsoft Defender ATP** e selecione Criar Política do Microsoft Defender **ATP**.

    ![Imagem do Assistente de Configuração do Microsoft Endpoint12](images/configmgr-create-policy.png)

7. Insira o nome e a descrição, verifique **se a integração** está selecionada e selecione **Next**.

    ![Imagem do Assistente de Configuração do Microsoft Endpoint13](images/configmgr-policy-name.png)


8. Clique em **Procurar**.

9. Navegue até o local do arquivo baixado da etapa 4 acima.

10. Clique em **Avançar**.
11. Configure o Agente com as amostras apropriadas (**Nenhum** ou **Todos os tipos de arquivo**).

    ![Imagem das configurações1](images/configmgr-config-settings.png)

12. Selecione a telemetria apropriada (**Normal** ou **Acelerada**) e clique em **Próximo**.

    ![Imagem das configurações2](images/configmgr-telemetry.png)

14. Verifique a configuração e clique em **Próximo**.

     ![Imagem das configurações3](images/configmgr-verify-configuration.png)

15. Clique **em Fechar** quando o Assistente for concluído.

16.  No console do Microsoft Endpoint Configuration Manager, clique com o botão direito do mouse na política Defender para Ponto de Extremidade que você acabou de criar e selecione **Implantar**.

     ![Imagem das configurações4](images/configmgr-deploy.png)

17. No painel direito, selecione a coleção criada anteriormente e clique em **OK**.

    ![Imagem das configurações5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Versões anteriores do Windows Client (Windows 7 e Windows 8.1)
Siga as etapas a seguir para identificar a ID do Espaço de Trabalho do Defender para Ponto de Extremidade e a Chave do Espaço de Trabalho, que serão necessárias para a integração de versões anteriores do Windows.

1. Em um Portal do Centro de Segurança do Microsoft Defender, selecione **Configurações > Integração**.

2. Em sistema operacional, **escolha Windows 7 SP1 e 8.1**.

3. Copie a **ID do Espaço de** Trabalho e **a Chave do Espaço de Trabalho** e salve-as. Eles serão usados posteriormente no processo.

    ![Imagem da integração](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Instale o Microsoft Monitoring Agent (MMA). <br>
    Atualmente, o MMA (a partir de janeiro de 2019) tem suporte nos seguintes Sistemas Operacionais Windows:

    -   SKUs de servidor: Windows Server 2008 SP1 ou Newer

    -   SKUs cliente: Windows 7 SP1 e posterior

    O agente MMA precisará ser instalado em dispositivos Windows. Para instalar o agente, alguns sistemas precisarão baixar o Update para experiência do cliente e [a telemetria](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) de diagnóstico para coletar os dados com o MMA. Essas versões do sistema incluem, mas podem não se limitar a:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    Especificamente, para o Windows 7 SP1, os seguintes patches devem ser instalados:

    -   Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Instale o [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) **ou** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        Não instale ambos no mesmo sistema.

5. Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.

Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.

### <a name="next-generation-protection"></a>Proteção de próxima geração 
O Windows Defender Antivírus é uma solução antimalware interna que oferece proteção de próxima geração para computadores desktop, computadores portáteis e servidores.

1. No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection \> Antimalware Polices** e escolha **Criar Política antimalware**.

    ![Imagem da política antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Selecione **Verificações** agendadas, **Configurações** de **verificação,** ações **padrão,** proteção em tempo **real,** configurações de exclusão, **avançadas,** substituições de **ameaças,** atualizações de inteligência de segurança e serviço de proteção na nuvem e escolha **OK**. 

    ![Imagem do painel de proteção de próxima geração1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    Em determinados setores ou alguns clientes corporativos selecionados podem ter necessidades específicas sobre como o Antivírus é configurado.

  
    [Verificação rápida versus verificação completa e verificação personalizada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Para obter mais detalhes, consulte [Estrutura de configuração do Windows Security](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Imagem do painel de proteção de próxima geração2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Imagem do painel de proteção de próxima geração3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Imagem do painel de proteção de próxima geração4](images/a28afc02c1940d5220b233640364970c.png)

    ![Imagem do painel de proteção de próxima geração5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Imagem do painel de proteção de próxima geração6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Imagem do painel de proteção de próxima geração7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Imagem do painel de proteção de próxima geração8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Imagem do painel de proteção de próxima geração9](images/3876ca687391bfc0ce215d221c683970.png)

3. Clique com o botão direito do mouse na política antimalware recém-criada e selecione **Implantar**.

    ![Imagem do painel de proteção de próxima geração10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Direcionar a nova política antimalware para sua coleção Windows 10 e clique em **OK**.

     ![Imagem do painel de proteção de próxima geração11](images/configmgr-select-collection.png)

Depois de concluir essa tarefa, você agora configurou com êxito o Windows Defender Antivírus.

### <a name="attack-surface-reduction"></a>Redução da superfície do ataque.
O pilar de redução de superfície de ataque do Defender para Ponto de Extremidade inclui o conjunto de recursos que está disponível em Exploit Guard. Regras de redução de superfície de ataque (ASR), Acesso Controlado a Pastas, Proteção de Rede e Proteção contra Exploração. 

Todos esses recursos fornecem um modo de auditoria e um modo de bloqueio. No modo de auditoria, não há impacto no usuário final. Tudo o que ele faz é coletar telemetria adicional e torná-la disponível no Centro de Segurança do Microsoft Defender. O objetivo com uma implantação é mover passo a passo os controles de segurança para o modo de bloqueio.

Para definir regras ASR no modo de auditoria:

1. No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.

   ![Imagem do Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Selecione **Redução de Superfície de Ataque**.
   

3. De definir regras como **Auditoria e** clique em **Próximo**.


    ![Imagem do console do Microsoft Endpoint Configuration Manager1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Confirme a nova política do Exploit Guard clicando em **Next**.

    ![Imagem do console do Microsoft Endpoint Configuration Manager2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. Depois que a política for criada, clique em **Fechar**.

    ![Imagem do console do Microsoft Endpoint Configuration Manager3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Imagem do console do Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.
    
    ![Imagem do console do Microsoft Endpoint Configuration Manager4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Destino da política para a coleção recém-criada do Windows 10 e clique em **OK**.

    ![Imagem do console do Microsoft Endpoint Configuration Manager5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Depois de concluir essa tarefa, agora você configurou com êxito as regras ASR no modo de auditoria.  
  
A seguir estão etapas adicionais para verificar se as regras ASR são aplicadas corretamente aos pontos de extremidade. (Isso pode levar alguns minutos)


1. Em um navegador da Web, navegue até <https://securitycenter.windows.com> .

2.  Selecione **Gerenciamento de configuração** no menu esquerdo.

3. Clique **em Ir para atacar o gerenciamento de superfície** no painel gerenciamento de superfície de ataque. 
    
    ![Imagem do gerenciamento de superfície de ataque](images/security-center-attack-surface-mgnt-tile.png)

4. Clique **na guia** Configuração em Relatórios de regras de redução de superfície de ataque. Ele mostra a visão geral da configuração de regras ASR e o status das regras ASR em cada dispositivo.

    ![Uma captura de tela de relatórios de regras de redução de superfície de ataque1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Clique em cada dispositivo mostra detalhes de configuração das regras ASR.

    ![Uma captura de tela de relatórios de regras de redução de superfície de ataque2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Confira [Otimizar a implantação e as detecções de regras ASR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   para obter mais detalhes.  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Definir regras de Proteção de Rede no modo de auditoria:
1. No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.

    ![Um Gerenciador de Configuração do System Center de captura de tela1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selecione **Proteção de rede**.

3. De definir a configuração como **Auditoria** e clique em **Próximo**. 

    ![Uma captura de tela Do System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Confirme a nova Política do Exploit Guard clicando em **Next**.
    
    ![Uma captura de tela Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Depois que a política for criada, clique em **Fechar**.

    ![Uma política exploit GUard de captura de tela2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.

    ![Uma captura de tela do Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Selecione a política para a coleção recém-criada do Windows 10 e escolha **OK**.

    ![Uma captura de tela do Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



Depois de concluir essa tarefa, você agora configurou com êxito a Proteção de Rede no modo de auditoria.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Para definir regras de Acesso Controlado a Pastas no modo de auditoria:

1. No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.

    ![Captura de tela do Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selecione **Acesso controlado a pastas**.
    
3. De definir a configuração **como Auditoria e** clique em **Próximo.**

    ![Captura de tela do Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Confirme a nova Política do Exploit Guard clicando em **Next**.

    ![Captura de tela do Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Depois que a política for criada, clique em **Fechar**.

    ![Captura de tela do Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.

    ![Captura de tela do Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Destino da política para a coleção recém-criada do Windows 10 e clique em **OK**.

    ![Captura de tela do Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Agora você configurou com êxito o acesso controlado a pastas no modo de auditoria.

## <a name="related-topic"></a>Tópicos relacionados
- [Integração usando o Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
