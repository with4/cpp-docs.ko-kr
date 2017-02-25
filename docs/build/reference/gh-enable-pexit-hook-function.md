---
title: "/GH(_pexit 후크 함수 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_pexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh 컴파일러 옵션[C++]"
  - "_pexit 함수"
  - "Gh 컴파일러 옵션[C++]"
  - "-Gh 컴파일러 옵션[C++]"
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /GH(_pexit 후크 함수 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 메서드나 함수의 끝에서 `_pexit`  함수를 호출합니다.  
  
## 구문  
  
```  
/GH  
```  
  
## 설명  
 `_pexit`  함수는 라이브러리의 일부가 아니며 `_pexit`에 대한 정의는 사용자가 결정합니다.  
  
 `_pexit`를 명시적으로 호출하지 않는 경우 프로토타입을 제공하지 않아도 됩니다.  이 함수는 다음과 같은 프로토타입을 갖고 있는 것처럼 나타나야 하며, 시작 시 모든 레지스터의 내용을 푸시하고 종료 시 변경되지 않은 내용을 팝해야 합니다.  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit`는 `_penter`와 비슷합니다. `_pexit` 함수를 작성하는 방법에 대한 예제는 [\/Gh\(\_penter 후크 함수 사용\)](../../build/reference/gh-enable-penter-hook-function.md)를 참조하십시오.  
  
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