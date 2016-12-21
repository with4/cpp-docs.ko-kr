---
title: "/Yl(디버그 라이브러리에 PCH 참조 넣기) | Microsoft Docs"
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
  - "/yi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yl 컴파일러 옵션[C++]"
  - "Yl 컴파일러 옵션[C++]"
  - "-Yl 컴파일러 옵션[C++]"
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yl(디버그 라이브러리에 PCH 참조 넣기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 옵션은 미리 컴파일된 헤더를 사용하는 디버깅 라이브러리를 만들려고 했지만 빌드가 실패한 경우에 사용합니다.  
  
## 구문  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## 인수  
 `symbol`  
 개체 모듈에 저장할 임의의 기호입니다.  
  
 \-  
 명시적으로 비활성화 하는 빼기 기호 \(\-\)는 **\/Yl** 컴파일러 옵션입니다.  
  
## 설명  
 기본적으로 컴파일러는 **\/Yl** 옵션 \(지정 하지 않고는 *symbol*\)을 사용합니다.  **\/Yl** 옵션을 사용 하면 디버거 형식에 대 한 완전 한 정보를 가져올 수 있습니다.  **\/Yl\-**는 기본 동작을 불가능하게 합니다.  
  
 **\/Yc** 및 **\/Yl**`symbol`을 사용하여 모듈을 컴파일하면 컴파일러는 \_\_@@\_PchSym\_@00@...@`symbol`과 유사한 기호를 만들어 개체 모듈에 저장합니다. 여기서 줄임표\(...\)는 링커 생성 문자열을 나타냅니다.  이러한 미리 컴파일된 헤더로 컴파일한 소스 파일은 지정된 기호를 참조하므로 링커에 라이브러리의 해당 디버깅 정보와 개체 모듈이 포함됩니다.  
  
 이 옵션을 사용하면 LNK1211이 발생할 수 있습니다.  [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md) 및 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 지정하면 컴파일러는 디버깅 정보가 들어 있는 미리 컴파일된 헤더 파일을 만듭니다.  미리 컴파일된 헤더를 라이브러리에 저장하고 이 라이브러리를 사용하여 개체 모듈을 빌드한 후, 소스 코드에서 미리 컴파일된 헤더 파일이 정의한 함수를 참조하지 않을 경우 오류가 발생할 수 있습니다.  
  
 이 문제를 해결하려면 **\/Yl**`symbol`을 지정하십시오. 여기서 `symbol`은 함수 정의가 포함되지 않은 미리 컴파일된 헤더 파일을 만들 때 라이브러리에 있는 임의의 기호 이름입니다.  이 옵션을 사용하면 컴파일러에서는 미리 컴파일된 헤더 파일에 디버깅 정보를 저장합니다.  
  
 미리 컴파일된 헤더에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [\/Y\(미리 컴파일된 헤더\)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)