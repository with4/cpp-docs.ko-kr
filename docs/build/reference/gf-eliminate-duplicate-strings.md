---
title: "/GF(중복 문자열 제거) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.StringPooling"
  - "VC.Project.VCCLWCECompilerTool.StringPooling"
  - "/gf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GF 컴파일러 옵션[C++]"
  - "문자열 중복"
  - "중복 문자열 제거 컴파일러 옵션[C++]"
  - "GF 컴파일러 옵션[C++]"
  - "-GF 컴파일러 옵션[C++]"
  - "문자열 풀링 컴파일러 옵션[C++]"
  - "문자열[C++], 풀링"
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /GF(중복 문자열 제거)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 실행하는 동안 프로그램 이미지와 메모리에서 동일한 문자열의 한 사본을 만들 수 있도록 합니다.  이것은 더 작은 프로그램을 만들 수 있는 *문자열 풀링*이라는 최적화입니다.  
  
## 구문  
  
```  
/GF  
```  
  
## 설명  
 **\/GF**를 사용하면 운영 체제는 메모리의 문자열 부분을 스왑하지 않고 이미지 파일에서 해당 문자열을 다시 읽을 수 있습니다.  
  
 **\/GF**를 사용하면 문자열을 읽기 전용으로 풀링합니다.  **\/GF**를 사용하여 문자열을 수정하면 응용 프로그램에서 오류가 발생합니다.  
  
 문자열을 풀링하면 다중 버퍼에 대한 다중 포인터로서 사용될 대상을 단일 버퍼에 대한 다중 포인터로 사용할 수 있습니다.  다음 코드에서 `s`와 `t`는 동일한 문자열로 초기화됩니다.  문자열이 풀링되므로 이는 동일한 메모리를 가리키게 됩니다.  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  편집하며 계속하기에 사용되는 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 사용하면 **\/GF** 옵션이 자동으로 설정됩니다.  
  
> [!NOTE]
>  **\/GF** 컴파일러 옵션은 각 고유 문자열에 대해 주소 지정 가능한 섹션을 작성합니다.  기본적으로 개체 파일에서는 주소 지정 가능한 섹션을 최대 65,536개까지 보유할 수 있습니다.  프로그램에 둘 이상의 65,536 문자열이 포함된 경우 추가 섹션을 만들기 위해 [\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) 컴파일러 옵션을 사용합니다.  
  
 **\/GF**는 [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 **\/O2**를 사용할 때 적용됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **문자열 풀링 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)