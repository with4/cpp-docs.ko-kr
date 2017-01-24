---
title: "__stdcall | Microsoft Docs"
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
  - "__stdcall_cpp"
  - "__stdcall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall 키워드[C++]"
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __stdcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `__stdcall` 호출 규칙은 Win32 API 함수를 호출하는 데 사용됩니다.  호출 수신자가 스택을 정리하므로 컴파일러는 **vararg** 함수를 `__cdecl`로 만듭니다.  이 호출 규칙을 사용하는 함수에는 함수 프로토타입이 필요합니다.  
  
## 구문  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## 설명  
 다음 목록에서는 이러한 호출 규칙의 구현을 보여 줍니다.  
  
|요소|구현|  
|--------|--------|  
|인수 전달 순서|오른쪽에서 왼쪽|  
|인수 전달 규칙|포인터 또는 참조 형식이 전달되지 않는 경우 값으로 전달|  
|스택 유지 관리 책임|호출된 함수가 스택에서 자신의 인수를 꺼냅니다.|  
|이름 데코레이션 규칙|밑줄\(\_\)이 이름 앞에 붙습니다.  이름 뒤에는 기호\(@\)가 오고 그 위에 인수 목록의 바이트 수\(10진수\)가 옵니다.  따라서 `int func( int a, double b )`로 선언된 함수는 `_func@12`로 데코레이팅됩니다.|  
|대\/소문자 변환 규칙|없음|  
  
 [\/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) 컴파일러 옵션은 다른 호출 규칙으로 명시적으로 선언되지 않은 모든 함수에 대해 `__stdcall`을 지정합니다.  
  
 `__stdcall` 한정자를 사용하여 선언된 함수는 [\_\_cdecl](../cpp/cdecl.md)을 사용하여 선언된 함수와 같은 방식으로 값을 반환합니다.  
  
 ARM 및 x64 프로세서에서는 `__stdcall`이 컴파일러에서 허용되고 무시됩니다. ARM 및 x64 아키텍처에서는 규칙에 따라 가능한 경우 인수가 레지스터로 전달되고 이후 인수는 스택에 전달됩니다.  
  
 비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다.  즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.  다음과 같은 클래스 정의가 주어진 경우  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 다음 코드는  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 다음 코드와 동일합니다.  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## 예제  
 다음 예제에서 \_\_**stdcall**을 사용하면 모든 `WINAPI` 함수 형식이 표준 호출로 처리됩니다.  
  
```c  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## 참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)