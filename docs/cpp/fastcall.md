---
title: __fastcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fastcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d69c97294795ed2f3f0b2d82ec8caa4734fa1f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fastcall"></a>__fastcall
**Microsoft 전용**  
  
 `__fastcall` 호출 규칙은 가능하면 함수의 인수가 레지스터에 전달되도록 지정합니다. 이 호출 규칙은 x86 아키텍처에만 적용됩니다. 다음 목록에서는 이러한 호출 규칙의 구현을 보여 줍니다.  
  
|요소|구현|  
|-------------|--------------------|  
|인수 전달 순서|왼쪽에서 오른쪽으로 인수 목록에서 발견된 처음 두 개의 DWORD 이하 인수는 ECX 및 EDX 레지스터로 전달되고, 다른 모든 인수는 오른쪽에서 왼쪽으로 스택에 전달됩니다.|  
|스택 유지 관리 책임|호출된 함수가 스택에서 인수를 꺼냅니다.|  
|이름 데코레이션 규칙|이름 앞에 at 기호(@)가 붙습니다. 이름 뒤에는 at 기호 다음에 매개 변수 목록의 바이트 수(10진수)가 붙습니다.|  
|대/소문자 변환 규칙|대/소문자 변환은 수행되지 않습니다.|  
  
> [!NOTE]
>  이후 컴파일러 버전은 다른 레지스터를 사용하여 매개 변수를 저장할 수도 있습니다.  
  
 사용 하는 [/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) 컴파일러 옵션을로 컴파일 모듈에서 각 함수 사용 하면 `__fastcall` 충돌 하는 특성을 사용 하 여 선언 된 함수 또는 함수 이름이 하지 않는 한 `main`합니다.  
  
 `__fastcall` 키워드는 ARM 및 x64 아키텍처를 대상으로 하는 컴파일러에서 허용되고 무시됩니다. x64 칩에서는 규칙에 따라 처음 네 개의 인수가 가능하면 레지스터로 전달되고 추가 인수는 스택에 전달됩니다. 자세한 내용은 참조 [개요 x64 호출 규칙](../build/overview-of-x64-calling-conventions.md)합니다. ARM 칩의 경우 최대 4개의 정수 인수와 8개의 부동 소수점 인수가 레지스터로 전달될 수 있으며 추가 인수는 스택에 전달됩니다.  
  
 비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다. 다음의 클래스 정의를 가정해 봅니다.  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 다음 코드는  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 다음 코드 조각과 일치합니다.  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>예제  
 다음 예제에서 `DeleteAggrWrapper` 함수에는 레지스터로 인수가 전달됩니다.  
  
```cpp  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)   
 [키워드](../cpp/keywords-cpp.md)