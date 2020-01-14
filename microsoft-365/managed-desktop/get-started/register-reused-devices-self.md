---
title: Registrar dispositivos existentes sozinho
description: Registrar os dispositivos reutilizados que você já pode ter para que eles possam ser gerenciados pelo Microsoft Managed desktop
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d9b390cc28002b4561d61fa1d6cc411f3b135f1
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112705"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="c4577-103">Registrar dispositivos existentes sozinho</span><span class="sxs-lookup"><span data-stu-id="c4577-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="c4577-104">Este tópico descreve as etapas para reutilizar os dispositivos que você já tem e registrá-los na área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4577-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c4577-105">Se você estiver trabalhando com dispositivos novos, siga as etapas em [registrar novos dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md) em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="c4577-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="c4577-106">O processo para parceiros está documentado em [etapas para que os parceiros registrem dispositivos](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="c4577-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="c4577-107">A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente).</span><span class="sxs-lookup"><span data-stu-id="c4577-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="c4577-108">Você pode registrar dispositivos usando a área de trabalho gerenciada da Microsoft no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c4577-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="c4577-109">Preparar-se para registrar dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="c4577-109">Prepare to register existing devices</span></span>


<span data-ttu-id="c4577-110">Para registrar dispositivos existentes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="c4577-111">Obtenha o hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4577-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="c4577-112">Mesclar os dados de hash</span><span class="sxs-lookup"><span data-stu-id="c4577-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="c4577-113">[Registre os dispositivos na área de trabalho gerenciada da Microsoft](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c4577-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="c4577-114">Verifique se a imagem está correta.</span><span class="sxs-lookup"><span data-stu-id="c4577-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="c4577-115">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4577-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="c4577-116">Obter o hash de hardware</span><span class="sxs-lookup"><span data-stu-id="c4577-116">Obtain the hardware hash</span></span>

<span data-ttu-id="c4577-117">A área de trabalho gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência a seu hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="c4577-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="c4577-118">Você tem quatro opções para obter essas informações de dispositivos que você já está usando:</span><span class="sxs-lookup"><span data-stu-id="c4577-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="c4577-119">Pergunte ao seu fornecedor de OEM o arquivo de registro do piloto automático, que inclui os hashes de hardware.</span><span class="sxs-lookup"><span data-stu-id="c4577-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="c4577-120">Criar um relatório personalizado no [Gerenciador de configurações](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="c4577-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="c4577-121">Executar um script do Windows PowerShell, usando o [Active Directory](#active-directory-powershell-script-method) ou [manualmente](#manual-powershell-script-method) em cada dispositivo, e coletar os resultados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4577-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="c4577-122">Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e [colete os hashes em uma unidade flash removível](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="c4577-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="c4577-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c4577-123">Configuration Manager</span></span>

<span data-ttu-id="c4577-124">Você pode usar o Microsoft Endpoint Configuration Manager para coletar os hashes de hardware de dispositivos existentes que você deseja registrar com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4577-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4577-125">Todos os dispositivos para os quais você deseja obter essas informações devem estar executando o Windows 10, versão 1703 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c4577-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="c4577-126">Você também precisa de um dispositivo que seja um cliente do Configuration Manager conectado ao site do Configuration Manager (Branch atual).</span><span class="sxs-lookup"><span data-stu-id="c4577-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="c4577-127">Você também precisa da função de sistema de site do ponto de relatório configurada em seu ambiente com o SQL Server Reporting Services habilitado.</span><span class="sxs-lookup"><span data-stu-id="c4577-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="c4577-128">Se você atendeu a todos esses pré-requisitos, você está pronto para coletar as informações seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="c4577-129">No console do Gerenciador de configurações, selecione **monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="c4577-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="c4577-130">No espaço de trabalho monitoramento, expanda **relatórios**e selecione **relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c4577-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="c4577-131">Na guia **página inicial** , na seção **criar** , selecione **criar relatório** para abrir o assistente para criar relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="c4577-132">Na página **informações** , defina estas configurações:</span><span class="sxs-lookup"><span data-stu-id="c4577-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="c4577-133">**Nome:** Especifique um nome para o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="c4577-134">**Descrição:** Especifique uma descrição para o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="c4577-135">**Servidor:** Exibe o nome do servidor de relatório no qual você está criando o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="c4577-136">**Caminho:** Selecione **procurar** para especificar uma pasta na qual você deseja armazenar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="c4577-137">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c4577-137">Select **Next**.</span></span> 
6. <span data-ttu-id="c4577-138">Na página **Resumo** , revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="c4577-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="c4577-139">Selecione **anterior** para alterar as configurações ou selecione **Avançar** para criar o relatório no Gerenciador de configurações.</span><span class="sxs-lookup"><span data-stu-id="c4577-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="c4577-140">Na página **conclusão** , selecione **fechar** para sair do assistente e abrir o **Construtor de relatórios** para inserir as configurações de relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="c4577-141">Insira sua conta de usuário e sua senha, se for solicitado e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="c4577-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="c4577-142">Se o construtor de relatórios não estiver instalado no dispositivo, você será solicitado a instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4577-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="c4577-143">Selecione **Executar para instalar o construtor de relatórios**, o que é necessário para modificar e criar relatórios.</span><span class="sxs-lookup"><span data-stu-id="c4577-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="c4577-144">**No Microsoft Report Builder**, forneça a instrução SQL para o relatório e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="c4577-145">No painel esquerdo, selecione **datadatasets**e clique com o botão direito do mouse para **Adicionar DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c4577-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="c4577-146">Vá para a guia **consulta** e, em seguida, insira o nome como *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="c4577-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="c4577-147">Selecione **usar um conjunto de um DataSet inserido em meu relatório**; O construtor de relatórios é aberto.</span><span class="sxs-lookup"><span data-stu-id="c4577-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="c4577-148">No **Construtor de relatórios**, selecione **fonte de dados:**.</span><span class="sxs-lookup"><span data-stu-id="c4577-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="c4577-149">Selecione a fonte de dados padrão, que deve começar com "AutoGen".</span><span class="sxs-lookup"><span data-stu-id="c4577-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="c4577-150">Escolha **tipo de consulta como texto**e, em seguida, insira esta consulta:</span><span class="sxs-lookup"><span data-stu-id="c4577-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="c4577-151">Navegue até a guia **campo** , os valores de wehre para o **nome do campo** e a origem do **campo** já devem estar preenchidos.</span><span class="sxs-lookup"><span data-stu-id="c4577-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="c4577-152">Se não estiverem, selecione **Adicionar**e, em seguida, selecione **campo de consulta**.</span><span class="sxs-lookup"><span data-stu-id="c4577-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="c4577-153">Insira o **nome do campo** e a **origem do campo**.</span><span class="sxs-lookup"><span data-stu-id="c4577-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="c4577-154">Repita o procedimento para cada um destes valores:</span><span class="sxs-lookup"><span data-stu-id="c4577-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="c4577-155">Fabricantes</span><span class="sxs-lookup"><span data-stu-id="c4577-155">Manufacturer</span></span> 
    - <span data-ttu-id="c4577-156">Modelo</span><span class="sxs-lookup"><span data-stu-id="c4577-156">Model</span></span> 
    - <span data-ttu-id="c4577-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="c4577-157">Serial_Number</span></span> 
    - <span data-ttu-id="c4577-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="c4577-158">HardwareHash</span></span>
7. <span data-ttu-id="c4577-159">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4577-159">Select **OK**.</span></span>

<span data-ttu-id="c4577-160">**Em seguida, defina a exibição do relatório e crie o relatório** seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="c4577-161">Selecionar **tabela ou matriz**; um novo assistente será aberto.</span><span class="sxs-lookup"><span data-stu-id="c4577-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="c4577-162">Em **escolher um conjunto de um**, selecione **escolher um conjunto de um existente neste relatório ou um conjunto de um compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="c4577-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="c4577-163">Selecione **DataSet0** (o padrão) e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c4577-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="c4577-164">Arraste o **fabricante**, o **modelo**e o **número de série** para a caixa grupos de **linhas** .</span><span class="sxs-lookup"><span data-stu-id="c4577-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="c4577-165">Arraste **HardwareHash** para a caixa **valores** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c4577-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="c4577-166">Desmarque as caixas de seleção **Mostrar Subtotais e totais gerais** e **expandir/recolher grupos**.</span><span class="sxs-lookup"><span data-stu-id="c4577-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="c4577-167">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c4577-167">Select **Next**.</span></span>
6. <span data-ttu-id="c4577-168">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c4577-168">Select **Finish**.</span></span>
7. <span data-ttu-id="c4577-169">Selecione **executar** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-169">Select **Run** to run your report.</span></span> <span data-ttu-id="c4577-170">Verifique se o relatório fornece as informações que você espera.</span><span class="sxs-lookup"><span data-stu-id="c4577-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="c4577-171">Se necessário, selecione **design** para retornar ao modo de design para modificar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="c4577-172">Selecione **salvar** para salvar o relatório no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c4577-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="c4577-173">Você pode executar o novo relatório no nó relatórios no espaço de trabalho de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c4577-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="c4577-174">**Por fim, exporte o relatório e use-o para registrar dispositivos** seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c4577-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="c4577-175">(Você só precisará seguir as etapas 1 e 2 desta seção se tiver navegado após as etapas anteriores.):</span><span class="sxs-lookup"><span data-stu-id="c4577-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="c4577-176">No console do Gerenciador de configurações, selecione **monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="c4577-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="c4577-177">Em **monitoramento**, expanda **relatórios**e selecione **relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c4577-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="c4577-178">Localize o relatório usando o nome que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4577-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="c4577-179">Clique com o botão direito do mouse no relatório e selecione **executar**.</span><span class="sxs-lookup"><span data-stu-id="c4577-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="c4577-180">Na caixa de diálogo que é aberta, selecione **Exportar** e, em seguida, selecione **salvar como CSV**.</span><span class="sxs-lookup"><span data-stu-id="c4577-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="c4577-181">Esta versão do relatório extrai hashes de todos os dispositivos Windows 10 aos quais o Gerenciador de configuração se comunica.</span><span class="sxs-lookup"><span data-stu-id="c4577-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="c4577-182">Você precisará filtrar os resultados apenas nos dispositivos que planeja registrar com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4577-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c4577-183">A consulta no Gerenciador de configurações não permite espaços em nomes de coluna exportados; é por isso que as etapas tinham que inserir "Serial_Number" e "HardwareHash".</span><span class="sxs-lookup"><span data-stu-id="c4577-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="c4577-184">Agora que você tem o arquivo CSV exportado, você deve editar os cabeçalhos de relatório para ler o *número de série* e o *hash de hardware* , conforme mostrado aqui antes de prosseguir com o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4577-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="c4577-185">Agora você pode prosseguir para [registrar dispositivos usando o portal do Azure](#register-devices-by-using-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c4577-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="c4577-186">Método de script do PowerShell do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4577-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="c4577-187">Em um ambiente do Active Directory, você pode usar `Get-MMDRegistrationInfo` o cmdlet do PowerShell para coletar remotamente as informações de dispositivos nos grupos do Active Directory usando o WinRM.</span><span class="sxs-lookup"><span data-stu-id="c4577-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="c4577-188">Você também pode usar o `Get-AD Computer` cmdlet e obter resultados filtrados para um determinado nome de modelo de hardware incluído no catálogo.</span><span class="sxs-lookup"><span data-stu-id="c4577-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="c4577-189">Para fazer isso, primeiro confirme esses pré-requisitos e prossiga com as etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="c4577-190">O WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c4577-190">WinRM is enabled.</span></span>
- <span data-ttu-id="c4577-191">Os dispositivos que você deseja registrar estão ativos na rede (ou seja, eles não são desconectados ou desativados).</span><span class="sxs-lookup"><span data-stu-id="c4577-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="c4577-192">Verifique se você tem um parâmetro de credencial de domínio que tenha permissão para executar remotamente nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4577-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="c4577-193">Verifique se o Firewall do Windows permite acesso ao WMI.</span><span class="sxs-lookup"><span data-stu-id="c4577-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="c4577-194">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="c4577-195">Abra o painel de controle do **Windows Defender firewall** e selecione **permitir um aplicativo ou recurso por meio do Windows Defender firewall**.</span><span class="sxs-lookup"><span data-stu-id="c4577-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="c4577-196">Encontre **Instrumentação de gerenciamento do Windows (WMI)** na lista, habilite para **privado e público**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4577-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="c4577-197">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c4577-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c4577-198">Execute *um* destes scripts:</span><span class="sxs-lookup"><span data-stu-id="c4577-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="c4577-199">Acessar os diretórios em que pode haver entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4577-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="c4577-200">Remova as entradas de cada dispositivo de *todos os* diretórios, incluindo os serviços de domínio do Active Directory do Windows Server e o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4577-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="c4577-201">Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.</span><span class="sxs-lookup"><span data-stu-id="c4577-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="c4577-202">Serviços de gerenciamento de acesso onde podem existir entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4577-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="c4577-203">Remova as entradas de cada dispositivo de *todos os* serviços de gerenciamento, incluindo o Microsoft Endpoint Configuration Manager, o Microsoft Intune e o Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="c4577-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manger, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="c4577-204">Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.</span><span class="sxs-lookup"><span data-stu-id="c4577-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="c4577-205">Agora você pode prosseguir para [registrar dispositivos](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c4577-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="c4577-206">Método de script do PowerShell manual</span><span class="sxs-lookup"><span data-stu-id="c4577-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="c4577-207">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c4577-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c4577-208">Sejam`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="c4577-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="c4577-209">Sejam`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c4577-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="c4577-210">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="c4577-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="c4577-211">Método de unidade flash</span><span class="sxs-lookup"><span data-stu-id="c4577-211">Flash drive method</span></span>

1. <span data-ttu-id="c4577-212">Em um dispositivo diferente daquele que você está registrando, insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="c4577-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="c4577-213">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c4577-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="c4577-214">Sejam`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="c4577-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="c4577-215">Ative o dispositivo que você está registrando, mas *não inicie a experiência de instalação*.</span><span class="sxs-lookup"><span data-stu-id="c4577-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="c4577-216">Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4577-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="c4577-217">Insira a unidade USB e, em seguida, pressione SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="c4577-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="c4577-218">Abra um prompt do PowerShell com direitos administrativos e, em `cd <pathToUsb>`seguida, execute.</span><span class="sxs-lookup"><span data-stu-id="c4577-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="c4577-219">Sejam`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="c4577-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="c4577-220">Sejam`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c4577-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="c4577-221">Remova a unidade USB e desligue o dispositivo executando`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="c4577-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="c4577-222">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="c4577-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="c4577-223">Não ligue o dispositivo que você está registrando novamente até concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="c4577-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="c4577-224">Mesclar dados de hash</span><span class="sxs-lookup"><span data-stu-id="c4577-224">Merge hash data</span></span>

<span data-ttu-id="c4577-225">Se você coletou os dados de hash de hardware pelos métodos manuais do PowerShell ou unidade flash, agora precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="c4577-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="c4577-226">Veja um exemplo de script do PowerShell para facilitar:</span><span class="sxs-lookup"><span data-stu-id="c4577-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="c4577-227">Com os dados de hash mesclados em um arquivo CSV, agora você pode prosseguir para [registrar os dispositivos](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c4577-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="c4577-228">Registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="c4577-228">Register devices</span></span>

<span data-ttu-id="c4577-229">O arquivo CSV deve estar em um formato específico para o registro.</span><span class="sxs-lookup"><span data-stu-id="c4577-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="c4577-230">Se você coletou os dados nas etapas anteriores, o arquivo já deve estar no formato correto; Se você obtiver o arquivo de um fornecedor, talvez seja necessário ajustar o formato.</span><span class="sxs-lookup"><span data-stu-id="c4577-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="c4577-231">Para sua conveniência, é possível baixar um [modelo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para esse arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c4577-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="c4577-232">O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas.</span><span class="sxs-lookup"><span data-stu-id="c4577-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="c4577-233">Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo.</span><span class="sxs-lookup"><span data-stu-id="c4577-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="c4577-234">Se você esquecer de alterar qualquer um dos dados de exemplo, o registro falhará.</span><span class="sxs-lookup"><span data-stu-id="c4577-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="c4577-235">Registrar dispositivos usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="c4577-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="c4577-236">No [portal do Azure](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecione **dispositivos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="c4577-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="c4577-237">Selecione **+ registrar dispositivos**; o funcionamento é aberto:</span><span class="sxs-lookup"><span data-stu-id="c4577-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="c4577-238">[![Entrada após selecionar registrar dispositivos, listando dispositivos com colunas para usuários atribuídos, número de série, status, data do último-observado e idade](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="c4577-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Infelizmente, isso não é verdadeiro. Podemos remover esta anotação, mas deixá-la agora até que haja uma oportunidade de conversar sobre ela.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="c4577-240">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4577-240">Follow these steps:</span></span>

1. <span data-ttu-id="c4577-241">Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4577-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="c4577-242">Opcionalmente, você pode adicionar uma ID de **pedido** ou de **compra** para seus próprios fins de controle.</span><span class="sxs-lookup"><span data-stu-id="c4577-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="c4577-243">Não há requisitos de formato para esses valores.</span><span class="sxs-lookup"><span data-stu-id="c4577-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="c4577-244">Selecione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="c4577-244">Select **Register devices**.</span></span> <span data-ttu-id="c4577-245">O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**.</span><span class="sxs-lookup"><span data-stu-id="c4577-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="c4577-246">O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário final comece a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4577-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="c4577-247">Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="c4577-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="c4577-248">Os Estados possíveis relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="c4577-248">Possible states reported there include:</span></span>

| <span data-ttu-id="c4577-249">Estado</span><span class="sxs-lookup"><span data-stu-id="c4577-249">State</span></span> | <span data-ttu-id="c4577-250">Descrição</span><span class="sxs-lookup"><span data-stu-id="c4577-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="c4577-251">Registro pendente</span><span class="sxs-lookup"><span data-stu-id="c4577-251">Registration pending</span></span> | <span data-ttu-id="c4577-252">O registro ainda não foi feito.</span><span class="sxs-lookup"><span data-stu-id="c4577-252">Registration is not done yet.</span></span> <span data-ttu-id="c4577-253">Verifique novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="c4577-253">Check back later.</span></span> |
| <span data-ttu-id="c4577-254">Falha no registro</span><span class="sxs-lookup"><span data-stu-id="c4577-254">Registration failed</span></span> | <span data-ttu-id="c4577-255">Não foi possível concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="c4577-255">Registration could not be completed.</span></span> <span data-ttu-id="c4577-256">Consulte [Solucionando problemas de registro de dispositivo](#troubleshooting-device-registration) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c4577-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="c4577-257">Pronto para o usuário</span><span class="sxs-lookup"><span data-stu-id="c4577-257">Ready for user</span></span> | <span data-ttu-id="c4577-258">O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="c4577-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="c4577-259">A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos.</span><span class="sxs-lookup"><span data-stu-id="c4577-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="c4577-260">Ativo</span><span class="sxs-lookup"><span data-stu-id="c4577-260">Active</span></span> | <span data-ttu-id="c4577-261">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c4577-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c4577-262">Isso também indica que eles estão usando o dispositivo regularmente.</span><span class="sxs-lookup"><span data-stu-id="c4577-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="c4577-263">Inativa</span><span class="sxs-lookup"><span data-stu-id="c4577-263">Inactive</span></span> | <span data-ttu-id="c4577-264">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c4577-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c4577-265">No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).</span><span class="sxs-lookup"><span data-stu-id="c4577-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="c4577-266">Solucionando problemas de registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4577-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="c4577-267">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="c4577-267">Error message</span></span> | <span data-ttu-id="c4577-268">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c4577-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="c4577-269">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="c4577-269">Device not found</span></span> | <span data-ttu-id="c4577-270">Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido.</span><span class="sxs-lookup"><span data-stu-id="c4577-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="c4577-271">Confirme esses valores com seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4577-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="c4577-272">Hash de hardware inválido</span><span class="sxs-lookup"><span data-stu-id="c4577-272">Hardware hash not valid</span></span> | <span data-ttu-id="c4577-273">O hash de hardware fornecido para este dispositivo não foi formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="c4577-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="c4577-274">Verifique novamente o hash de hardware e envie novamente.</span><span class="sxs-lookup"><span data-stu-id="c4577-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="c4577-275">Dispositivo já registrado</span><span class="sxs-lookup"><span data-stu-id="c4577-275">Device already registered</span></span> | <span data-ttu-id="c4577-276">Este dispositivo já está registrado na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4577-276">This device is already registered to your organization.</span></span> <span data-ttu-id="c4577-277">Nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="c4577-277">No further action required.</span></span> |
| <span data-ttu-id="c4577-278">Dispositivo solicitado por outra organização</span><span class="sxs-lookup"><span data-stu-id="c4577-278">Device claimed by another organization</span></span> | <span data-ttu-id="c4577-279">Este dispositivo já foi reivindicado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="c4577-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="c4577-280">Consulte seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4577-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="c4577-281">Erro inesperado</span><span class="sxs-lookup"><span data-stu-id="c4577-281">Unexpected error</span></span> | <span data-ttu-id="c4577-282">Sua solicitação não pôde ser processada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c4577-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="c4577-283">Entre em contato com o suporte e forneça a ID da solicitação:<requestId></span><span class="sxs-lookup"><span data-stu-id="c4577-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="c4577-284">Verificar a imagem</span><span class="sxs-lookup"><span data-stu-id="c4577-284">Check the image</span></span>

<span data-ttu-id="c4577-285">Se o seu dispositivo vier de um fornecedor de parceiros de área de trabalho gerenciada da Microsoft, a imagem deve estar correta.</span><span class="sxs-lookup"><span data-stu-id="c4577-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="c4577-286">Você também poderá aplicar a imagem sozinho, se preferir.</span><span class="sxs-lookup"><span data-stu-id="c4577-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="c4577-287">Para começar, entre em contato com o representante da Microsoft com o qual você está trabalhando e forneça o local e as etapas para a aplicação da imagem.</span><span class="sxs-lookup"><span data-stu-id="c4577-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="c4577-288">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4577-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4577-289">Antes de entregar o dispositivo ao usuário, verifique se você obteve e aplicou as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="c4577-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="c4577-290">Se todas as licenças forem aplicadas, você poderá preparar [seus usuários para usar dispositivos](get-started-devices.md)e o usuário poderá iniciar o dispositivo e prosseguir com a experiência de instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="c4577-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









