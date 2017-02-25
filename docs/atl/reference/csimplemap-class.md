---
title: "CSimpleMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleMap"
  - "ATL.CSimpleMap"
  - "CSimpleMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMap class"
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CSimpleMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 단순 매핑 배열을 지원합니다.  
  
## 구문  
  
```  
  
      template <   
   class TKey,  
   class TVal,  
   class TEqual = CSimpleMapEqualHelper< TKey, TVal >   
>   
class CSimpleMap  
```  
  
#### 매개 변수  
 `TKey`  
 키 요소 형식입니다.  
  
 `TVal`  
 값 요소 형식입니다.  
  
 `TEqual`  
 정의 하는 요소 형식에 대 한 일치 테스트는 성분 개체 `T`.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CSimpleMap::\_ArrayElementType](../Topic/CSimpleMap::_ArrayElementType.md)|값 형식에 대 한 형식 정의입니다.|  
|[CSimpleMap::\_ArrayKeyType](../Topic/CSimpleMap::_ArrayKeyType.md)|키 형식에 대 한 형식 정의입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSimpleMap::CSimpleMap](../Topic/CSimpleMap::CSimpleMap.md)|생성자입니다.|  
|[CSimpleMap::~CSimpleMap](../Topic/CSimpleMap::~CSimpleMap.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleMap::Add](../Topic/CSimpleMap::Add.md)|키와 관련된 값 맵 배열에 추가합니다.|  
|[CSimpleMap::FindKey](../Topic/CSimpleMap::FindKey.md)|특정 키를 찾습니다.|  
|[CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)|특정 값을 찾습니다.|  
|[CSimpleMap::GetKeyAt](../Topic/CSimpleMap::GetKeyAt.md)|지정 된 키를 검색합니다.|  
|[CSimpleMap::GetSize](../Topic/CSimpleMap::GetSize.md)|항목에 매핑 배열을 반환합니다.|  
|[CSimpleMap::GetValueAt](../Topic/CSimpleMap::GetValueAt.md)|지정 된 값을 검색합니다.|  
|[CSimpleMap::Lookup](../Topic/CSimpleMap::Lookup.md)|지정 된 키와 연결 된 값을 반환 합니다.|  
|[CSimpleMap::Remove](../Topic/CSimpleMap::Remove.md)|키와 일치 하는 값을 제거합니다.|  
|[CSimpleMap::RemoveAll](../Topic/CSimpleMap::RemoveAll.md)|모든 키와 값을 제거합니다.|  
|[CSimpleMap::RemoveAt](../Topic/CSimpleMap::RemoveAt.md)|특정 키와 일치 하는 값을 제거합니다.|  
|[CSimpleMap::ReverseLookup](../Topic/CSimpleMap::ReverseLookup.md)|지정 된 값과 연결 된 키를 반환 합니다.|  
|[CSimpleMap::SetAt](../Topic/CSimpleMap::SetAt.md)|지정 된 키와 연결 된 값을 설정 합니다.|  
|[CSimpleMap::SetAtIndex](../Topic/CSimpleMap::SetAtIndex.md)|특정 키 및 값을 설정합니다.|  
  
## 설명  
 `CSimpleMap`단순 매핑 배열의 지정 된 형식의 모든 지원 `T`, 핵심 요소 및 관련된 값의 배열 순서가 지정 되지 않은 관리 합니다.  
  
 매개 변수는 `TEqual` 는 동등 함수 두 형식의 요소를 정의 하는 방법을 제공 `T`.  클래스와 유사한 만들어  [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), 같음 테스트는 지정 된 배열에 대 한 동작을 변경할 수 있습니다.  예를 들어, 포인터와 배열 다룰 때는 일치로 포인터를 참조 하는 값에 따라 정의 하는 데 유용한 할 수 있습니다.  기본 구현을 사용 하 여  **operator\=\=\(\)**.  
  
 둘 다 `CSimpleMap` 및  [CSimpleArray](../../atl/reference/csimplearray-class.md) 이전 ATL 호환 릴리스를 완벽 하 고 효율적인 컬렉션 구현으로 제공에 대 한 제공 하는  [CAtlArray](../../atl/reference/catlarray-class.md) 및  [CAtlMap](../../atl/reference/catlmap-class.md).  
  
 다른 맵 컬렉션에서는 ATL 및 MFC와 달리이 클래스 간단한 배열을 구현 되며 선형 검색 조회 검색 해야 합니다.  `CAtlMap`배열의 요소 수가 포함 되어 있는 경우 사용 해야 합니다.  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 예제  
 [!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/CPP/csimplemap-class_1.cpp)]  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)