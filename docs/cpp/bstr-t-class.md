---
title: "_bstr_t 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t 클래스"
  - "BSTR 개체"
  - "BSTR 개체, COM 캡슐화"
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_bstr_t` 개체는 [BSTR 데이터 형식](http://msdn.microsoft.com/ko-kr/1b2d7d2c-47af-4389-a6b6-b01b7e915228)을 캡슐화합니다.  클래스는 해당하는 경우 **SysAllocString** 및 **SysFreeString**에 대한 함수 호출과 다른 `BSTR` API를 통해 리소스 할당 및 할당 해제를 관리합니다.  `_bstr_t` 클래스는 과도한 오버헤드를 방지하기 위해 참조 가산을 사용합니다.  
  
### 생성  
  
|||  
|-|-|  
|[\_bstr\_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` 개체를 생성합니다.|  
  
### 작업  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|`BSTR`을 `_bstr_t`로 래핑된 `BSTR`로 복사합니다.|  
|[연결](../cpp/bstr-t-attach.md)|`_bstr_t` 래퍼를 `BSTR`에 연결합니다.|  
|[copy](../cpp/bstr-t-copy.md)|캡슐화된 `BSTR`의 복사본을 구성합니다.|  
|[분리](../cpp/bstr-t-detach.md)|`_bstr_t`로 래핑된 `BSTR`을 반환하고 `BSTR`을 `_bstr_t`에서 분리합니다.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|`_bstr_t`로 래핑된 `BSTR`을 가리킵니다.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`_bstr_t`에 의해 래핑되는 `BSTR`의 시작 부분을 가리킵니다.|  
|[length](../cpp/bstr-t-length.md)|`_bstr_t`에 있는 문자의 수를 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../cpp/bstr-t-operator-equal.md)|기존 `_bstr_t` 개체에 새 값을 할당합니다.|  
|[operator \+\=](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` 개체의 끝 부분에 문자를 추가합니다.|  
|[operator \+](../cpp/bstr-t-operator-add-equal-plus.md)|두 문자열을 연결합니다.|  
|[operator \!](../cpp/bstr-t-operator-logical-not.md)|캡슐화된 `BSTR`이 **NULL** 문자열인지 확인합니다.|  
|[operator \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/bstr-t-relational-operators.md)|두 `_bstr_t` 개체를 비교합니다.|  
|[operator wchar\_t\* &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|캡슐화된 유니코드 또는 멀티바이트 `BSTR` 개체에 대한 포인터를 추출합니다.|  
  
## Microsoft 전용 종료  
  
## 요구 사항  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib 또는 comsuppwd.lib\(자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 참조\)  
  
## 참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)