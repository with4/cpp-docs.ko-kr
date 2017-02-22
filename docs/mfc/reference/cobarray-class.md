---
title: "CObArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CObArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 개체 형식"
  - "배열[C++], 포인터"
  - "CObArray class"
  - "개체 배열, CObArray class"
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CObArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

배열을 지 원하는 `CObject` 포인터.  
  
## 구문  
  
```  
class CObArray : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|빈 배열을 생성 `CObject` 포인터.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|배열의 끝에 요소를 추가합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|다른 배열 배열에 추가 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|다른 배열 배열에 복사 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|임시 참조 배열 내의 요소 포인터를 반환합니다.|  
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
 이러한 개체 배열을 C 배열과 비슷한 이지만 동적으로 축소 하 고 필요에 따라 커질 수 있습니다.  
  
 배열 인덱스는 항상 0 위치에서 시작합니다.  상한 수정 또는 확장 과거 현재 바인딩 요소를 추가 하면 배열 허용 여부를 결정할 수 있습니다.  일부 요소가 null 인 경우에 상한에 연속적으로 메모리를 할당 합니다.  
  
 Win32에서의 크기는 `CObArray` 개체에 사용 가능한 메모리로 제한 됩니다.  
  
 C 배열의 액세스 때와 마찬가지로 `CObArray` 인덱스 요소 상수 이며 배열 크기에 독립적입니다.  
  
 `CObArray`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  배열의 경우 `CObject` 포인터 저장 보관, 오버 로드 된 삽입 연산자 또는 사용 하는 `Serialize` 각 멤버 함수 `CObject` 배열 인덱스와 함께 요소를 직렬화, 결과적으로.  
  
 개별 덤프 해야 하는 경우 `CObject` 배열에서 요소를 깊이를 설정 해야 합니다의 `CDumpContext` 1 이상의 개체.  
  
 경우는 `CObArray` 개체가 삭제 되거나 때 요소 제거만 `CObject` 포인터 제거, 오브젝트가 참조.  
  
> [!NOTE]
>  배열을 사용 하기 전에 사용 `SetSize` 크기를 설정 하 고 메모리를 할당 합니다.  사용 하지 않는 경우 `SetSize`, 배열에 요소를 추가 하면 자주 재할당 되 고 복사 될 수 있습니다.  자주 재할당 및 복사 비효율적입니다 및 메모리를 조각 낼 수 있습니다.  
  
 배열 클래스 파생 목록 파생 비슷합니다.  에 특수 목록 클래스의 파생에 대 한 자세한 내용은  [컬렉션](../../mfc/collections.md).  
  
> [!NOTE]
>  사용 해야는 `IMPLEMENT_SERIAL` 매크로 배열을 serialize 하려는 경우 파생된 클래스의 구현에서입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStringArray Class](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CByteArray Class](../../mfc/reference/cbytearray-class.md)   
 [CWordArray Class](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray Class](../../mfc/reference/cdwordarray-class.md)