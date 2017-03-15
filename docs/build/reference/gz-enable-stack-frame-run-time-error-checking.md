---
title: "/GZ(스택 프레임 런타임 오류 검사 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gz"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GZ 컴파일러 옵션[C++]"
  - "디버그 빌드, 릴리스 빌드 오류 catch"
  - "GZ 컴파일러 옵션[C++]"
  - "-GZ 컴파일러 옵션[C++]"
  - "릴리스 빌드 오류"
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /GZ(스택 프레임 런타임 오류 검사 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/RTC\(런타임 오류 검사\)](../../build/reference/rtc-run-time-error-checks.md) 옵션과 동일한 작업을 수행합니다.  사용되지 않습니다.  
  
## 구문  
  
```  
/GZ  
```  
  
## 설명  
 **\/GZ**는 최적화되지 않은 빌드\([\/Od\(디버그 비활성화\)](../../build/reference/od-disable-debug.md)\)에만 사용됩니다.  
  
 **\/GZ**는 사용되지 않으며 대신 [\/RTC\(런타임 오류 검사\)](../../build/reference/rtc-run-time-error-checks.md)를 사용합니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
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