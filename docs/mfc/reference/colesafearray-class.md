---
title: "COleSafeArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], safe"
  - "COleSafeArray class"
  - "ODBC, safe arrays"
  - "safe arrays"
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleSafeArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임의의 형식 및 차원 배열을 사용한 작업에 대 한 클래스입니다.  
  
## 구문  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleSafeArray::COleSafeArray](../Topic/COleSafeArray::COleSafeArray.md)|`COleSafeArray` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleSafeArray::AccessData](../Topic/COleSafeArray::AccessData.md)|배열의 데이터에 대 한 포인터를 검색합니다.|  
|[COleSafeArray::AllocData](../Topic/COleSafeArray::AllocData.md)|배열에 대해 메모리를 할당합니다.|  
|[COleSafeArray::AllocDescriptor](../Topic/COleSafeArray::AllocDescriptor.md)|안전 배열 설명자에 메모리를 할당합니다.|  
|[COleSafeArray::Attach](../Topic/COleSafeArray::Attach.md)|기존의 컨트롤을 제공  **변형** 배열에 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::Clear](../Topic/COleSafeArray::Clear.md)|모든 데이터를 원본으로 사용이 해제  **변형**.|  
|[COleSafeArray::Copy](../Topic/COleSafeArray::Copy.md)|기존 배열의 복사본을 만듭니다.|  
|[COleSafeArray::Create](../Topic/COleSafeArray::Create.md)|안전 배열을 만듭니다.|  
|[COleSafeArray::CreateOneDim](../Topic/COleSafeArray::CreateOneDim.md)|1 차원 만듭니다 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::Destroy](../Topic/COleSafeArray::Destroy.md)|기존 배열 소멸 시킵니다.|  
|[COleSafeArray::DestroyData](../Topic/COleSafeArray::DestroyData.md)|안전 배열에 데이터를 소멸 시킵니다.|  
|[COleSafeArray::DestroyDescriptor](../Topic/COleSafeArray::DestroyDescriptor.md)|안전 배열 설명자를 소멸 시킵니다.|  
|[COleSafeArray::Detach](../Topic/COleSafeArray::Detach.md)|분리 된  **변형** 배열에서 `COleSafeArray` 개체 \(데이터 없습니다 해제 되지 않도록\).|  
|[COleSafeArray::GetByteArray](../Topic/COleSafeArray::GetByteArray.md)|안전 배열로 내용을 복사 하는  [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](../Topic/COleSafeArray::GetDim.md)|배열의 차수를 반환합니다.|  
|[COleSafeArray::GetElement](../Topic/COleSafeArray::GetElement.md)|안전 배열의 단일 요소를 검색합니다.|  
|[COleSafeArray::GetElemSize](../Topic/COleSafeArray::GetElemSize.md)|크기를 바이트 단위로 안전 배열의 한 요소를 반환합니다.|  
|[COleSafeArray::GetLBound](../Topic/COleSafeArray::GetLBound.md)|안전 배열의 모든 차원에 대 한 하한값을 반환합니다.|  
|[COleSafeArray::GetOneDimSize](../Topic/COleSafeArray::GetOneDimSize.md)|1 차원에서 요소의 개수를 반환 합니다. `COleSafeArray` 개체입니다.|  
|[COleSafeArray::GetUBound](../Topic/COleSafeArray::GetUBound.md)|안전 배열의 모든 차원에 대해 상한을 반환합니다.|  
|[COleSafeArray::Lock](../Topic/COleSafeArray::Lock.md)|배열 잠금 횟수가 증가 하 고 배열의 데이터에 대 한 포인터 배열 설명자에 배치 합니다.|  
|[COleSafeArray::PtrOfIndex](../Topic/COleSafeArray::PtrOfIndex.md)|인덱싱된 요소에 대 한 포인터를 반환합니다.|  
|[COleSafeArray::PutElement](../Topic/COleSafeArray::PutElement.md)|단일 요소 배열에 할당합니다.|  
|[COleSafeArray::Redim](../Topic/COleSafeArray::Redim.md)|안전 배열의 최하위 \(가장 오른쪽\) 경계를 변경합니다.|  
|[COleSafeArray::ResizeOneDim](../Topic/COleSafeArray::ResizeOneDim.md)|요소는 1 차원 수가 변경 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::UnaccessData](../Topic/COleSafeArray::UnaccessData.md)|감소는 잠금 배열을 계산 하 고 검색 포인터를 무효로 만듭니다 `AccessData`.|  
|[COleSafeArray::Unlock](../Topic/COleSafeArray::Unlock.md)|잠금 횟수를 줄입니다 배열을 해제 하거나 크기를 조정할 수 있습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[COleSafeArray::operator LPCVARIANT](../Topic/COleSafeArray::operator%20LPCVARIANT.md)|액세스 하는 기본  **변형** 의 구조는 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::operator LPVARIANT](../Topic/COleSafeArray::operator%20LPVARIANT.md)|액세스 하는 기본  **변형** 의 구조는 `COleSafeArray` 개체입니다.|  
|[COleSafeArray::operator \=](../Topic/COleSafeArray::operator%20=.md)|복사 값으로는 `COleSafeArray` 개체 \(**SAFEARRAY**,  **변형**, `COleVariant`, 또는 `COleSafeArray` 배열\).|  
|[COleSafeArray::operator \=\=](../Topic/COleSafeArray::operator%20==.md)|두 개의 variant 배열을 비교 \(**SAFEARRAY**,  **변형**, `COleVariant`, 또는 `COleSafeArray` 배열\).|  
|[COleSafeArray::operator \<\<](../Topic/COleSafeArray::operator%20%3C%3C.md)|내용을 출력을 `COleSafeArray` 덤프 컨텍스트 개체입니다.|  
  
## 설명  
 `COleSafeArray`OLE에서 파생 된  **변형** 구조.  OLE  **SAFEARRAY** 멤버 함수를 통해 사용할 수 있는 `COleSafeArray`으로 바이트의 1 차원 배열에 대 한 특별히 멤버 함수 집합으로.  
  
## 상속 계층 구조  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)