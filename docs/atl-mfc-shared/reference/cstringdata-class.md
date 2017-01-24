---
title: "CStringData Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringData class"
  - "shared classes, CStringData"
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringData Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 문자열 개체의 데이터를 나타냅니다.  
  
## 구문  
  
```  
  
struct CStringData  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[AddRef](../Topic/CStringData::AddRef.md)|문자열 데이터 개체의 참조 횟수를 증가 시킵니다.|  
|[data](../Topic/CStringData::data.md)|문자 데이터의 문자열 개체를 검색합니다.|  
|[IsLocked](../Topic/CStringData::IsLocked.md)|연결 된 문자열 개체의 버퍼 잠겨 있는지 여부를 결정 합니다.|  
|[IsShared](../Topic/CStringData::IsShared.md)|현재 연결 된 문자열 개체의 버퍼 공유 하는 경우를 결정 합니다.|  
|[잠금](../Topic/CStringData::Lock.md)|연결 된 문자열 개체의 버퍼를 잠급니다.|  
|[Release](../Topic/CStringData::Release.md)|지정 된 string 개체를 해제합니다.|  
|[잠금 해제](../Topic/CStringData::Unlock.md)|연결된 문자열 개체의 버퍼의 잠금을 해제 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[nAllocLength](../Topic/CStringData::nAllocLength.md)|할당 된 데이터의 길이가 `XCHAR`s \(종료 null\) 포함 안|  
|[nDataLength](../Topic/CStringData::nDataLength.md)|현재 사용 되는 데이터의 길이가 `XCHAR`s \(종료 null\) 포함 안|  
|[nRefs](../Topic/CStringData::nRefs.md)|개체의 현재 참조 개수|  
|[pStringMgr](../Topic/CStringData::pStringMgr.md)|이 string 개체의 문자열 관리자에 대 한 포인터입니다.|  
  
## 설명  
 이 클래스는 사용자 지정 문자열 관리자 구현 개발자가만 사용 해야 합니다.  사용자 지정 문자열 관리자에 대 한 자세한 내용은  [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 이 클래스는 다양 한 종류의 정보와 같은 높은 문자열 개체 관련 데이터 캡슐화  [CStringT](../../atl-mfc-shared/reference/cstringt-class.md),  [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), 또는  [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) 개체입니다.  모든 상위 문자열 개체를 해당 연결에 대 한 포인터 포함 `CStringData` 개체를 여러 문자열 개체가 동일한 문자열 데이터 개체를 가리키도록 합니다.  이 관계에서 참조 횟수가 표시 됩니다 \(`nRefs`\)에 `CStringData` 개체입니다.  
  
> [!NOTE]
>  경우에 따라 문자열 형식 \(같은  **CFixedString**\) 둘 이상의 상위 문자열 개체와 문자열 데이터 개체를 공유 하지 않습니다.  이 대 한 자세한 내용은  [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 이 데이터의 구성 됩니다.  
  
-   메모리 관리자 \(형식의  [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)\)는 문자열입니다.  
  
-   현재 길이 \([nDataLength](../Topic/CStringData::nDataLength.md)\)는 문자열입니다.  
  
-   할당 된 길이 \([nAllocLength](../Topic/CStringData::nAllocLength.md)\)는 문자열입니다.  성능상의 이유로이 현재 문자열 길이에서 다를 수 있습니다.  
  
-   참조 횟수가 \([nRefs](../Topic/CStringData::nRefs.md)\)에 `CStringData` 개체입니다.  이 값이 동일한 문자열 객체를 공유 하는 결정 하는 데 사용 됩니다 `CStringData` 개체입니다.  
  
-   실제 문자 버퍼 \([데이터](../Topic/CStringData::data.md)\)는 문자열입니다.  
  
    > [!NOTE]
    >  문자열 개체의 실제 문자 버퍼 문자열 관리자가 할당 되 고 추가 되는 `CStringData` 개체입니다.  
  
## 요구 사항  
 **헤더:** atlsimpstr.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)