---
title: "CMapStringToOb Class | Microsoft Docs"
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
  - "CMapStringToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToOb class"
  - "컬렉션 클래스, string mapping"
  - "문자열[C++], class for mapping"
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고유 매핑하는 사전 컬렉션 클래스 `CString` 개체에 `CObject` 포인터.  
  
## 구문  
  
```  
class CMapStringToOb : public CObject  
```  
  
## Members  
  
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
 삽입 한 후에 `CString`\-`CObject*` 쌍 \(요소\)에 지도 효율적으로 검색 하거나 문자열을 사용 하는 쌍을 삭제 또는 `CString` 의 키 값.  맵의 모든 요소를 반복할 수 있습니다.  
  
 형식의 변수에  **위치** 대체 항목 액세스 모든 맵 변형에서 사용 됩니다.  사용할 수 있는  **위치** 맵을 통해 반복 하 고 항목을 "기억" 할.  이 반복이 키 값으로 순차적입니다 생각 합니다. 그렇지 않습니다.  검색 된 요소의 시퀀스는 결정 되지 않았습니다.  
  
 `CMapStringToOb`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  오버 로드 된 커서는 보관 하는 맵이 저장 된 경우 각 요소에서 serialize 될 \(**\<\<**\) 연산자와는 `Serialize` 멤버 함수입니다.  
  
 지도에서 개별 요소의 진단 덤프 해야 하는 경우 \(의 `CString` 값 및 `CObject` 내용을\), 덤프 컨텍스트 깊이가 1 이상으로 설정 해야 합니다.  
  
 때는 `CMapStringToOb` 개체를 삭제 하거나이 때 해당 요소 제거는 `CString` 개체와 `CObject` 포인터가 제거 됩니다.  참조 개체는 `CObject` 포인터 소멸 되지 않습니다.  
  
 맵 클래스 파생 목록 파생 비슷합니다.  문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md) 예는 특수 목록 클래스를 파생 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString Class](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb Class](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)