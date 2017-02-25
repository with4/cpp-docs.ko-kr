---
title: "/E(stdout으로 전처리) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/E 컴파일러 옵션[C++]"
  - "-E 컴파일러 옵션[C++]"
  - "전처리기 출력"
  - "전처리기 출력, 표준 출력에 복사"
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /E(stdout으로 전처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C와 C\+\+ 소스 파일을 전처리하고 전처리된 파일을 표준 출력 장치에 복사합니다.  
  
## 구문  
  
```  
/E  
```  
  
## 설명  
 이 처리 과정에서 모든 전처리기 지시문이 실행되고 매크로가 확장되며 주석이 제거됩니다.  전처리된 결과에 주석을 보존하려면 [\/C\(전처리 중에 주석 유지\)](../../build/reference/c-preserve-comments-during-preprocessing.md) 옵션을 함께 사용하십시오.  
  
 **\/E** 옵션을 사용하면 포함된 파일의 시작과 끝에 그리고 조건적 컴파일을 위해 전처리기 지시문에 의해 제거된 줄에 `#line` 지시문이 추가됩니다.  이 지시문은 전처리된 파일의 행 번호를 다시 지정합니다.  따라서 프로세스의 뒷 단계에서 발생한 오류는 전처리된 파일의 줄이 아닌 원본 소스 파일의 줄 번호를 참조합니다.  
  
 **\/E** 옵션을 사용하면 컴파일되지 않습니다.  컴파일에 필요한 사전 처리된 파일을 다시 전송해야 합니다.  또한 **\/E**를 사용하면 **\/FA**, **\/Fa** 및 **\/Fm** 옵션을 사용해도 출력 파일이 생성되지 않습니다.  자세한 내용은 [\/FA, \/Fa\(목록 파일\)](../../build/reference/fa-fa-listing-file.md) 및 [\/Fm\(맵 파일 이름 지정\)](../../build/reference/fm-name-mapfile.md)를 참조하십시오.  
  
 `#line` 지시문을 사용하지 않으려면 [\/EP\(\#line 지시문 없이 stdout로 전처리\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 옵션을 대신 사용합니다.  
  
 전처리된 출력을 `stdout` 대신 파일로 보내려면 [\/P\(파일 전처리\)](../../build/reference/p-preprocess-to-a-file.md) 옵션을 사용합니다.  
  
 `#line` 지시문을 사용하지 않고 전처리된 출력을 파일로 보내려면 **\/P**와 **\/EP**를 함께 사용합니다.  
  
 **\/E** 옵션을 사용할 경우에는 미리 컴파일된 헤더를 사용할 수 없습니다.  
  
 개별 파일로 전처리를 할 때 토큰 뒤의 공백은 제외됩니다.  이로 인해 잘못된 프로그램이 되거나 의도하지 않은 결과가 생길 수 있습니다.  다음 프로그램은 제대로 컴파일됩니다.  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 그러나 다음과 같이 컴파일하면  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 test2.cpp의 `int main`이 잘못되어 `intmain`이 됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄은 `ADD.C`를 전처리하고 주석을 유지하며, `#line` 지시문을 추가하고 표준 출력 장치에 결과를 표시합니다.  
  
```  
CL /E /C ADD.C  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)