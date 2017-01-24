---
title: "/GA(Windows 응용 프로그램 최적화) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA 컴파일러 옵션[C++]"
  - "GA 컴파일러 옵션[C++]"
  - "-GA 컴파일러 옵션[C++]"
  - "Windows 최적화 컴파일러 옵션"
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GA(Windows 응용 프로그램 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

TLS\(스레드 로컬 저장소\) 변수에 액세스하기 위한 .exe 파일의 코드를 더 효율적으로 만들 수 있습니다.  
  
## 구문  
  
```  
/GA  
```  
  
## 설명  
 **\/GA**는 Windows 기반 프로그램에서 [\_\_declspec\(thread\)](../../cpp/declspec.md)로 선언된 데이터에 액세스하는 속도를 빠르게 합니다.  이 옵션을 사용하면 [\_\_tls\_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) 매크로는 0으로 가정됩니다.  
  
 **\/GA**를 DLL에 사용하면 불량 코드가 생성됩니다.  
  
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