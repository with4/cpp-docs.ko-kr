---
title: "CSimpleArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSimpleArray"
  - "ATL::CSimpleArray"
  - "CSimpleArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArray class"
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSimpleArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 단순 배열 관리를 위한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   class T,  
   class TEqual = CSimpleArrayEqualHelper< T >  
>   
class CSimpleArray  
```  
  
#### 매개 변수  
 `T`  
 배열에 저장 하는 데이터의 형식입니다.  
  
 `TEqual`  
 정의 하는 요소 형식에 대 한 일치 테스트는 성분 개체 `T`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSimpleArray::CSimpleArray](../Topic/CSimpleArray::CSimpleArray.md)|단순 배열에 대 한 생성자입니다.|  
|[CSimpleArray::~CSimpleArray](../Topic/CSimpleArray::~CSimpleArray.md)|단순 배열에 대 한 소멸자가 있습니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleArray::Add](../Topic/CSimpleArray::Add.md)|배열에 새 요소를 추가합니다.|  
|[CSimpleArray::Find](../Topic/CSimpleArray::Find.md)|배열에서 요소를 찾습니다.|  
|[CSimpleArray::GetData](../Topic/CSimpleArray::GetData.md)|배열에 저장 된 데이터에 대 한 포인터를 반환 합니다.|  
|[CSimpleArray::GetSize](../Topic/CSimpleArray::GetSize.md)|배열에 저장 된 요소를 반환 합니다.|  
|[CSimpleArray::Remove](../Topic/CSimpleArray::Remove.md)|배열에서 지정 된 요소를 제거합니다.|  
|[CSimpleArray::RemoveAll](../Topic/CSimpleArray::RemoveAll.md)|배열에서 모든 요소를 제거합니다.|  
|[CSimpleArray::RemoveAt](../Topic/CSimpleArray::RemoveAt.md)|배열에서 지정한 요소를 제거합니다.|  
|[CSimpleArray::SetAtIndex](../Topic/CSimpleArray::SetAtIndex.md)|배열에 지정 된 요소를 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CSimpleArray::operator](../Topic/CSimpleArray::operator.md)|배열에서 요소를 검색합니다.|  
|[CSimpleArray::operator \=](../Topic/CSimpleArray::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 `CSimpleArray`만들고 지정 된 형식의 모든 단순 배열, 관리에 대 한 메서드를 제공 합니다. `T`.  
  
 매개 변수는 `TEqual` 는 동등 함수 두 형식의 요소를 정의 하는 방법을 제공 `T`.  클래스와 유사한 만들어  [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), 같음 테스트는 지정 된 배열에 대 한 동작을 변경할 수 있습니다.  예를 들어, 포인터와 배열 다룰 때는 일치로 포인터를 참조 하는 값에 따라 정의 하는 데 유용한 할 수 있습니다.  기본 구현을 사용 하 여  **operator\=\(\)**.  
  
 둘 다 `CSimpleArray` 및  [CSimpleMap](../../atl/reference/csimplemap-class.md) 는 적은 수의 요소에 대 한 설계 되었습니다.  [CAtlArray](../../atl/reference/catlarray-class.md) 및  [CAtlMap](../../atl/reference/catlmap-class.md) 배열의 요소 수가 포함 된 경우에 사용 해야 합니다.  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 예제  
 [!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/CPP/csimplearray-class_1.cpp)]  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)