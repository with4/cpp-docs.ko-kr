---
title: "/J(부호 없는 기본 문자 형식) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned"
  - "VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned"
  - "/j"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/J 컴파일러 옵션[C++]"
  - "char 데이터 형식"
  - "부호 없는 기본 문자 형식"
  - "기본, char 형식"
  - "J 컴파일러 옵션[C++]"
  - "-J 컴파일러 옵션[C++]"
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /J(부호 없는 기본 문자 형식)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 `char` 형식을 `signed char`에서 `unsigned char`로 변경하고, `char` 형식이 `int` 형식으로 확장되는 경우에는 0 확장합니다.  
  
## 구문  
  
```  
/J  
```  
  
## 설명  
 `char` 값이 명시적으로 signed로 선언되면, **\/J** 옵션은 이 값에 영향을 주지 않으며, 이 값이 `int` `signed` 형식으로 확장되는 경우에는 부호가 확장됩니다.  
  
 **\/J** 옵션을 사용하면 `_CHAR_UNSIGNED`를 정의할 수 있습니다. 이를 LIMITS.h 파일에서 `#ifndef`와 함께 사용하여 기본 `char` 형식의 범위를 정의할 수 있습니다.  
  
 ANSI C 및 C\+\+에서는 `char` 형식을 특별하게 구현할 필요가 없습니다.  이 옵션은 영어 이외의 언어로 번역될 문자 데이터 작업에서 유용하게 사용될 수 있습니다.  
  
> [!NOTE]
>  이 컴파일러 옵션을 사용 하 여 ATL\/MFC를 사용 하 여 오류가 생성 될 수 있습니다.  이 오류를 정의 하 여 사용할 수 없게 되지만  `_ATL_ALLOW_CHAR_UNSIGNED` ,이 해결 방법은 지원 되지 않으며 항상 작동 하지 않을 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  프로젝트 **속성 페이지** 대화 상자에서 **구성 속성** 아래의 왼쪽 창에서 **C\/C\+\+**을 확장한 다음 **명령줄**을 선택합니다.  
  
3.  **추가 옵션** 창에 **\/J** 컴파일러 옵션을 지정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)