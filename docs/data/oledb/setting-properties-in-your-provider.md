---
title: 공급자에 속성 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5d43e452d0fffcb4dc6eddcae722f8056dbd39dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109289"
---
# <a name="setting-properties-in-your-provider"></a>공급자에 속성 설정
원하는 속성에 대 한 속성 그룹과 속성 ID를 찾습니다. 자세한 내용은 참조 [OLE DB 속성](https://msdn.microsoft.com/en-us/library/ms722734.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 마법사에서 생성 하는 공급자 코드에서 속성 그룹에 해당 하는 속성 매핑이 두를 찾습니다. 속성 그룹의 이름을 일반적으로 개체의 이름에 해당합니다. 명령 또는 행 집합에서 명령 및 행 집합 속성을 확인할 수 있습니다. 데이터 원본 개체에 데이터 원본 및 초기화 속성을 찾을 수 있습니다.  
  
 추가 속성 맵에 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) 매크로입니다. PROPERTY_INFO_ENTRY_EX는 4 개의 매개 변수가 사용 됩니다.  
  
-   사용자 속성에 해당 하는 속성 ID입니다. 속성 이름의 앞에서 처음 7 자 ("DBPROP_")를 제거 해야 합니다. 추가 하려는 경우 등 **가 DBPROP_MAXROWS**, 전달 `MAXROWS` 첫 번째 요소로 합니다. 이 속성은 사용자 지정 속성을 하는 경우 전체 GUID 이름을 전달 (예를 들어 `DBMYPROP_MYPROPERTY`).  
  
-   Variant 형식의 속성 (에서 [OLE DB 속성](https://msdn.microsoft.com/en-us/library/ms722734.aspx) 에 *OLE DB Programmer's Reference*). 입력는 **VT_** 형식 (예: `VT_BOOL` 또는 `VT_I2`) 데이터 형식에 해당 하 합니다.  
  
-   읽기 및 쓰기 가능한 속성 인지 및 속해 있는 그룹을 나타내는 플래그입니다. 예를 들어 다음 코드는 행 집합 그룹에 속하는 읽기/쓰기 속성을 나타냅니다.  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   속성의 기본 값입니다. 이렇게 할 **VARIANT_FALSE** 부울에 대 한 입력 또는 정수 형식에 대 한 예를 들어 0입니다. 속성 변경 하지 않으면이 값을 있습니다.  
  
    > [!NOTE]
    >  일부 속성은 연결 되어 책갈피나 업데이트와 같은 다른 속성에 있습니다. 하나의 속성이 true로 설정 하는 소비자를 다른 속성 설정 해야 합니다. OLE DB 공급자 템플릿이 메서드를 통해 지원 [cutlprops:: Onpropertychanged](../../data/oledb/cutlprops-onpropertychanged.md)합니다.  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB 공급자가 무시 되는 속성  
 Microsoft OLE DB 공급자는 OLE DB 속성인을 무시합니다.  
  
-   **가 DBPROP_MAXROWS** 읽기 전용 공급자에 대해서만 작동 (즉, 여기서 DBPROP_IRowsetChange 및 DBPROP_IRowsetUpdate가 false); 그렇지 않으면이 속성은 지원 되지 않습니다.  
  
-   **DBPROP_MAXPENDINGROWS** 무시 되는 공급자는 한계를 지정 합니다.  
  
-   **DBPROP_MAXOPENROWS** 무시 되는 공급자는 한계를 지정 합니다.  
  
-   **DBPROP_CANHOLDROWS** 무시 되는 공급자는 한계를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)