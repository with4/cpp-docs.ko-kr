---
title: "연습: 응용 프로그램 로컬 폴더에 Visual C++ 응용 프로그램 배포 | Microsoft Docs"
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
  - "Visual C++ 응용 프로그램 배포"
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 응용 프로그램 로컬 폴더에 Visual C++ 응용 프로그램 배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해당 폴더에 파일을 복사 하 여 Visual C\+\+ 응용 프로그램을 배포 하는 방법에 설명 합니다.  
  
## 사전 요구 사항  
  
-   Visual Studio 설치 된 컴퓨터입니다.  
  
-   Visual C\+\+ 라이브러리가 없는 다른 컴퓨터입니다.  
  
### 응용 프로그램 로컬 폴더에 응용 프로그램을 배포하려면  
  
1.  단계를 실행 하 여 MFC 응용 프로그램 빌드를 만들고 [연습: 설치 프로젝트를 사용하여 Visual C\+\+ 응용 프로그램 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  적절 한 MFC 및 C 런타임 \(CRT\) 라이브러리 파일 복사\-예를 들어,는 x86 플랫폼 및 유니코드 지원, 복사 mfc100u.dll \\Program Files\\Microsoft Visual Studio 10.0\\vc\\redist\\x86\\—and에서 msvcr100.dll 여 MFC 프로젝트의 \\Release\\ 폴더에 붙여넣습니다.  복사 해야 하는 다른 파일에 대 한 자세한 내용은 [재배포할 DLL 확인](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Visual C\+\+ 라이브러리가 없는 두 번째 컴퓨터에서 MFC 응용 프로그램을 실행 합니다.  
  
    1.  \\Release\\ 폴더의 내용을 복사 하 여 두 번째 컴퓨터에서 응용 프로그램 폴더에 있습니다.  
  
    2.  두 번째 컴퓨터에서 응용 프로그램을 실행 합니다.  
  
     응용 프로그램 로컬 폴더에서 Visual C\+\+ 라이브러리를 사용할 수 있기 때문에 응용 프로그램이 성공적으로 실행됩니다.  
  
## 참고 항목  
 [배포 예제](../ide/deployment-examples.md)