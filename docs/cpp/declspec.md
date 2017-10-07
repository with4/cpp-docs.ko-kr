---
title: __declspec | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b29b6243611f1ca59a579869469c803d3735f9df
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Microsoft 전용  
 저장소 클래스 정보를 지정하기 위한 확장 특성 구문에서는 주어진 형식의 인스턴스가 아래의 Microsoft 전용 저장소 클래스 특성과 함께 저장되도록 지정하는 `__declspec` 키워드를 사용합니다. 다른 저장소 클래스 한정자의 예에는 `static` 키워드와 `extern` 키워드가 있습니다. 그러나 이 키워드는 C 및 C++ 언어의 ANSI 사양에 포함되므로 확장 특성 구문에는 사용되지 않습니다. 확장 특성 구문은 C 및 C++ 언어에 대한 Microsoft 전용 확장을 간소화하고 표준화합니다.  
  
## <a name="grammar"></a>문법  
 *decl 지정자*:  
 `__declspec (`  *확장-decl-한정자-seq*  `)`  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier*opt  
  
 *확장-decl-한정자 확장-decl-한정자-seq*  
  
 *extended-decl-modifier*:  
 `align(` *#* `)`  
  
 `allocate("`*segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*segname*`")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get_func_name*&#124;`,put=` *put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 공백은 선언 한정자 시퀀스를 구분합니다. 뒤에 나오는 단원에 예제가 있습니다.  
  
 확장된 특성 문법에서 이러한 Microsoft 전용 저장소 클래스 특성을 지 원하는: [맞춤](../cpp/align-cpp.md), [할당](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [사용 되지 않는](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) [프로세스](../cpp/process.md), [제한](../cpp/restrict.md), [safebuffer](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), 및 [스레드](../cpp/thread.md)합니다. 또한 이러한 COM 개체 특성을 지원: [속성](../cpp/property-cpp.md) 및 [uuid](../cpp/uuid-cpp.md)합니다.  
  
 `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` 및 `uuid` 저장소 클래스 특성은 적용되는 개체 또는 함수의 선언에만 해당되는 속성입니다. `thread` 특성은 데이터 및 개체에만 영향을 줍니다. `naked` 특성은 함수에만 영향을 줍니다. `dllimport` 및 `dllexport` 특성은 함수, 데이터 및 개체에 영향을 줍니다. `property`, `selectany` 및 `uuid` 특성은 COM 개체에 영향을 줍니다.  
  
 `__declspec` 키워드는 단순한 선언 시작 부분에 와야 합니다. 컴파일러는 선언에서 * 또는 & 뒤와 변수 식별자 앞에 오는 `__declspec` 키워드를 경고 없이 무시합니다.  
  
 사용자 정의 형식 선언의 시작 부분에 지정된 `__declspec` 특성은 해당 형식의 변수에 적용됩니다. 예:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 이 경우 특성이 `varX`에 적용됩니다. `__declspec` 또는 `class` 키워드 뒤에 오는 `struct` 특성은 사용자 정의 형식에 적용됩니다. 예:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 이 경우 특성이 `X`에 적용됩니다.  
  
 단순한 선언에 `__declspec` 특성을 사용하는 데 대한 일반적인 지침은 다음과 같습니다.  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 *decl-지정자-seq* 을 포함 해야 무엇 보다도 기본 형식 (예: `int`, `float`, `typedef`, 또는 클래스 이름), 저장소 클래스 (예: `static`, `extern`), 또는 `__declspec`확장 합니다. *init 선언 자 목록* 해야 부분을 포함, 무엇 보다도 포인터의 선언입니다. 예:  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 다음 코드는 정수 스레드 로컬 변수를 선언하고 값을 사용하여 초기화합니다.  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [C 확장 저장소 클래스 특성](../c-language/c-extended-storage-class-attributes.md)
