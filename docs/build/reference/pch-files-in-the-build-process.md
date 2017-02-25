---
title: "빌드 프로세스의 PCH 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 빌드 프로세스"
  - "메이크파일, 빌드 프로세스의 PCH 파일"
  - "PCH 파일, 빌드 프로세스"
ms.assetid: ebb4b368-8a11-4009-b347-01e79af02fbc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 빌드 프로세스의 PCH 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

소프트웨어 프로젝트의 코드 베이스는 대개 여러 개의 C 또는 C\+\+ 소스 파일, 개체 파일, 라이브러리 및 헤더 파일에 들어 있습니다.  일반적으로 메이크파일은 이러한 요소들을 결합하여 실행 파일로 만듭니다.  다음 그림은 미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조를 보여 줍니다.  이 다이어그램에 있는 NMAKE 매크로 이름과 파일 이름은 [PCH용 샘플 메이크파일](../../build/reference/sample-makefile-for-pch.md) 및 [PCH에 대한 예제 코드](../../build/reference/example-code-for-pch.md)의 예제 코드에 있는 것과 일치합니다.  
  
 이 그림에서는 세 개의 다이어그램 장치를 사용하여 빌드 프로세스의 흐름을 보여 줍니다.  명명된 사각형은 각 파일 또는 매크로를 나타내며, 세 개의 매크로는 하나 이상의 파일을 나타냅니다.  회색으로 표시된 영역은 각 컴파일 또는 링크 동작을 나타냅니다.  화살표는 컴파일 또는 링크 프로세스 중에 결합되는 파일 및 매크로를 보여 줍니다.  
  
 ![미리 컴파일된 헤더 파일을 사용하는 메이크파일](../../build/reference/media/vc30ow1.png "vc30OW1")  
미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조  
  
 다이어그램의 맨 위쪽부터 보면, STABLEHDRS와 BOUNDRY는 모두 다시 컴파일하지 않아도 될 것 같은 파일을 나열하는 NMAKE 매크로입니다.  이 파일들은 다음과 같은 명령 문자열을 사용하여 컴파일됩니다.  
  
```  
CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp  
```  
  
 단, 미리 컴파일된 헤더 파일\(STABLE.pch\)이 없거나, 두 매크로에 나열된 파일을 변경하는 경우에만 수행됩니다.  두 경우 모두, 미리 컴파일된 헤더 파일에는 STABLEHDRS 매크로에 나열된 파일의 코드만 포함하게 됩니다.  미리 컴파일되기를 원하는 마지막 파일은 BOUNDRY 매크로에 나열합니다.  
  
 이 매크로에 나열하는 파일들은 헤더 파일일 수도 있고 C 또는 C\+\+ 소스 파일일 수도 있습니다. 하나의 .pch 파일을 C 및 C\+\+ 모듈 모두와 함께 사용할 수는 없습니다. **hdrstop** 매크로를 사용하여 BOUNDRY 파일 내의 일부 지점에서 미리 컴파일하는 작업을 중지시킬 수 있습니다.  자세한 내용은 [hdrstop](../../preprocessor/hdrstop.md)을 참조하십시오.  
  
 계속해서 다이어그램의 밑 부분을 보면, APPLIB.obj는 최종 응용 프로그램에 사용되는 지원 코드를 나타냅니다.  이 코드는 APPLIB.cpp와 UNSTABLEHDRS 매크로에 나열되는 파일 및 미리 컴파일된 헤더에서 미리 컴파일된 코드를 기초로 만들어집니다.  
  
 MYAPP.obj는 최종 응용 프로그램을 나타냅니다.  이 코드는 MYAPP.cpp와 UNSTABLEHDRS 매크로에 나열되는 파일 및 미리 컴파일된 헤더에서 미리 컴파일된 코드를 기초로 만들어집니다.  
  
 마지막으로, OBJS 매크로에 나열된 파일들\(APPLIB.obj 및 MYAPP.obj\)을 링크하면 실행 파일\(MYAPP.EXE\)이 만들어집니다.  
  
 이 그림에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [PCH용 샘플 메이크파일](../../build/reference/sample-makefile-for-pch.md)  
  
-   [PCH에 대한 예제 코드](../../build/reference/example-code-for-pch.md)  
  
## 참고 항목  
 [프로젝트에 미리 컴파일된 헤더 사용](../../build/reference/using-precompiled-headers-in-a-project.md)