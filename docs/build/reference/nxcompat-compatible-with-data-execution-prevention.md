---
title: "/NXCOMPAT(데이터 실행 방지 기능과 호환) | Microsoft Docs"
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
  - "/NXCOMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NXCOMPAT 링커 옵션"
  - "NXCOMPAT 링커 옵션"
  - "-NXCOMPAT 링커 옵션"
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NXCOMPAT(데이터 실행 방지 기능과 호환)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 파일이 Windows 데이터 실행 방지 기능과 호환되는지 테스트되었음을 나타냅니다.  
  
## 구문  
  
```  
/NXCOMPAT[:NO]  
```  
  
## 설명  
 **\/NXCOMPAT**는 기본적으로 사용됩니다.  
  
 **\/NXCOMPAT:NO**를 사용하여 실행 파일이 데이터 실행 방지 기능과 호환되지 않음을 명시적으로 지정할 수 있습니다.  
  
 데이터 실행 방지 기능에 대한 자세한 내용은 다음 문서를 참조하십시오.  
  
-   [데이터 실행 방지 \(DEP\) 기능에 대한 자세한 내용](http://go.microsoft.com/fwlink/?LinkID=157771)은 Microsoft 도움말 및 지원 웹 사이트에서 참조하십시오.  
  
-   [데이터 실행 방지](http://go.microsoft.com/fwlink/?LinkID=157770) 는 MSDN 웹 사이트에서 참조하십시오.  
  
-   [데이터 실행 방지 \(Windows Embedded\)](http://go.microsoft.com/fwlink/?LinkID=157768)는  MSDN 웹 사이트에서 참조하십시오.  
  
### Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)