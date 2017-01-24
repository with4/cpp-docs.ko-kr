---
title: "CStringArray Class | Microsoft Docs"
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
  - "CStringArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 문자열"
  - "CStringArray class"
  - "string arrays"
  - "문자열[C++], 컬렉션"
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CString](../../atl-mfc-shared/using-cstring.md) 개체 배열을 지원합니다.  
  
## 구문  
  
```  
class CStringArray : public CObject  
```  
  
## 멤버  
 `CStringArray`의 멤버 함수는 [CObArray](../../mfc/reference/cobarray-class.md) 클래스의 멤버 함수와 비슷합니다.  이처럼 두 함수가 비슷하므로 `CObArray` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다.  `CObject` 포인터가 반환 값으로 표시될 때마다 [CString](../../atl-mfc-shared/using-cstring.md) 포인터가 아닌 [CString](../../atl-mfc-shared/using-cstring.md) 개체를 대체합니다.  `CObject` 포인터가 함수 매개 변수로 사용될 때마다 `LPCTSTR`을 대체합니다.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 예를 들어 위의 코드는  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 및  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 위의 코드는 다음과 같이 변환됩니다.  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|빈 배열을 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|지정된 인덱스의 값을 반환합니다.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|배열의 요소에 대한 액세스를 허용합니다.  **NULL**일 수 있습니다.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|유효한 최대 인덱스를 반환합니다.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|배열이 비어 있는지를 확인합니다.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|이 배열의 모든 요소를 반환합니다.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|특정 인덱스의 요소를 제거합니다.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|이 배열에 포함된 요소의 수를 설정합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|  
  
## 설명  
 `CStringArray`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다.  오버로드된 삽입 연산자 또는 `Serialize` 멤버 함수를 사용하여 `CString` 개체 배열을 보관 파일에 저장하는 경우에는 각 요소가 차례로 serialize됩니다.  
  
> [!NOTE]
>  배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다.  `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다.  이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.  
  
 배열에 개별 문자열 요소의 덤프가 필요하면 덤프 컨텍스트의 수준을 1 이상으로 설정해야 합니다.  
  
 `CString` 배열을 삭제하거나 해당 요소를 제거하면 문자열 메모리가 적절하게 해제됩니다.  
  
 `CStringArray` 사용에 대한 자세한 내용은 [컬렉션](../../mfc/collections.md) 문서를 참조하세요.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringArray`  
  
## 요구 사항  
 **헤더:** afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)