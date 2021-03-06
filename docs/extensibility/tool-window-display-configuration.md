---
title: Tool-Fenster-Anzeigekonfiguration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, configuring
- tool windows, appearance
ms.assetid: 502a4926-bb83-473e-94e2-8e833c5f8b53
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 087fc8bc20b8ed70001b44ae06c614fad58c1439
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839699"
---
# <a name="tool-window-display-configuration"></a>Tool-Fenster-Anzeigekonfiguration
Wenn eine VSPackage ein Toolfenster, die Standardposition, Größe, andockstil und andere Informationen zur Sichtbarkeit registriert wird optional Werte angegeben werden. Weitere Informationen zum Tool-Fenster-Registrierung, finden Sie unter [Tool Windows in der Registrierung](../extensibility/tool-windows-in-the-registry.md)  

## <a name="window-display-information"></a>Anzeigeinformationen für Fenster  
 Grundlegende Anzeigekonfiguration ein Toolfenster werden in bis zu sechs optionalen Werte gespeichert:  

```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              (Default)       = reg_sz: <Package GUID>Name            = reg_sz: <name of tool window>Float           = reg_sz: <position>Style           = reg_sz: <dock style>Window          = reg_sz: <window GUID>Orientation     = reg_sz: <orientation>DontForceCreate = reg_dword: 0x00000000  
```  


| name | Typ | Daten | Beschreibung |
|-----------------|-----------| - | - |
| name | REG_SZ | "Kurzen Namen hier einfügen" | Ein kurzer Name, der das Toolfenster beschreibt. Nur für den Verweis in der Registrierung verwendet. |
| Float | REG_SZ | "X1, Y1, X2, Y2" | Vier durch Trennzeichen getrennte Werte. X1, Y1, ist die Koordinate der oberen linken Ecke des Toolfensters. X2, Y2 ist die Koordinate der unteren rechten Ecke. Alle Werte sind in Bildschirmkoordinaten. |
| Stil | REG_SZ | "MDI"<br /><br /> "Float"<br /><br /> "Verknüpft"<br /><br /> "Registerkarten"<br /><br /> "AlwaysFloat" | Ein Schlüsselwort, das Angeben der anfänglichen anzeigenzustand des Toolfensters.<br /><br /> "MDI" = MDI-Fensters angedockt.<br /><br /> "Float" = Gleitkommawert.<br /><br /> "Verknüpft" = verknüpft, die mit einem anderen Fenster (angegeben in den Fenster-Eintrag).<br /><br /> "Registerkarten" = in Kombination mit einem anderen Toolfenster.<br /><br /> "AlwaysFloat" = nicht angedockt werden.<br /><br /> Weitere Informationen finden Sie unter den folgenden Kommentarabschnitt. |
| Fenster | REG_SZ | *\<GUID &GT;* | Die GUID eines Fensters, das Toolfenster verknüpft oder im Registerformat werden kann. Die GUID möglicherweise gehört, um eine eigene Windows oder eines der Fenster in der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. |
| Ausrichtung | REG_SZ | "Left"<br /><br /> "Right"<br /><br /> "Top"<br /><br /> "Unten" | Finden Sie unter den folgenden Kommentarabschnitt. |
| DontForceCreate | REG_DWORD | 0 oder 1 | Wenn dieser Eintrag vorhanden ist und dessen Wert nicht 0 (null), wird das Fenster geladen, aber nicht sofort angezeigt. |

### <a name="comments"></a>Kommentare  
 Der Eintrag Ausrichtung definiert die Position, in dem das Toolfenster angedockt wird, wenn dessen eigener Titelleiste doppelgeklickt wird. Die Position ist relativ zum angegebenen Fensters im Eintrag im Fenster. Wenn der Style-Eintrag auf "Verknüpft" festgelegt ist, kann der Eintrag für die Ausrichtung "Left", "Right", "Top" und "Bottom" sein. Wenn der Style-Eintrag "Im Registerformat", der die Ausrichtung Eintrag "beibehalten werden sollen" oder "Rechte" und gibt an, wo die Registerkarte hinzugefügt wird. Wenn der Style-Eintrag ist "Float", wird das Toolfenster zuerst verschoben. Wenn auf die Titelleiste doppelgeklickt wird, gelten die Ausrichtung und Fenster-Einträge und das Fenster verwendet das Format "Im Registerformat". Wenn der Style-Eintrag "AlwaysFloat" ist, kann nicht das Toolfenster angedockt werden. Wenn der Style-Eintrag "MDI" ist, wird das Toolfenster mit der MDI-Bereich verknüpft ist, und der Eintrag im Fenster wird ignoriert.  

### <a name="example"></a>Beispiel  

```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {A0C5197D-0AC7-4B63-97CD-8872A789D233}\  
              (Default)       = reg_sz: {DA9FB551-C724-11D0-AE1F-00A0C90FFFC3}  
              DontForceCreate = reg_dword: 0x00000000  
              Float           = reg_sz: 100,100,450,300  
              Name            = reg_sz: Bookmarks  
              Orientation     = reg_sz: Left  
              Style           = reg_sz: Tabbed  
              Window          = reg_sz: {34E76E81-EE4A-11D0-00A0C90FFFC3}  
```  

## <a name="tool-window-visibility"></a>Toolfenstersichtbarkeit  
 Werte in den optional Sichtbarkeit Unterschlüssel bestimmen die sichtbarkeitseinstellungen des Toolfensters. Die Namen der Werte werden verwendet, um die GUIDs der Befehle zu speichern, die die Sichtbarkeit des Fensters zu erfordern. Wenn der Befehl ausgeführt wird, garantiert die IDE an, dass das Toolfenster erstellt und sichtbar gemacht wird.  

```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              Visibility\  
                (Default) = reg_sz:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_sz:  
```  

|name|Typ|Daten|Beschreibung|  
|----------|----------|----------|-----------------|  
|(Standard)|REG_SZ|Keiner|Lassen Sie leer.|  
|*\<GUID &GT;*|REG_DWORD-Wert oder REG_SZ|0 oder eine beschreibende Zeichenfolge.|Dies ist optional. Der Eintrag Name muss die GUID eines Befehls müssen die Sichtbarkeit. Der Wert enthält lediglich eine informative Zeichenfolge. Der Wert in der Regel ist eine `reg_dword` auf 0 festgelegt.|  

### <a name="example"></a>Beispiel  

```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {EEFA5220-E298-11D0-8F78-00A0C9110057}\  
              Visibility\  
                (Default) = reg_sz:  
                {93694fa0-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
                {9DA22B82-6211-11d2-9561-00600818403B} = reg_dword: 0x00000000  
                {adfc4e66-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
```  

## <a name="see-also"></a>Siehe auch  
 [VSPackages](../extensibility/internals/vspackages.md)