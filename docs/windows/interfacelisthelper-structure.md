---
title: "InterfaceListHelper 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceListHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceListHelper 구조체"
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceListHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### 매개 변수  
 `T0`  
 필요로 된 탬플릿 매개변수 0  
  
 `T1`  
 기본인 템플릿 매개 변수 1은 지정되지 않습니다.  
  
 `T2`  
 템플릿 매개 변수 2는 기본적으로 지정 되지 않습니다.세 번째 템플릿 매개 변수입니다.  
  
 `T3`  
 기본인 템플릿 매개 변수 3은 지정되지 않습니다.  
  
 `T4`  
 기본인 템플릿 매개 변수 4은 지정되지 않습니다.  
  
 `T5`  
 기본인 템플릿 매개 변수 5은 지정되지 않습니다.  
  
 `T6`  
 기본인 템플릿 매개 변수 6은 지정되지 않습니다.  
  
 `T7`  
 기본인 템플릿 매개 변수 7은 지정되지 않습니다.  
  
 `T8`  
 기본인 템플릿 매개 변수 8은 지정되지 않습니다.  
  
 `T9`  
 기본인 템플릿 매개 변수 9은 지정되지 않습니다.  
  
## 설명  
 InterfaceList 형식의 반복적으로 지정된 템플릿 매개 변수 인수를 적용하여 작성 합니다.  
  
 InterfaceListHelper 템플릿은 템플릿 매개 변수 `T0` 를 사용하여, 첫 번째 데이터를 정의하는 InterfaceList 구조를 선택한 다음 재귀적 멤버 나머지 모든 템플릿 매개 변수를 InterfaceListHelper 서식 파일에 적용합니다.  InterfaceListHelper는 나머지 템플릿 매개 변수가 없는 경우 중지 합니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`TypeT`|InterfaceList 형식에 대한 동의어|  
  
## 상속 계층  
 `InterfaceListHelper`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)