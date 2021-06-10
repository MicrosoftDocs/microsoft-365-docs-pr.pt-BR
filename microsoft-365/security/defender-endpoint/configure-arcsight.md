---
title: Configurar o Micro Focus ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade
description: Configurar o Micro Focus ArcSight para receber e puxar detecções de Central de Segurança do Microsoft Defender
keywords: configurar o Micro Focus ArcSight, as ferramentas de gerenciamento de informações e eventos de segurança, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166180"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Configurar o Micro Focus ArcSight para puxar o Defender para detecções de ponto de extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

Você precisará instalar e configurar alguns arquivos e ferramentas para usar o Micro Focus ArcSight para que ele possa puxar o Defender para detecções de ponto de extremidade.

>[!Note]
>- [O Alerta do Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções
>- [O Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Device e seus detalhes de Alerta relacionados.

## <a name="before-you-begin"></a>Antes de começar

Configurar a ferramenta Micro Focus ArcSight Connector requer vários arquivos de configuração para ele puxar e analisar detecções do seu aplicativo Azure Active Directory (AAD).

Esta seção orienta você a obter as informações necessárias para definir e usar os arquivos de configuração necessários corretamente.

- Certifique-se de habilitar o recurso de integração SIEM no **menu Configurações.** Para obter mais informações, consulte [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).

- Tenha o arquivo salvo da habilitação do recurso de integração SIEM pronto. Você precisará obter os seguintes valores:
  - URL de atualização do token OAuth 2.0
  - ID do cliente OAuth 2.0
  - Segredo do cliente OAuth 2.0

- Tenha os seguintes arquivos de configuração prontos:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    Você teria salvo um arquivo .zip que contém esses dois arquivos quando escolheu o Micro Focus ArcSight como o tipo SIEM que você usa em sua organização.

- Certifique-se de gerar os seguintes tokens e se eles estão prontos:
  - Token de acesso
  - Token de atualização

  Você pode gerar esses tokens a partir da seção de instalação de integração **siem** do portal.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Instalar e configurar o Micro Focus ArcSight FlexConnector

As etapas a seguir pressupom que você concluiu todas as etapas necessárias em [Before you begin](#before-you-begin).

1. Instale o mais recente instalador Windows FlexConnector de 32 bits. Você pode encontrar isso no Centro de Software HPE. Normalmente, a ferramenta é instalada no seguinte local padrão: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>Você pode escolher onde salvar a ferramenta, por exemplo, C: \\ *folder_location*\current\bin onde folder_location representa o local da instalação. 

2. Siga o assistente de instalação pelas seguintes tarefas:
   - Introdução
   - Escolha Instalar Pasta
   - Escolha Instalar Conjunto
   - Escolha Pasta de Atalho
   - Resumo da pré-instalação
   - Instalando...

   Você pode manter os valores padrão para cada uma dessas tarefas ou modificar a seleção para atender aos seus requisitos.

3. Abra o Explorador de Arquivos e localize os dois arquivos de configuração salvos ao habilitar o recurso de integração SIEM. Coloque os dois arquivos no local de instalação do FlexConnector, por exemplo:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > Você deve colocar os arquivos de configuração nesse local, onde folder_location *representa* o local onde você instalou a ferramenta.

4. Depois que a instalação do conector principal é concluída, a janela de Instalação do Conector é aberta. Na janela Configuração do Conector, selecione **Adicionar um Conector**.

5. Selecione Tipo: **ArcSight FlexConnector REST** e clique em **Próximo**.

6. Digite as informações a seguir no formulário de detalhes do parâmetro. Todos os outros valores no formulário são opcionais e podem ser deixados em branco.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Campo</th>
    <th>Valor</th>
    </tr>
    <tr>
    <td>Arquivo de Configuração</td>
    <td>Digite o nome do arquivo de propriedade do cliente. O nome deve corresponder ao arquivo fornecido na .zip que você baixou.
Por exemplo, se o arquivo de configuração no diretório flexagent for chamado &quot; &quot;WDATP-Connector.js&quot; onparser.properties, digite &quot; &quot; WDATP-Connector &quot; como o nome do arquivo de propriedade do cliente.</td>
    </tr>
    <td>URL de eventos</td>
    <td>Dependendo do local do datacenter, selecione a URL da UE ou dos EUA: </br></br> <b>Para a UE</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>Para OS:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>Para o</b>Reino Unido : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Tipo de autenticação</td>
    <td>OAuth 2</td>
    </tr>
    <td>Arquivo propriedades do cliente OAuth 2</td>
    <td>Navegue até o local do <em>arquivo wdatp-connector.properties.</em> O nome deve corresponder ao arquivo fornecido na .zip que você baixou.</td>
    <tr>
    <td>Token de atualização</td>
    <td>Você pode obter um token de atualização de duas maneiras: gerando um token de atualização a partir da página de configurações <b>siem</b> ou usando a ferramenta restutil. <br><br> Para obter mais informações sobre como gerar um token de atualização da configuração <b>Preferências,</b> consulte <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>. </br> </br><b>Obter seu token de atualização usando a ferramenta restutil:</b> </br> a. Abra um prompt de comando. Navegue até C:\<em>folder_location</em>\current\bin onde folder_location <em>representa</em> o local onde você instalou a ferramenta. </br></br> b. Tipo: <code>arcsight restutil token -config</code> do diretório bin. Por exemplo: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Uma janela do navegador da Web será aberta. </br> </br>c. Digite suas credenciais e clique no campo senha para permitir que a página seja redirecionada. No prompt de logon, insira suas credenciais. </br> </br>d. Um token de atualização é mostrado no prompt de comando. </br></br> e. Copie e colar no campo <b>Token de Atualização.</b>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. Uma janela do navegador é aberta pelo conector. Faça logon com suas credenciais de aplicativo. Depois de fazer logon, você será solicitado a dar permissão ao cliente OAuth2. Você deve dar permissão ao cliente OAuth 2 para que a configuração do conector possa ser autenticada.

   Se for <code>redirect_uri</code> uma URL https, você será redirecionado para uma URL no host local. Você verá uma página que solicita que você confie no certificado fornecido pelo conector em execução no host local. Você precisará confiar nesse certificado se o redirect_uri for um https.
   
   Se, no entanto, você especificar uma URL http para o redirect_uri, não será necessário fornecer consentimento para confiar no certificado.

8. Continue com a configuração do conector retornando à janela de Instalação do Conector do Micro Focus ArcSight.

9. Selecione o **Gerenciador ArcSight (criptografado)** como o destino e clique em **Próximo**.

10. Digite o IP/nome do host de destino no **Nome do Host do Gerente** e suas credenciais no formulário de parâmetros. Todos os outros valores no formulário devem ser mantidos com os valores padrão. Clique em **Avançar**.

11. Digite um nome para o conector no formulário de detalhes do conector. Todos os outros valores no formulário são opcionais e podem ser deixados em branco. Clique em **Avançar**.

12. A janela de certificado de importação do Gerenciador de ESM é mostrada. Selecione **Importar o certificado para conector do destino e** clique em **Próximo**. A **janela Adicionar resumo do** conector é exibida e o certificado é importado.

13. Verifique se os detalhes na janela Adicionar resumo **do** conector estão corretos e clique em **Próximo**.

14. Selecione **Instalar como um serviço e** clique em **Próximo**.

15. Digite um nome no campo **Nome Interno do** Serviço. Todos os outros valores no formulário podem ser mantidos com os valores padrão ou deixados em branco . Clique em **Avançar**.

16. Digite os parâmetros de serviço e clique em **Next**. Uma janela com o **Resumo do Serviço de Instalação** é mostrada. Clique em **Avançar**.

17. Termine a instalação selecionando **Exit** e **Next.**

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Instalar e configurar o console ArcSight de Foco Micro

1. Siga o assistente de instalação pelas seguintes tarefas:
   - Introdução
   - Contrato de Licença
   - Aviso Especial
   - Escolha Diretório de instalação arcSight
   - Escolha Pasta de Atalho
   - Resumo da pré-instalação

2. Clique em **Instalar**. Após a conclusão da instalação, o Assistente de Configuração do Console ArcSight será aberto.

3. Digite localhost no **Nome do Host do Gerente** e 8443 na Porta do **Gerente** e clique em **Próximo**.

4. Selecione **Usar conexão direta** e clique em **Próximo**.

5. Selecione **Autenticação Baseada em Senha** e clique em **Próximo**.

6. Selecione **Esta é uma única instalação do usuário. (Recomendado)**, em seguida, clique **em Próximo**.

7. Clique **em Feito** para sair do instalador.

8. Faça logon no console ArcSight de Foco Micro.

9. Navegue até **Active channel set** New  >  **Condition**  >    >  **Device Device Product**.

10. Definir **Produto do Dispositivo = Microsoft Defender ATP**. Quando você verificar se os eventos estão fluindo para a ferramenta, pare o processo novamente e vá para os Serviços Windows e inicie o REST do ArcSight FlexConnector.

Agora você pode executar consultas no console Do Micro Focus ArcSight.

O Defender para detecções de ponto de extremidade aparecerá como eventos discretos, com "Microsoft" como o fornecedor e "Windows Defender ATP" como o nome do dispositivo.


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Solução de problemas da conexão Micro Focus ArcSight

**Problema:** Falha ao atualizar o token. Você pode encontrar o log localizado em C: folder_location \current\logs onde folder_location representa o local onde \\ você instalou a ferramenta.  Abra _agent.log_ e procure `ERROR/FATAL/WARN` por .

**Sintoma:** Você recebeu a seguinte mensagem de erro:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Solução:**

1. Pare o processo clicando em Ctrl + C na janela Conector. Clique **em Y** quando perguntado "Encerrar o trabalho em lote Y/N?".

2. Navegue até a pasta onde você armazenou o arquivo WDATP-connector.properties e edite-o para adicionar o seguinte valor: `reauthenticate=true` .

3. Reinicie o conector executando o seguinte comando: `arcsight.bat connectors` .

   Uma janela do navegador é exibida. Permita que ele seja executado, ele deve desaparecer e o conector agora deve estar em execução.

> [!NOTE]
> Verifique se o conector está sendo executado interrompendo o processo novamente. Em seguida, inicie o conector novamente e nenhuma janela do navegador deve aparecer.

## <a name="related-topics"></a>Tópicos relacionados
- [Habilitar a integração do SIEM no Defender para Ponto de Extremidade](enable-siem-integration.md)
- [Pull detections to your SIEM tools](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Pull Defender para detecções de ponto de extremidade usando a API REST](pull-alerts-using-rest-api.md)
- [Solucionar problemas de integração da ferramenta SIEM](troubleshoot-siem.md)
