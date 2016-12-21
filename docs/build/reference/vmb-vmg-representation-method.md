---
title: "/vmb, /vmg(표시 메서드) | Microsoft Docs"
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
  - "/vmb"
  - "/vmg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmb 컴파일러 옵션[C++]"
  - "/vmg 컴파일러 옵션[C++]"
  - "표시 메서드 컴파일러 옵션[C++]"
  - "vmb 컴파일러 옵션[C++]"
  - "-vmb 컴파일러 옵션[C++]"
  - "vmg 컴파일러 옵션[C++]"
  - "-vmg 컴파일러 옵션[C++]"
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /vmb, /vmg(표시 메서드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 클래스 멤버에 대한 포인터를 표시하기 위해 사용하는 메서드를 선택합니다.  
  
 클래스 멤버에 대한 포인터를 선언하기 전에 클래스를 정의하는 경우 **\/vmb**를 사용합니다.  
  
 클래스를 정의하기 전에 클래스 멤버에 대한 포인터를 선언해야 하는 경우 **\/vmg**를 사용합니다.  이 옵션은 서로를 참조하는 서로 다른 두 개의 클래스에서 멤버를 정의하는 경우에 필요합니다.  이러한 상호 참조 클래스의 경우에는 클래스가 정의되기 전에 참조되어야 합니다.  
  
## 구문  
  
```  
/vmb  
/vmg  
```  
  
## 설명  
 코드에서 [pointers\_to\_members](../../preprocessor/pointers-to-members.md) 또는 [상속 키워드](../../cpp/inheritance-keywords.md)를 사용하여 포인터 표시를 지정할 수도 있습니다.  
  
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