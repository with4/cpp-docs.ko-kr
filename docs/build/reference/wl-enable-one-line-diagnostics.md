---
title: "/WL(1줄 진단 사용) | Microsoft Docs"
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
  - "/wl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WL 컴파일러 옵션[C++]"
  - "WL 컴파일러 옵션[C++]"
  - "-WL 컴파일러 옵션[C++]"
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WL(1줄 진단 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류나 경고 메시지에 더 자세한 정보를 추가합니다.  
  
## 구문  
  
```  
/WL  
```  
  
## 설명  
 기본적으로 C\+\+ 컴파일러의 오류와 경고 메시지 뒤에는 추가 정보가 새로운 1줄에 나타날 수 있습니다.  명령줄에서 컴파일하면 추가 정보 줄이 오류나 경고 메시지에 추가될 수 있습니다.  이는 사용자가 빌드 출력을 로그 파일에 캡쳐한 후 모든 오류와 경고를 찾기 위해 해당 로그를 처리하는 경우에 유용합니다.  세미콜론으로 추가 줄에서 오류나 경고 메시지를 구분합니다.  
  
 모든 오류와 경고 메시지에 추가 정보 줄이 있는 것은 아닙니다.  다음 코드에서는 추가 정보 줄이 있는 오류가 발생합니다. 이 코드로 **\/WL**이 사용될 경우의 효과를 테스트할 수 있습니다.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
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