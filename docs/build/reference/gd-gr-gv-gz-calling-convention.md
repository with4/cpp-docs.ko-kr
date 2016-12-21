---
title: "/Gd, /Gr, /Gv, /Gz(호출 규칙) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gr"
  - "/Gv"
  - "/gz"
  - "/Gd"
  - "VC.Project.VCCLCompilerTool.CallingConvention"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gd 컴파일러 옵션[C++]"
  - "/Gr 컴파일러 옵션[C++]"
  - "/Gv 컴파일러 옵션[C++]"
  - "/Gz 컴파일러 옵션[C++]"
  - "Gd 컴파일러 옵션[C++]"
  - "-Gd 컴파일러 옵션[C++]"
  - "Gr 컴파일러 옵션[C++]"
  - "-Gr 컴파일러 옵션[C++]"
  - "Gv 컴파일러 옵션[C++]"
  - "-Gv 컴파일러 옵션[C++]"
  - "Gz 컴파일러 옵션[C++]"
  - "-Gz 컴파일러 옵션[C++]"
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gd, /Gr, /Gv, /Gz(호출 규칙)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 옵션에 따라 함수 인수가 스택에 푸시되는 순서, 호출자 함수 또는 호출된 함수가 호출 마지막 단계에서 스택의 인수를 제거하는지 여부, 개별 함수를 식별하기 위해 컴파일러에 사용되는 이름 데코레이션 규칙이 결정됩니다.  
  
## 구문  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## 설명  
 **\/Gd**는 기본 설정으로, C\+\+ 멤버 함수와 [\_\_stdcall](../../cpp/stdcall.md), [\_\_fastcall](../../cpp/fastcall.md) 또는 [\_\_vectorcall](../../cpp/vectorcall.md)로 표시된 함수를 제외한 모든 함수에 대해 [\_\_cdecl](../../cpp/cdecl.md) 호출 규칙을 지정합니다.  
  
 **\/Gr**은 C\+\+ 멤버 함수, 이름이 `main`인 함수 및 `__cdecl`, `__stdcall` 또는 `__vectorcall`로 표시된 함수를 제외한 모든 함수에 대해 `__fastcall` 호출 규칙을 지정합니다.  모든 `__fastcall` 함수는 프로토타입을 가져야 합니다.  이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며 기타 아키텍처를 대상으로 하는 컴파일러에서 무시됩니다.  
  
 **\/Gz**는 C\+\+ 멤버 함수, 이름이 `main`인 함수 및 `__cdecl`, `__fastcall` 또는 `__vectorcall`로 표시된 함수를 제외한 모든 함수에 대해 `__stdcall` 호출 규칙을 지정합니다.  모든 `__stdcall` 함수는 프로토타입을 가져야 합니다.  이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며 기타 아키텍처를 대상으로 하는 컴파일러에서 무시됩니다.  
  
 **\/Gv**는 C\+\+ 멤버 함수, main이라는 함수, `vararg` 변수 인수 목록이 있는 함수 또는 `__cdecl`, `__stdcall` 또는 `__fastcall` 특성과 충돌하는 것으로 표시된 함수를 제외한 모든 함수에 대한 `__vectorcall` 호출 규칙을 지정합니다.  이 호출 규칙은 \/arch:SSE2 이상을 지원하는 x86 및 x64 아키텍처에서만 사용할 수 있으며 ARM 아키텍처를 대상으로 하는 컴파일러에서 무시됩니다.  
  
 가변 인수를 취하는 함수는 `__cdecl`로 표시해야 합니다.  
  
 **\/Gd**, **\/Gr**, **\/Gv** 및 **\/Gz**는 [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) 또는 **\/clr:pure**와 함께 사용할 수 없습니다.  
  
> [!NOTE]
>  x86 프로세서의 경우 기본적으로 C\+\+ 멤버 함수에서 [\_\_thiscall](../../cpp/thiscall.md)을 사용합니다.  
  
 모든 프로세서에 대해 `__cdecl`, `__fastcall`, `__vectorcall` 또는 `__stdcall`로서 명시적으로 표시된 멤버 함수는 해당 아키텍처에서 무시되지 않을 경우 지정된 호출 규칙을 사용합니다.  다양한 수의 인수를 가지는 멤버 함수는 항상 `__cdecl` 호출 규칙을 사용합니다.  
  
 이러한 컴파일러 옵션은 C\+\+ 메서드와 함수의 이름 데코레이션에 영향을 주지 않습니다.  `extern "C"`로 선언된 것을 제외하고 C\+\+ 메서드와 함수는 다른 이름 데코레이션 구성표를 사용합니다.  자세한 내용은 [데코레이팅된 이름](../../build/reference/decorated-names.md)을 참조하십시오.  
  
 호출 규칙에 대한 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)를 참조하십시오.  
  
