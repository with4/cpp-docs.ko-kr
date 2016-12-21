---
title: "CComSafeArray 클래스 | Microsoft Docs"
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
  - "CComSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArray 클래스"
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSafeArray 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 **SAFEARRAY** 구조체의 래퍼입니다.  
  
## 구문  
  
```  
template <  
   typename T,  
   VARTYPE _vartype = _ATL_AutomationType< T >::type  
>  
class CComSafeArray  
```  
  
#### 매개 변수  
 `T`  
 배열에 저장할 데이터의 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComSafeArray::CComSafeArray](../Topic/CComSafeArray::CComSafeArray.md)|생성자입니다.|  
|[CComSafeArray::~CComSafeArray](../Topic/CComSafeArray::~CComSafeArray.md)|소멸자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComSafeArray::Add](../Topic/CComSafeArray::Add.md)|하나 이상의 요소 또는 **SAFEARRAY** 구조체를 `CComSafeArray`에 추가합니다.|  
|[CComSafeArray::Attach](../Topic/CComSafeArray::Attach.md)|**SAFEARRAY** 구조체를 `CComSafeArray` 개체에 연결합니다.|  
|[CComSafeArray::CopyFrom](../Topic/CComSafeArray::CopyFrom.md)|**SAFEARRAY** 구조체의 내용을 `CComSafeArray` 개체에 복사합니다.|  
|[CComSafeArray::CopyTo](../Topic/CComSafeArray::CopyTo.md)|`CComSafeArray` 개체의 복사본을 만듭니다.|  
|[CComSafeArray::Create](../Topic/CComSafeArray::Create.md)|`CComSafeArray` 개체를 만듭니다.|  
|[CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)|`CComSafeArray` 개체를 제거합니다.|  
|[CComSafeArray::Detach](../Topic/CComSafeArray::Detach.md)|**SAFEARRAY**를 `CComSafeArray` 개체에서 분리합니다.|  
|[CComSafeArray::GetAt](../Topic/CComSafeArray::GetAt.md)|1차원 배열에서 단일 요소를 검색합니다.|  
|[CComSafeArray::GetCount](../Topic/CComSafeArray::GetCount.md)|배열의 요소 수를 반환합니다.|  
|[CComSafeArray::GetDimensions](../Topic/CComSafeArray::GetDimensions.md)|배열의 차원 수를 반환합니다.|  
|[CComSafeArray::GetLowerBound](../Topic/CComSafeArray::GetLowerBound.md)|배열의 지정된 차원에 대한 하한을 반환합니다.|  
|[CComSafeArray::GetSafeArrayPtr](../Topic/CComSafeArray::GetSafeArrayPtr.md)|`m_psa` 데이터 멤버의 주소를 반환합니다.|  
|[CComSafeArray::GetType](../Topic/CComSafeArray::GetType.md)|배열에 저장된 데이터의 형식을 반환합니다.|  
|[CComSafeArray::GetUpperBound](../Topic/CComSafeArray::GetUpperBound.md)|배열의 모든 차원에 대한 상한을 반환합니다.|  
|[CComSafeArray::IsSizable](../Topic/CComSafeArray::IsSizable.md)|`CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.|  
|[CComSafeArray::MultiDimGetAt](../Topic/CComSafeArray::MultiDimGetAt.md)|다차원 배열에서 단일 요소를 검색합니다.|  
|[CComSafeArray::MultiDimSetAt](../Topic/CComSafeArray::MultiDimSetAt.md)|다차원 배열의 요소 값을 설정합니다.|  
|[CComSafeArray::Resize](../Topic/CComSafeArray::Resize.md)|`CComSafeArray` 개체의 크기를 조정합니다.|  
|[CComSafeArray::SetAt](../Topic/CComSafeArray::SetAt.md)|1차원 배열의 요소 값을 설정합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CComSafeArray::operator LPSAFEARRAY](../Topic/CComSafeArray::operator%20LPSAFEARRAY.md)|**SAFEARRAY** 포인터에 값을 캐스팅합니다.|  
|[CComSafeArray::operator](../Topic/CComSafeArray::operator.md)|배열에서 요소를 검색합니다.|  
|[CComSafeArray::operator \=](../Topic/CComSafeArray::operator%20=.md)|대입 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComSafeArray::m\_psa](../Topic/CComSafeArray::m_psa.md)|이 데이터 멤버는 **SAFEARRAY** 구조체의 주소를 유지합니다.|  
  
## 설명  
 `CComSafeArray`는 [SAFEARRAY Data Type](http://msdn.microsoft.com/ko-kr/9ec8025b-4763-4526-ab45-390c5d8b3b1e) 클래스에 대한 래퍼를 제공합니다. 따라서 거의 모든 VARIANT 지원 형식의 1차원 및 다차원 배열을 쉽게 만들고 관리할 수 있습니다.  
  
 `CComSafeArray`는 프로세스 간의 배열 전달을 간소화할 뿐만 아니라 상한과 하한에 대해 배열 인덱스 값을 확인하여 추가 보안을 제공합니다.  
  
 `CComSafeArray`의 하한은 모든 사용자 정의 값에서 시작할 수 있지만 C\+\+를 통해 액세스하는 배열에서는 0을 하한으로 사용해야 합니다. Visual Basic과 같은 다른 언어에서는 다른 경계 값\(예: \-10~10\)을 사용할 수 있습니다.  
  
 `CComSafeArray` 개체를 만들려면 [CComSafeArray::Create](../Topic/CComSafeArray::Create.md)를 사용하고, 제거하려면 [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)를 사용합니다.  
  
 `CComSafeArray`는 VARIANT 데이터 형식의 다음 하위 집합을 포함할 수 있습니다.  
  
|VARTYPE|설명|  
|-------------|--------|  
|VT\_I1|char|  
|VT\_I2|short|  
|VT\_I4|int|  
|VT\_I4|long|  
|VT\_I8|longlong|  
|VT\_UI1|byte|  
|VT\_UI2|ushort|  
|VT\_UI4|uint|  
|VT\_UI4|ulong|  
|VT\_UI8|ulonglong|  
|VT\_R4|float|  
|VT\_R8|double|  
|VT\_DECIMAL|decimal pointer|  
|VT\_VARIANT|variant pointer|  
|VT\_CY|Currency 데이터 형식|  
  
## 요구 사항  
 **헤더:** atlsafe.h  
  
## 예제  
 [!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/CPP/ccomsafearray-class_1.cpp)]  
  
## 참고 항목  
 [SAFEARRAY Data Type](http://msdn.microsoft.com/ko-kr/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](../Topic/CComSafeArray::Create.md)   
 [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)   
 [Class Overview](../../atl/atl-class-overview.md)