---
title: "/QIfist(_ftol 사용 안 함) | Microsoft Docs"
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
  - "/qifist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QIfist 컴파일러 옵션[C++]"
  - "-QIfist 컴파일러 옵션[C++]"
  - "/QIfist 컴파일러 옵션[C++]"
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /QIfist(_ftol 사용 안 함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 형식에서 정수 계열 형식으로 변환해야 할 때 도우미 함수 `_ftol`이 호출되지 않도록 합니다.  
  
## 구문  
  
```  
/QIfist  
```  
  
## 설명  
  
> [!NOTE]
>  **\/QIfist**는 x86을 대상으로 한 컴파일러에서만 사용할 수 있습니다; [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 또는 ARM을 대상으로 한 컴파일러에서는 이 컴파일러 옵션을 사용할 수 없습니다.  
  
 `_ftol` 함수를 사용하면 부동 소수점 형식을 정수 계열 형식으로 변환할 뿐 아니라, 제어 워드의 비트 10 및 11을 설정하여 FPU\(부동 소수점 단위\)의 반올림 모드를 0\(잘라내기\)으로 지정합니다.  따라서 ANSI 표준에서 설명하는 대로 숫자의 소수 부분이 잘리고 부동 소수점 형식이 정수 계열 형식으로 변환됩니다.  **\/QIfist** 옵션을 사용하면 이러한 변환이 적용되지 않습니다.  반올림 모드는 Intel 참조 문서에 있는 다음 네 가지 중 한 가지가 됩니다.  
  
-   가까운 값으로 반올림\(중간인 경우는 짝수로 반올림\)  
  
-   음의 방향으로 반올림  
  
-   양의 방향으로 반올림  
  
-   0으로 반올림  
  
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C 런타임 함수를 사용하면 FPU의 반올림 동작을 변경할 수 있습니다.  FPU의 기본 반올림 모드는 "가까운 값으로 반올림"입니다. **\/QIfist** 옵션을 사용하면 응용 프로그램의 성능을 향상시킬 수 있지만 오류가 발생할 수 있습니다.  프로덕션 환경에서 **\/QIfist** 옵션으로 빌드한 코드를 사용하기 전에 반올림 모드의 영향을 받기 쉬운 코드 부분을 완전히 테스트해야 합니다.  
  
 [\/arch\(x86\)](../../build/reference/arch-x86.md) 및 **\/QIfist**는 같은 컴파일에서 사용할 수 없습니다.  
  
> [!NOTE]
>  비트를 반올림하면 매번 계산 후에 부동 소수점도 반올림되므로 **\/QIfist**는 기본적으로 적용되지 않습니다. 따라서 C 스타일 \(0으로\) 반올림에 대한 플래그를 설정하면 부동 소수점 계산 결과가 달라질 수 있습니다.  부동 소수점 숫자의 소수 부분을 잘라내는 동작이 코드에 필요한 경우 **\/QIfist**를 사용하지 말아야 합니다.  확실하지 않으면 **\/QIfist** 옵션을 사용하지 마십시오.  
  
 **\/QIfist**는 사용되지 않습니다.  부동 소수점에서 정수로의 변환 속도와 관련하여 컴파일러 성능이 크게 향상되었습니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)