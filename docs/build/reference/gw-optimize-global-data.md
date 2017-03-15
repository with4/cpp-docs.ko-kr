---
title: "/Gw(전역 데이터 최적화) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Gw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gw 컴파일러 옵션[C++]"
  - "-Gw 컴파일러 옵션[C++]"
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Gw(전역 데이터 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COMDAT 섹션 최적화에 대한 글로벌 데이터 패키지입니다.  
  
## 구문  
  
```  
/Gw[-]  
```  
  
## 설명  
 **\/Gw** 옵션은 개별 COMDAT 섹션에서 컴파일러가 패키지 전역 데이터를 사용하게 합니다.  기본적으로, **\/Gw** 는 해제 되고 명시적으로 설정되야 합니다.  명시적으로 비활성화하려면, **\/Gw\-**을 사용하세요.  **\/Gw** 및 [\/GL](../../build/reference/gl-whole-program-optimization.md) 가 활성화될 때, 링커는 전체 프로그램 최적화를 사용하여 참조 되지 않은 전역 데이터를 제외 하기 위해 또는 동일한 읽기 전용 글로벌 데이터를 병합하기 위해 COMDAT 섹션을 비교합니다.  이것은 결과 이진 파일의 크기를 크게 줄일 수 있습니다.  
  
 별도로 컴파일하고 링크 하는 경우, [\/OPT:REF](../../build/reference/opt-optimizations.md) 링커 옵션을 사용하여**\/Gw** 옵션으로 컴파일된 개체 파일의 참조 되지 않은 전역 변수를 실행할 수 있는 것으로부터 제외시키는 옵션을 사용할 수 있습니다.  
  
 또한 [\/OPT:ICF](../../build/reference/opt-optimizations.md) 및 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 링커 옵션은 개체의 **\/Gw** 옵션으로 여러 개체 파일을 컴파일한 동일한 읽기 전용 전역 변수를 실행하는 곳에 함께 병합되는 데 사용할 수 있습니다.  
  
 자세한 내용은 Visual C\+\+ 팁 블로그에서 다음을 참조하십시오. [Introducing \/Gw 컴파일러 스위치](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) .  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 속성을 **\/Gw**에 포함하도록 수정한 후 **확인**을 선택합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)