<!-- ## Provision Favorites -->
>*Supported versions: Microsoft Edge on Windows 10, version 1511 or later*<br>
>*Default setting:  Disabled or not configured (Customizable)*

[!INCLUDE [provision-favorites-shortdesc](../shortdesc/provision-favorites-shortdesc.md)]

>[!IMPORTANT]
>Enable only this policy or the Keep favorites in sync between Internet Explorer and Microsoft Edge policy. If you enable both, Microsoft Edge prevents users from syncing their favorites between the two browsers.

### Allowed values

|Group Policy  |Description |Most restricted |
|---|---|:---:|
|Disabled or not configured<br>**(default)** |Default list of favorites not defined in Microsoft Edge. In this case, the Favorites list is customizable, such as adding folders, or adding and removing favorites. | |
|Enabled |Define a default list of favorites in Microsoft Edge. In this case, the Save a Favorite, Import settings, and context menu options (such as Create a new folder) are turned off.<p>To define a default list of favorites, do the following:<ol><li>In the upper-right corner of Microsoft Edge, click the ellipses (**...**) and select **Settings**.</li><li>Click **Import from another browser**, click **Export to file**, and save the file.</li><li>In the **Options** section of the Group Policy Editor, provide the location that points the file with the list of favorites to provision.  Specify the URL as: <ul><li>HTTP location: "SiteList"=http://localhost:8080/URLs.html</li><li>Local network: "SiteList"="\network\shares\URLs.html"</li><li>Local file: "SiteList"=file:///c:\Users\\Documents\URLs.html</li></ul></li></ol> |![Most restricted value](../images/check-gn.png) | 
---

### Configuration combinations
| **Keep favorites in sync between IE and Microsoft Edge** | **Provision Favorites** | **Outcome** |
| --- | --- | --- |
| Disabled or not configured (default) | Disabled or not configured (default) | **Turned off/not syncing**. Microsoft Edge prevents users from syncing their favorites. |
| Enabled (turned on/syncing) | Disabled or not configured (default) | **Turned on/syncing**. Syncs favorites between Internet Explorer and Microsoft Edge. |
| Enabled (turned on/syncing) | Enabled (provision list of favorites) | **Turned off/not syncing**. Microsoft Edge prevents users from syncing their favorites. |
| Disabled or not configured (default) | Enabled (provision list of Favorites) | **Turned on/syncing**. Syncs favorites between Internet Explorer and Microsoft Edge. |
---

### ADMX info and settings
#### ADMX info
- **GP English name:** Provision Favorites
- **GP name:** ConfiguredFavorites
- **GP element:** ConfiguredFavoritesPrompt
- **GP path:** Windows Components/Microsoft Edge
- **GP ADMX file name:** MicrosoftEdge.admx

#### MDM settings
- **MDM name:** Browser/[ProvisionFavorites](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-browser#browser-provisionfavorites)
- **Supported devices:** Desktop
- **URI full path:** ./Vendor/MSFT/Policy/Config/Browser/ProvisionFavorites 
- **Data type:** String

#### Registry settings
- **Path:** HLKM\Software\Policies\Microsoft\MicrosoftEdge\Favorites
- **Value name:** ConfiguredFavorites
- **Value type:** REG_SZ

### Related policies
[Keep favorites in sync between Internet Explorer and Microsoft Edge](../available-policies.md#keep-favorites-in-sync-between-internet-explorer-and-microsoft-edge): [!INCLUDE [keep-favorites-in-sync-between-ie-and-edge-shortdesc](../shortdesc/keep-favorites-in-sync-between-ie-and-edge-shortdesc.md)]

<hr>