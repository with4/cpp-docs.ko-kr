---
title: "이전 버전의 런타임에서 C++ /clr 응용 프로그램 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "app.config 파일, 지정된 런타임 버전"
  - "응용 프로그램 배포[C++], 지정된 런타임 버전"
  - "응용 프로그램[C++], 지정된 런타임 버전"
  - "이전 버전과의 호환성[C++], 지정된 런타임 버전"
  - "공용 언어 런타임[C++], 지정된 버전"
  - "호환성[C++], 지정된 런타임 버전"
  - "응용 프로그램 배포[C++], 지정된 런타임 버전"
  - "버전[C++]"
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 이전 버전의 런타임에서 C++ /clr 응용 프로그램 실행
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

별도로 지정 하지 않으면 Visual C\+\+.NET Framework 응용 프로그램 응용 프로그램을 빌드하려면 컴파일러를 사용 하 여 공용 언어 런타임 \(CLR\) 버전에서 실행 되도록 빌드됩니다.  그러나 한 버전의 런타임이 필요한 기능을 제공 합니다. 다른 버전에서 실행 되도록 빌드한.exe 응용 프로그램입니다.  
  
 이 작업을 수행 하려면 런타임 버전 정보를 포함 하는 app.config 파일을 제공 된 `supportedRuntime` 태그.  
  
 런타임에 폼의 이름을 app.config 파일이 있어야 합니다.  *filename.ext*.config, 위치  *filename.ext* 응용 프로그램을 시작한 실행 파일의 이름 및 실행 파일과 같은 디렉터리에 있어야 합니다.  예를 들어, 응용 프로그램 이름이 TestApp.exe 이면 app.config 파일 TestApp.exe.config 지정 됩니다.  
  
 둘 이상의 런타임 버전을 지정 하 고 두 개 이상의 런타임 버전이 설치 되어 있는 컴퓨터에서 응용 프로그램을 실행 하는 경우 응용 프로그램 구성 파일에 지정 된 및 설치 된 첫 번째 버전을 사용 합니다.  
  
 자세한 내용은 [How to: Configure an App to Target a .NET Framework Version](http://msdn.microsoft.com/ko-kr/5247b307-89ca-417b-8dd0-e8f9bd2f4717)을 참조하십시오.  
  
 Visual C\+\+ 빌드된 응용 프로그램은 CLR 버전 1.1 또는 버전 1.0에서 실행할 컴파일러를 사용 하 여 컴파일해야  [\/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## 참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)