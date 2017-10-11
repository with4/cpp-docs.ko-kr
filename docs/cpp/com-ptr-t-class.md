---
title: "_com_ptr_t 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3979a33f095092c5cbaac91793c501e31304a6d4
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrt-class"></a>_com_ptr_t 클래스
**Microsoft 전용**  
  
 `_com_ptr_t` 개체는 COM 인터페이스 포인터를 캡슐화하며 "스마트" 포인터라고 합니다. 이 템플릿 클래스 리소스 할당 및 할당 해제 함수 호출을 통해 관리 하는 **IUnknown** 멤버 함수: `QueryInterface`, `AddRef`, 및 **릴리스**합니다.  
  
 스마트 포인터에서 제공 하는 typedef 정의에서 일반적으로 참조 되는 **_COM_SMARTPTR_TYPEDEF** 매크로입니다. 이 매크로는 인터페이스 이름과 IID를 사용하며 인터페이스의 이름 및 `_com_ptr_t`의 접미사로 `Ptr` 의 특수화를 선언합니다. 예:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 선언 된 `_com_ptr_t` 특수화 **IMyInterfacePtr**합니다.  
  
 집합이 [함수 템플릿](../cpp/relational-function-templates.md),이 서식 파일의 멤버가 아닌 클래스, 비교 연산자의 우변에 있는 스마트 포인터와 비교 지원 합니다.  
  
### <a name="construction"></a>생성  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|`_com_ptr_t` 개체를 생성합니다.|  
  
### <a name="low-level-operations"></a>하위 수준 연산  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|호출의 `AddRef` 의 멤버 함수 **IUnknown** 캡슐화 된 인터페이스 포인터입니다.|  
|[Attach](../cpp/com-ptr-t-attach.md)|이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|지정 된 개체의 새 인스턴스를 만듭니다는 **CLSID** 또는 **ProgID**합니다.|  
|[Detach](../cpp/com-ptr-t-detach.md)|캡슐화된 인터페이스 포인터를 추출하고 반환합니다.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|지정 된 개체의 기존 인스턴스를 연결 된 **CLSID** 또는 **ProgID**합니다.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|캡슐화된 인터페이스 포인터가 반환됩니다.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|호출의 `QueryInterface` 의 멤버 함수 **IUnknown** 캡슐화 된 인터페이스 포인터입니다.|  
|[릴리스](../cpp/com-ptr-t-release.md)|호출의 **릴리스** 의 멤버 함수 **IUnknown** 캡슐화 된 인터페이스 포인터입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 =](../cpp/com-ptr-t-operator-equal.md)|기존 `_com_ptr_t` 개체에 새 값을 할당합니다.|  
|[연산자 = =,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|스마트 포인터 개체를 다른 스마트 포인터, 원시 인터페이스 포인터를 비교 또는 **NULL**합니다.|  
|[추출기](../cpp/com-ptr-t-extractors.md)|캡슐화된 COM 인터페이스 포인터를 추출합니다.|  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** comip.h  
  
 **Lib:** 에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용은)  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)
