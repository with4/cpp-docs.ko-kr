---
title: "/Os, /Ot(크기 우선 코드, 속도 우선 코드) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed"
  - "/os"
  - "VC.Project.VCCLCompilerTool.FavorSizeOrSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Os 컴파일러 옵션[C++]"
  - "/Ot 컴파일러 옵션[C++]"
  - "빠른 코드"
  - "속도 우선 코드 컴파일러 옵션[C++]"
  - "크기 우선 코드 컴파일러 옵션[C++]"
  - "Os 컴파일러 옵션[C++]"
  - "-Os 컴파일러 옵션[C++]"
  - "Ot 컴파일러 옵션[C++]"
  - "-Ot 컴파일러 옵션[C++]"
  - "작은 컴퓨터 코드"
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Os, /Ot(크기 우선 코드, 속도 우선 코드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

EXE와 DLL의 크기를 최소화하거나 최대화합니다.  
  
## 구문  
  
```  
/Os  
/Ot  
```  
  
## 설명  
 **\/Os**\(코드 크기 우선\) 옵션은 속도보다 크기를 우선적으로 처리하도록 컴파일러에 지시하여 EXE 파일과 DLL의 크기를 최소화합니다.  그러면 컴파일러는 여러 C 및 C\+\+ 구문을 기능이 유사한 기계어 코드 시퀀스로 만들 수 있습니다.  이러한 차이 때문에 크기와 속도를 상대적으로 조정해야 하는 경우가 있습니다.  **\/Os** 및 **\/Ot** 옵션을 사용하면 크기와 속도 중에서 어떤 것을 우선적으로 고려할 것인지 지정할 수 있습니다.  
  
 **\/Ot**\(코드 속도 우선\) 옵션은 크기보다 속도를 우선적으로 처리하도록 컴파일러에 지시하여 EXE 파일과 DLL의 속도를 최대화합니다. 이 옵션이 기본값입니다. 그러면 컴파일러는 여러 C 및 C\+\+ 구문을 기능이 유사한 기계어 코드 시퀀스로 만들 수 있습니다.  이러한 차이 때문에 크기와 속도를 상대적으로 조정해야 하는 경우가 있습니다.  \/Ot 옵션은 속도 최대화 옵션\([\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)\)에 포함되어 있습니다.  **\/O2** 옵션은 여러 옵션을 결합하여 상당히 속도가 빠른 코드를 만듭니다.  
  
 **\/Os** 또는 **\/Ot**를 사용하는 경우 코드를 최적화하려면 [\/Og](../../build/reference/og-global-optimizations.md)를 지정해야 합니다.  
  
> [!NOTE]
>  프로파일링 테스트 실행에서 수집되는 정보는 **\/Ob**, **\/Os** 또는 **\/Ot**를 지정할 때 적용되는 최적화를 재정의합니다.  자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)을 참조하십시오.  
  
 **x86 전용**  
  
 다음 예제 코드에서는 코드 크기 우선 옵션\(**\/Os**\)과 코드 속도 우선 옵션\(**\/Ot**\) 사이의 차이점을 보여 줍니다.  
  
> [!NOTE]
>  아래에서는 **\/Os** 또는 **\/Ot**를 사용하는 경우 예상되는 동작에 대해 설명합니다.  그러나 아래 코드를 사용할 경우에는 컴파일러에서 코드를 최적화하는 방식이 릴리스에 따라 다를 수 있습니다.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 아래 기계어 코드처럼 DIFFER.c가 크기 우선 코드\(**\/Os**\)로 컴파일될 경우, 컴파일러는 return 문의 곱셈 식을 짧지만 느린 코드 시퀀스를 만드는 곱셈으로 구현합니다.  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 반대로, DIFFER.c가 코드 속도 우선\(**\/Ot**\)으로 컴파일될 경우, 컴파일러는 return 문의 곱셈 식을 빠르지만 긴 코드 시퀀스를 만드는 일련의 shift와 `LEA` 명령으로 구현합니다.  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **END x86 Specific**  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **크기 또는 속도** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)