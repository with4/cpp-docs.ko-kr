---
title: "/Zm(메모리 할당 제한 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 메모리 할당 제한"
  - "/Zm 컴파일러 옵션[C++]"
  - "cl.exe 컴파일러, 메모리 할당 제한"
  - "메모리 할당, 메모리 할당 제한 컴파일러 옵션"
  - "PCH 파일, 메모리 할당 제한"
  - "미리 컴파일된 헤더 파일, 메모리 할당 제한"
  - "미리 컴파일된 헤더 메모리의 할당 제한 지정 컴파일러 옵션"
  - "Zm 컴파일러 옵션[C++]"
  - "-Zm 컴파일러 옵션[C++]"
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Zm(메모리 할당 제한 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 할당하는 메모리의 양을 결정합니다.  
  
## 구문  
  
```  
/Zmfactor  
```  
  
## 인수  
 `factor`  
 미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 사용하는 메모리의 양을 결정하는 배율 인수입니다.  
  
 `factor` 인수는 컴파일러에 정의된 작업 버퍼의 기본 크기에 대한 퍼센트입니다.  `factor`의 기본값은 100\(퍼센트\)이지만 그보다 크거나 작게 지정할 수 있습니다.  
  
## 설명  
 이전 버전의 Visual C\+\+의 컴파일러에서는 각각 제한이 있는 별개의 몇 가지 힙을 사용했습니다.  그러나 지금은 컴파일러에서 필요에 따라 동적으로 힙의 크기를 전체 힙 크기 한계까지 늘리기 때문에 미리 컴파일된 헤더를 생성하기 위해 고정 크기 버퍼만 필요합니다.  따라서 **\/Zm** 컴파일러 옵션은 자주 사용되지 않습니다.  
  
 **\/Zm** 컴파일러 옵션을 사용하는 경우 컴파일러가 힙 공간을 벗어나 실행되고 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 오류 메시지를 표시하면 너무 많은 메모리를 예약한 것일 수 있습니다.  **\/Zm** 옵션 제거를 고려하십시오.  컴파일러에서 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 오류 메시지가 발생하면 관련 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 메시지에 **\/Zm** 컴파일러 옵션을 사용하여 컴파일할 때 사용할 `factor` 인수가 표시됩니다.  
  
 다음 표에서는 미리 컴파일된 헤더 버퍼의 기본 크기를 75MB로 가정할 경우 `factor` 인수가 메모리 할당 제한에 어떠한 영향을 미치는지를 보여 줍니다.  
  
|`factor`의 값|메모리 할당 제한|  
|-----------------|---------------|  
|10|7.5MB|  
|100|75MB|  
|200|150MB|  
|1000|750MB|  
|2000|1500MB|  
  
## 메모리 할당 제한을 설정하는 기타 방법  
  
#### Visual Studio 개발 환경에서 \/Zm 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  탐색 창에서 **구성 속성**, **C\/C\+\+**, **명령줄**을 선택합니다.  
  
3.  **추가 옵션** 상자에 **\/Zm** 컴파일러 옵션을 입력합니다.  
  
#### 프로그래밍 방식으로 \/Zm 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)