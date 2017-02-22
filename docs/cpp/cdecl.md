---
title: "__cdecl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__cdecl"
  - "__cdecl_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__cdecl 키워드[C++]"
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# __cdecl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `__cdecl`은 C 및 C\+\+ 프로그램의 기본 호출 규칙입니다.  스택은 호출자에 의해 정리되기 때문에 **vararg** 함수를 수행할 수 있습니다.  `__cdecl` 호출 규칙은 각 함수 호출에 스택 정리 코드를 포함시키기 때문에 [\_\_stdcall](../cpp/stdcall.md)보다 큰 실행 가능 명령문을 생성합니다.  다음 목록에서는 이러한 호출 규칙의 구현을 보여 줍니다.  
  
|요소|구현|  
|--------|--------|  
|인수 전달 순서|오른쪽에서 왼쪽|  
|스택 유지 관리 책임|호출하는 함수가 스택에서 인수를 꺼냅니다.|  
|이름 데코레이션 규칙|밑줄 문자\(\_\)는 C 링크를 사용하는 \_\_cdecl 함수를 내보내는 경우를 제외하고 이름 앞에 붙습니다.|  
|대\/소문자 변환 규칙|대\/소문자 변환은 수행되지 않습니다.|  
  
> [!NOTE]
>  관련 내용은 [데코레이팅된 이름](../build/reference/decorated-names.md)를 참조하십시오.  
  
 변수나 함수 이름 앞에 `__cdecl` 한정자를 넣습니다.  C 명명 규칙 및 호출 규칙은 기본값이므로 `__cdecl`은 **\/Gv**\(vectorcall\), **\/Gz**\(stdcall\) 또는 **\/Gr**\(fastcall\) 컴파일러 옵션을 지정했을 때만 x86 코드에서 사용됩니다.  [\/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) 컴파일러 옵션은 `__cdecl` 호출 규칙을 강제합니다.  
  
 ARM 및 x64 프로세서에서는 컴파일러가 `__cdecl`을 수락하지만 일반적으로 무시합니다.  ARM 및 x64에서는 규칙에 따라 인수는 가능한 경우 레지스터로 전달되고 이후 인수는 스택에 전달됩니다.  x64 코드에서는 `__cdecl`을 사용하여 **\/Gv** 컴파일러 옵션을 재정의하고 기본 x64 호출 규칙을 사용합니다.  
  
 비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다.  즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.  다음의 클래스 정의를 가정해 봅니다.  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 다음 코드는  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 다음 코드 조각과 일치합니다.  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## 예제  
 다음 예제에서 컴파일러는 `system` 함수에 대해 C 명명 규칙 및 호출 규칙을 사용하도록 지시되었습니다.  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## 참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)