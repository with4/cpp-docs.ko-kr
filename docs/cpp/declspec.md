---
title: __declspec | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4358712e5573095229a48a6d08b78706c608874d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403650"
---
# <a name="declspec"></a>__declspec

**Microsoft 전용**

저장소 클래스 정보 사용을 지정 하는 확장 된 특성 구문은 합니다 **__declspec** 키워드를 지정 된 형식의 인스턴스는 아래에 나열 된 Microsoft 전용 저장소 클래스 특성으로 저장 하도록 지정 합니다. 다른 저장소 클래스 한정자의 예로 **정적** 하 고 **extern** 키워드입니다. 그러나 이 키워드는 C 및 C++ 언어의 ANSI 사양에 포함되므로 확장 특성 구문에는 사용되지 않습니다. 확장 특성 구문은 C 및 C++ 언어에 대한 Microsoft 전용 확장을 간소화하고 표준화합니다.

## <a name="grammar"></a>문법

*decl-specifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***확장-선언-한정자-seq***)** 

*extended-decl-modifier-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier* *extended-decl-modifier-seq*

*extended-decl-modifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**align(** *#* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**allocate("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**appdomain**  
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**사용 되지 않음**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**  
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**  
&nbsp;&nbsp;&nbsp;&nbsp;**naked**  
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**  
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**  
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**  
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**  
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**  
&nbsp;&nbsp;&nbsp;&nbsp;**프로세스**  
&nbsp;&nbsp;&nbsp;&nbsp;**property(** { **get=**_get_func_name_ &#124; **,put=**_put_func_name_ } **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**제한**  
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**  
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**  
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**  
&nbsp;&nbsp;&nbsp;&nbsp;**thread**  
&nbsp;&nbsp;&nbsp;&nbsp;**uuid("** *ComObjectGUID* **")**  

공백은 선언 한정자 시퀀스를 구분합니다. 뒤에 나오는 단원에 예제가 있습니다.

확장 된 특성 문법 이러한 Microsoft 전용 저장소 클래스 특성에서 지 원하는: [맞춤](../cpp/align-cpp.md)를 [할당할](../cpp/allocate.md)를 [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [사용 되지 않음](../cpp/deprecated-cpp.md)를 [dllexport](../cpp/dllexport-dllimport.md)를 [dllimport](../cpp/dllexport-dllimport.md)를 [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md)를 [noinline](../cpp/noinline.md)를 [noreturn](../cpp/noreturn.md)를 [nothrow](../cpp/nothrow-cpp.md)를 [novtable](../cpp/novtable.md) 를 [프로세스](../cpp/process.md), [제한](../cpp/restrict.md)를 [safebuffers](../cpp/safebuffers.md)를 [selectany](../cpp/selectany.md)를 [스펙터](../cpp/spectre.md), 및 [스레드](../cpp/thread.md)합니다. 또한 이러한 COM 개체 특성인 지원: [속성](../cpp/property-cpp.md) 하 고 [uuid](../cpp/uuid-cpp.md)합니다.

합니다 **code_seg**, **dllexport**를 **dllimport**를 **naked**를 **noalias**, **nothrow** , **속성**, **제한할**를 **selectany**를 **스레드**, 및 **uuid**저장소 클래스 특성은 적용 되는 함수 개체의 선언에만 속성입니다. 합니다 **스레드** 특성 데이터에 영향을 줍니다. 및 개체에 합니다. 합니다 **naked** 하 고 **스펙터** 특성 함수에만 영향을 합니다. 합니다 **dllimport** 하 고 **dllexport** 특성 함수, 데이터 및 개체에 영향을 줍니다. 합니다 **속성**, **selectany**, 및 **uuid** 특성 COM 개체에 영향을 줍니다.

합니다 **__declspec** 키워드는 단순한 선언 시작 부분에 배치 해야 합니다. 컴파일러 경고 없이 무시 **__declspec** 키워드 뒤에 배치 * 또는 & 및 선언에 변수 식별자 앞에 있습니다.

A **__declspec** 사용자 정의 형식 선언의 시작 부분에 지정 된 특성이 해당 형식의 변수에 적용 됩니다. 예를 들어:

```cpp
__declspec(dllimport) class X {} varX;
```

이 경우 특성이 `varX`에 적용됩니다. A **__declspec** 특성 뒤에 배치 합니다 **클래스** 또는 **구조체** 키워드는 사용자 정의 형식에 적용 합니다. 예를 들어:

```cpp
class __declspec(dllimport) X {};
```

이 경우 특성이 `X`에 적용됩니다.

사용에 대 한 일반적인 지침은 합니다 **__declspec** 특성 단순한 선언에는 다음과 같습니다.

*decl-specifier-seq* *init-declarator-list*;

합니다 *선언에서 지정자-seq* 있어야, 무엇 보다도 기본 형식 (예: **int**를 **float**, **typedef**, 또는 클래스 이름), 저장소 클래스 (예: **정적**를 **extern**), 또는 **__declspec** 확장 합니다. 합니다 *init-선언 자 목록* 있어야, 무엇 보다도 선언의 포인터 부분입니다. 예를 들어:

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

다음 코드는 정수 스레드 로컬 변수를 선언하고 값을 사용하여 초기화합니다.

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료
 [키워드](../cpp/keywords-cpp.md)  
 [C 확장 저장소 클래스 특성](../c-language/c-extended-storage-class-attributes.md)  