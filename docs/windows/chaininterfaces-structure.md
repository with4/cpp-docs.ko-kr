---
title: "ChainInterfaces 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChainInterfaces 구조체"
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스 Id 집합에 적용할 수 있는 확인 및 초기화 함수를 지정 합니다.  
  
## 구문  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### 매개 변수  
 `I0`  
 \(필요로 된\) 인터페이스 ID 0.  
  
 `I1`  
 \(필요로 된\) 인터페이스 ID 1.  
  
 `I2`  
 \(선택 사항\) 인터페이스 ID 2입니다.  
  
 `I3`  
 \(선택 사항\) 인터페이스 ID 3입니다.  
  
 `I4`  
 \(선택 사항\) 인터페이스 ID 4입니다.  
  
 `I5`  
 \(선택 사항\) 인터페이스 ID 5입니다.  
  
 `I6`  
 \(선택 사항\) 인터페이스 ID 6입니다.  
  
 `I7`  
 \(선택 사항\) 인터페이스 ID 7입니다.  
  
 `I8`  
 \(선택 사항\) 인터페이스 ID 8입니다.  
  
 `I9`  
 \(선택 사항\) 인터페이스 ID 9입니다.  
  
 `DerivedType`  
 파생 형식  
  
 `BaseType`  
 파생된 형식의 기본 형식입니다.  
  
 `hasImplements`  
 `true` 일경우, [구현](../windows/implements-structure.md) 구조체로부터 도출되지 않은 클래스를 사용하여 부울 값은 [Mixln](../windows/mixin-structure.md) 구조체를 사용할 수 없게 합니다.  
  
## 멤버  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[ChainInterfaces::CanCastTo 메서드](../windows/chaininterfaces-cancastto-method.md)|지정된 인터페이스 ID를 ChainInterface 탬플릿 매개변수에 의해 정의된 각각의 특수화를 캐스팅할 수 있는지 여부를 나타냅니다.|  
|[ChainInterfaces::CastToUnknown 메서드](../windows/chaininterfaces-casttounknown-method.md)|IUnknown 에대한 포인터에 대한 `I0` 템플릿 매개변수에 의해 정의된 형식의 인터페이스 포인터를 캐스팅합니다.|  
|[ChainInterfaces::FillArrayWithIid 메서드](../windows/chaininterfaces-fillarraywithiid-method.md)|지정된 인터페이스 IDs의 배열에서 지정된 위치에서 `I0` 템플릿 매개변수에 의해 정의된 인터페이스 ID를 저장합니다.|  
|[ChainInterfaces::Verify 메서드](../windows/chaininterfaces-verify-method.md)|IUnknown 및\/또는 IInspectable로부터 상속받은 `I9` 를 통하여 템플릿 매개변수 `I0` 에 의해 정의된 각각의 인터페이스를 확인합니다. `I9`을 통해, `I0` 은 `I1` 을 상속받습니다.|  
  
### 보호 된 상수  
  
|Name|설명|  
|----------|--------|  
|[ChainInterfaces::IidCount 상수](../windows/chaininterfaces-iidcount-constant.md)|인터페이스 ID의 총 수는 `I9` 를 통한 인터페이스에서 템플릿 매개변수 `I0` 로 지정됨을 포함합니다.|  
  
## 상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)