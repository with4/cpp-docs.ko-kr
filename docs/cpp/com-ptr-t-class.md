---
title: "_com_ptr_t 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t 클래스"
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# _com_ptr_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_com_ptr_t` 개체는 COM 인터페이스 포인터를 캡슐화하며 "스마트" 포인터라고 합니다.  이 템플릿 클래스는 `QueryInterface`, `AddRef` 및 **Release** 등의 **IUnknown** 멤버 함수에 대한 함수 호출을 통해 자원 할당과 반환을 관리합니다.  
  
 스마트 포인터는 일반적으로 **\_COM\_SMARTPTR\_TYPEDEF** 매크로가 제공하는 typedef 정의에서 참조됩니다.  이 매크로는 인터페이스 이름과 IID를 사용하며 인터페이스의 이름 및 `Ptr`의 접미사로 `_com_ptr_t` 의 특수화를 선언합니다.  예를 들면 다음과 같습니다.  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 `_com_ptr_t` 특수화 **IMyInterfacePtr**을 선언합니다.  
  
 이 템플릿 클래스의 멤버가 아닌 [함수 템플릿](../cpp/relational-function-templates.md)의 집합은 비교 연산자 오른쪽에 있는 스마트 포인터와 비교를 지원합니다.  
  
### 생성  
  
|||  
|-|-|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-com-ptr-t.md)|`_com_ptr_t` 개체를 생성합니다.|  
  
### 하위 수준 연산  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|캡슐화된 인터페이스 포인터에 대해 **IUnknown**의 멤버 함수 `AddRef`를 호출합니다.|  
|[연결](../cpp/com-ptr-t-attach.md)|이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|**CLSID** 또는 **ProgID**가 지정된 개체의 새 인스턴스를 만듭니다.|  
|[분리](../cpp/com-ptr-t-detach.md)|캡슐화된 인터페이스 포인터를 추출하고 반환합니다.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|**CLSID** 또는 **ProgID**가 지정된 개체의 기존 인스턴스에 연결합니다.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|캡슐화된 인터페이스 포인터가 반환됩니다.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|캡슐화된 인터페이스 포인터에 **IUnknown**의 멤버 함수 `QueryInterface`를 호출합니다.|  
|[Release](../cpp/com-ptr-t-release.md)|캡슐화된 인터페이스 포인터에 **IUnknown**의 멤버 함수 **Release**를 호출합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../cpp/com-ptr-t-operator-equal.md)|기존 `_com_ptr_t` 개체에 새 값을 할당합니다.|  
|[연산자 \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/com-ptr-t-relational-operators.md)|스마트 포인터 개체를 다른 스마트 포인터, 원시 인터페이스 포인터 또는 **NULL**과 비교합니다.|  
|[추출기](../cpp/com-ptr-t-extractors.md)|캡슐화된 COM 인터페이스 포인터를 추출합니다.|  
  
## Microsoft 전용 종료  
  
## 요구 사항  
 **헤더:** comip.h  
  
 **Lib:** comsuppw.lib 또는 comsuppwd.lib\(자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 참조\)  
  
## 참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)