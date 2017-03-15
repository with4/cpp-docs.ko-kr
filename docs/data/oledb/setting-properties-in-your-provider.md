---
title: "공급자에 속성 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 속성"
  - "속성[C++], OLE DB 공급자"
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 공급자에 속성 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

원하는 속성의 속성 그룹과 속성 ID를 찾습니다.  자세한 내용은 *OLE DB Programmer's Reference*의 [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx)를 참조하십시오.  
  
 마법사가 생성한 공급자 코드에서 속성 그룹에 해당하는 속성 맵을 찾습니다.  속성 그룹의 이름은 일반적으로 개체 이름과 일치합니다.  명령과 행 집합 속성은 명령이나 행 집합에서 찾을 수 있고, 데이터 소스와 초기화 속성은 데이터 소스 개체에서 찾을 수 있습니다.  
  
 속성 맵에 [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md) 매크로를 추가합니다.  PROPERTY\_INFO\_ENTRY\_EX에는 다음 네 개의 매개 변수가 있습니다.  
  
-   속성에 해당하는 속성 ID.  속성 이름 앞 부분에서 처음 7자\("DBPROP\_"\)를 제거해야 합니다.  예를 들어, **DBPROP\_MAXROWS**를 추가하려면 `MAXROWS`를 첫 번째 요소로 전달합니다.  사용자 지정 속성일 경우에는 전체 GUID 이름\(예: `DBMYPROP_MYPROPERTY`\)을 전달합니다.  
  
-   속성의 variant 형식\(*OLE DB Programmer's Reference*의 [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx) 참조\).  데이터 형식에 해당하는 **VT\_** type\(예: `VT_BOOL` 또는 `VT_I2`\)을 입력합니다.  
  
-   속성이 읽기 가능인지 쓰기 가능인지와 속성이 속하는 그룹을 표시하는 플래그.  예를 들어, 다음 코드는 행 집합 그룹에 속하는 읽기\/쓰기 속성을 표시합니다.  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   속성의 기준 값입니다.  예를 들어, 이 값은 부울 형식일 경우에는 **VARIANT\_FALSE**이고 정수 형식일 경우에는 0입니다.  변경 사항이 없으면 속성은 기준 값을 갖습니다.  
  
    > [!NOTE]
    >  일부 속성은 책갈피나 업데이트와 같은 다른 속성에 연결되어 있습니다.  소비자가 한 속성을 true로 설정하면 다른 속성도 설정해야 합니다.  OLE DB 공급자 템플릿은 [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md) 메서드를 통해 이를 지원합니다.  
  
## Microsoft OLE DB 공급자가 무시하는 속성  
 Microsoft OLE DB 공급자는 다음과 같은 OLE DB 속성을 무시합니다.  
  
-   **DBPROP\_MAXROWS** 는 읽기 전용 공급자\(DBPROP\_IRowsetChange 및 DBPROP\_IRowsetUpdate가 false인 경우\)에 대해서만 작동됩니다. 다른 경우에는 이 속성이 지원되지 않습니다.  
  
-   **DBPROP\_MAXPENDINGROWS**는 무시됩니다. 공급자는 한계를 지정합니다.  
  
-   **DBPROP\_MAXOPENROWS**는 무시됩니다. 공급자는 한계를 지정합니다.  
  
-   **DBPROP\_CANHOLDROWS**는 무시됩니다. 공급자는 한계를 지정합니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)