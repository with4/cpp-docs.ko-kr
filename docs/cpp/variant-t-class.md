---
title: "_variant_t 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Variant"
  - "_variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t 클래스"
  - "_variant_t 클래스, 멤버 함수"
  - "_variant_t 클래스, 연산자"
  - "VARIANT 개체"
  - "VARIANT 개체, COM 캡슐화"
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _variant_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 `_variant_t` 개체는 `VARIANT` 데이터 형식을 캡슐화합니다.  클래스는 리소스 할당 및 할당 해제를 관리하고 **VariantInit** 및 **VariantClear** 으로 적절하게 함수 호출을 합니다.  
  
### 생성  
  
|||  
|-|-|  
|[\_variant\_t](../cpp/variant-t-variant-t.md)|`_variant_t` 개체를 생성합니다.|  
  
### 작업  
  
|||  
|-|-|  
|[연결](../cpp/variant-t-attach.md)|**VARIANT** 개체를 `_variant_t` 개체에 연결합니다.|  
|[Clear](../cpp/variant-t-clear.md)|캡슐화된 **VARIANT** 개체를 지웁니다.|  
|[ChangeType](../cpp/variant-t-changetype.md)|`_variant_t` 개체의 형식을 지정된 **VARTYPE**으로 변경합니다.|  
|[분리](../cpp/variant-t-detach.md)|캡슐화된 **VARIANT** 개체를 이 `_variant_t` 개체에서 분리합니다.|  
|[SetString](../cpp/variant-t-setstring.md)|이 `_variant_t` 개체에 문자열을 할당합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[Operator \=](../cpp/variant-t-operator-equal.md)|기존 `_variant_t` 개체에 새 값을 할당합니다.|  
|[operator \=\=, \!\=](../cpp/variant-t-relational-operators.md)|두 `_variant_t` 개체가 같음 또는 같지 않음을 비교합니다.|  
|[추출기](../cpp/variant-t-extractors.md)|캡슐화된 **VARIANT** 개체에서 데이터를 추출합니다.|  
  
## Microsoft 전용 종료  
  
## 요구 사항  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib 또는 comsuppwd.lib\(자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 참조\)  
  
## 참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)