## \_\_cdecl 특성  
 X86 프로세서의 경우 모든 함수 인수는 스택 오른쪽에서 왼쪽으로 전달됩니다.  ARM 및 x64 아키텍처에서 일부 인수는 레지스터로 전달되며 나머지는 오른쪽에서 왼쪽으로 스택에 전달됩니다.  호출 루틴은 스택에서 인수를 꺼냅니다.  
  
 C에서 `__cdecl` 명명 규칙은 앞에 밑줄\(`_`\)이 오는 함수 이름을 사용하며, 대\/소문자 변환은 수행되지 않습니다.  `extern "C"`로 선언되는 경우를 제외하고 C\+\+ 함수는 다른 이름 데코레이션 구성표를 사용합니다.  자세한 내용은 [데코레이팅된 이름](../../build/reference/decorated-names.md)을 참조하십시오.  
  
## \_\_fastcall 특성  
 `__fastcall` 함수의 인수 중 일부는 레지스터에 전달되고\(x86 프로세서의 경우 EXC 및 EDX\) 나머지 인수는 오른쪽에서 왼쪽으로 스택에 푸시됩니다.  호출된 루틴은 반환하기 전에 스택에서 이 인수를 꺼냅니다.  일반적으로 **\/Gr**는 실행 시간을 줄입니다.  
  
> [!NOTE]
>  인라인 어셈블리 언어로 작성된 함수에 대해 `__fastcall` 호출 규칙을 사용할 때는 주의하십시오.  레지스터 사용과 컴파일러의 사용이 충돌할 수 있습니다.  
  
 C에서 `__fastcall` 명명 규칙은 앞에 \(`@`\) 기호가 오고 뒤에 바이트 단위로 표시된 함수 인수 크기가 오는 함수 이름을 사용합니다.   대\/소문자 변환은 수행되지 않습니다.  컴파일러는 명명 규칙에 이 템플릿을 사용합니다.  
  
```c  
@function_name@number  
```  
  
 `__fastcall` 명명 규칙을 사용할 때는 표준 포함 파일을 사용합니다.  그렇지 않으면 확인할 수 없는 외부 참조가 발생합니다.  
  
## \_\_stdcall 특성  
 `__stdcall` 함수의 인수는 스택에 오른쪽부터 왼쪽으로 넣어지고,호출된 함수는 반환되기 전에 스택에서 이 인수를 꺼냅니다.  
  
 C에서 `__stdcall` 명명 규칙은 앞에 밑줄\(`_`\)이 오고 뒤에 \(@\) 기호와 바이트 단위로 표시된 함수의 인수 크기가 오는 함수 이름을 사용합니다.  대\/소문자 변환은 수행되지 않습니다.  컴파일러는 명명 규칙에 이 템플릿을 사용합니다.  
  
```c  
_functionname@number  
```  
  
## \_\_vectorcall 고유 정보  
 `__vectorcall` 함수의 정수 인수는 부동 소수점과 벡터 값에 대해 최대 2개\(x86\) 또는 4개\(x64\)의 정수 레지스터 및 최대 6개의 XMM 레지스터를 사용하여 값으로 전달되고 나머지는 스택우로 오른쪽에서 왼쪽으로 전달됩니다.  호출된 함수는 반환 전에 스택을 정리합니다.  벡터 및 부동 소수점 반환 값은 XMM0에 반환됩니다.  
  
 C의 경우 `__vectorcall` 명명 규칙에서는 함수 이름 뒤에 두 개의 @ 기호\(@@\)와 바이트 단위로 표시된 함수 인수의 크기가 차례로 따라오는 형식을 사용합니다.  대\/소문자 변환은 수행되지 않습니다.  컴파일러는 명명 규칙에 이 템플릿을 사용합니다.  
  
```c  
functionname@@number  
```  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box.  For details, see [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md).  
  
2.  Select the **C\/C\+\+** folder.  
  
3.  Select the **Advanced** property page.  
  
4.  Modify the **Calling Convention** property.  
  
### To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)