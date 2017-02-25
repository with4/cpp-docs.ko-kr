---
title: "CMapWordToOb Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapWordToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapWordToOb class"
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMapWordToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지도를 지 원하는 `CObject` 포인터를 16 비트 단어를 입력 합니다.  
  
## 구문  
  
```  
class CMapWordToOb : public CObject  
```  
  
## Members  
 멤버 함수를 `CMapWordToOb` 클래스의 멤버 함수와 유사  [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  이 유사성 때문에 사용할 수 있는 `CMapStringToOb` 멤버 함수 사양에 대 한 설명서를 참조 합니다.  볼 위치는 `CString` 또는  **const** 포인터를 `char` 함수 매개 변수 또는 반환 값으로 대체  **단어**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 예를 들어, 변환  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  오버 로드 된 커서는 보관 하는 맵이 저장 된 경우 각 요소에서 serialize 될 \(**\<\<**\) 연산자와는 `Serialize` 멤버 함수입니다.  
  
 개별 덤프 해야 하는 경우  **단어**\-`CObject` 요소를 설정 해야 심도 덤프 컨텍스트를 1 이상으로 합니다.  
  
 경우는 `CMapWordToOb` 개체를 삭제 하거나이 때 해당 요소 제거는 `CObject` 포인터가 제거 됩니다.  참조 개체는 `CObject` 포인터 소멸 되지 않습니다.  
  
 에 대 한 자세한 내용은 `CMapWordToOb`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToOb`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)