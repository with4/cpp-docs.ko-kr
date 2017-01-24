---
title: "CByteArray Class | Microsoft Docs"
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
  - "CByteArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], byte"
  - "바이트 배열"
  - "CByteArray class"
  - "MFC collection classes, 바이트 배열"
ms.assetid: 53d4a512-657c-4187-9609-e3f5339a78e0
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CByteArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

바이트의 동적 배열을 지원합니다.  
  
## 구문  
  
```  
class CByteArray : public CObject  
```  
  
## Members  
 멤버 함수를 `CByteArray` 클래스의 멤버 함수와 유사  [CObArray](../../mfc/reference/cobarray-class.md).  이 유사성 때문에 사용할 수 있는 `CObArray` 멤버 함수 사양에 대 한 설명서를 참조 합니다.  볼 위치는 `CObject` 포인터가 함수 매개 변수 또는 반환 값으로 대체는  **바이트**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 예를 들어, 변환  
  
 `BYTE CByteArray::GetAt( int <nIndex> ) const;`  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|빈 배열을 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|배열의 끝에 요소를 추가합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|다른 배열 배열에 추가 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|다른 배열 배열에 복사 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|바이트 배열에 대 한 임시 참조를 반환합니다.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|현재 상한 위의 모든 사용 되지 않는 메모리를 해제합니다.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|지정 된 인덱스의 값을 반환합니다.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|이 배열의 요소 수를 가져옵니다.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|배열 요소에 액세스할 수 있습니다.  수  **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|이 배열의 요소 수를 가져옵니다.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|가장 큰 올바른 인덱스를 반환합니다.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|요소를 다른 배열의 모든 요소는 지정 된 인덱스에 삽입합니다.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|배열이 비어 있는지 확인 합니다.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|이 배열에서 모든 요소를 제거합니다.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|특정 인덱스에 있는 요소를 제거합니다.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|지정 된 인덱스 값으로 설정합니다. 배열 증가할 수 없습니다.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|지정 된 인덱스 값으로 설정합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|이 배열에 포함 될 수 있는 요소를 설정 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|설정 하거나 지정 된 인덱스에 있는 요소를 가져옵니다.|  
  
## 설명  
 `CByteArray`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  바이트 배열을 가진 오버 로드 된 삽입을 보관 저장 되어 있는 경우 \(**\<\<**\) 연산자와는 `Serialize` 멤버 함수가 각 요소입니다을 직렬화 합니다.  
  
> [!NOTE]
>  배열을 사용 하기 전에 사용 `SetSize` 크기를 설정 하 고 메모리를 할당 합니다.  사용 하지 않는 경우 `SetSize`, 배열에 요소를 추가 하면 자주 재할당 되 고 복사 될 수 있습니다.  자주 재할당 및 복사 비효율적입니다 및 메모리를 조각 낼 수 있습니다.  
  
 출력 배열의 개별 요소를 디버깅 해야 하는 경우의 깊이 설정의 `CDumpContext` 개체에 1 이상.  
  
 사용에 대 한 자세한 내용은 `CByteArray`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CByteArray`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)