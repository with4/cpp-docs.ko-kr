---
title: "CMapPtrToPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapPtrToPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapPtrToPtr class"
  - "컬렉션 클래스, pointer mapping"
  - "pointer mapping class"
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMapPtrToPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Void 포인터를 void 포인터에 의해 키의 지도 지원 합니다.  
  
## 구문  
  
```  
class CMapPtrToPtr : public CObject  
```  
  
## Members  
 멤버 함수를 `CMapPtrToPtr` 클래스의 멤버 함수와 유사  [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  이 유사성 때문에 사용할 수 있는 `CMapStringToOb` 멤버 함수 사양에 대 한 설명서를 참조 합니다.  볼 위치는 `CObject` 포인터는 함수 매개 변수 또는 반환 값에 대 한 포인터를 대체 `void`.  볼 위치는 `CString` 또는  **const** 포인터를 `char` 에 대 한 포인터를 함수 매개 변수 또는 반환 값으로 대체 `void`.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 예를 들어, 변환  
  
 `BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMapStringToOb::CMapStringToOb](../Topic/CMapStringToOb::CMapStringToOb.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMapStringToOb::GetCount](../Topic/CMapStringToOb::GetCount.md)|이 지도에서 요소의 개수를 반환합니다.|  
|[CMapStringToOb::GetHashTableSize](../Topic/CMapStringToOb::GetHashTableSize.md)|현재 해시 테이블에서 요소를 결정합니다.|  
|[CMapStringToOb::GetNextAssoc](../Topic/CMapStringToOb::GetNextAssoc.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CMapStringToOb::GetSize](../Topic/CMapStringToOb::GetSize.md)|이 지도에서 요소의 개수를 반환합니다.|  
|[CMapStringToOb::GetStartPosition](../Topic/CMapStringToOb::GetStartPosition.md)|첫 번째 요소를 반환합니다.|  
|[CMapStringToOb::HashKey](../Topic/CMapStringToOb::HashKey.md)|지정 된 키의 해시 값을 계산합니다.|  
|[CMapStringToOb::InitHashTable](../Topic/CMapStringToOb::InitHashTable.md)|해시 테이블을 초기화합니다.|  
|[CMapStringToOb::IsEmpty](../Topic/CMapStringToOb::IsEmpty.md)|빈 지도 조건 \(요소\)에 대해 테스트 합니다.|  
|[CMapStringToOb::Lookup](../Topic/CMapStringToOb::Lookup.md)|Void 포인터는 void 포인터 키를 기반으로 찾습니다.  포인터 값을 않는 가리키는 엔터티 키 비교에 사용 됩니다.|  
|[CMapStringToOb::LookupKey](../Topic/CMapStringToOb::LookupKey.md)|지정 된 키 값과 연결 된 키에 대 한 참조를 반환 합니다.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|이 지도에서 모든 요소를 제거합니다.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|키에 지정 된 요소를 제거 합니다.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|지도에 요소를 삽입합니다. 일치 하는 키가 없는 경우 기존 요소를 대체 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|지도에 요소를 삽입 합니다.\-운영자 대체 `SetAt`.|  
  
## 설명  
 `CMapPtrToPtr`통합은 `IMPLEMENT_DYNAMIC` 런타임 형식 액세스 및 덤프를 지원 하기 위해 매크로 `CDumpContext` 개체.  개별 지도 요소 \(포인터 값\)의 덤프 해야 하는 경우 1 이상으로 깊이 덤프 컨텍스트를 설정 해야 합니다.  
  
 포인터\-포인터 맵은 직렬화 할 수 없습니다.  
  
 경우는 `CMapPtrToPtr` 개체를 삭제 하거나 해당 요소를 제거할 경우의 포인터만 제거 되 고 엔터티 참조는 없습니다.  
  
 에 대 한 자세한 내용은 `CMapPtrToPtr`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapPtrToPtr`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)