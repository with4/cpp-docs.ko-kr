---
title: "MIDL 속성 페이지: 고급 | Microsoft Docs"
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
  - "VC.Project.VCMidlTool.ErrorCheckBounds"
  - "VC.Project.VCMidlTool.ErrorCheckStubData"
  - "VC.Project.VCMidlTool.ErrorCheckAllocations"
  - "VC.Project.VCMidlTool.CPreprocessOptions"
  - "VC.Project.VCMidlTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCMidlTool.EnableErrorChecks"
  - "VC.Project.VCMidlTool.RedirectOutputAndErrors"
  - "VC.Project.VCMidlTool.ErrorCheckEnumRange"
  - "VC.Project.VCMidlTool.StructMemberAlignment"
  - "VC.Project.VCMidlTool.ErrorCheckRefPointers"
  - "VC.Project.VCMidlTool.ValidateParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MIDL, 속성 페이지"
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MIDL 속성 페이지: 고급
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MIDL** 폴더의 **고급** 속성 페이지에서는 다음과 같은 MIDL 컴파일러 옵션을 지정합니다.  
  
-   오류 검사 사용 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   할당 검사 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   범위 검사 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   열거형 범위 검사 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   참조 포인터 검사 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   스텁 데이터 검사 \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   매개 변수 유효성 검사\([\/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)\) \*  
  
-   구조체 멤버 맞춤 \([\/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388)\)  
  
-   리디렉션된 출력 파일 \([\/o](http://msdn.microsoft.com/library/windows/desktop/aa367351)\)  
  
-   C 전처리 옵션 \([\/cpp\_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318)\)  
  
-   전처리기 정의 해제 \([\/U](http://msdn.microsoft.com/library/windows/desktop/aa367373)\)  
  
 \* \/robust는 Windows 2000 이상의 컴퓨터용으로 빌드할 때만 사용할 수 있습니다.  ATL 프로젝트를 빌드하는 경우 \/robust를 사용하려면 dlldatax.c 파일에서 다음 줄을 변경합니다.  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 **MIDL** 폴더의 **고급** 속성 페이지에 액세스하는 방법에 대한 내용은 [방법: 속성 페이지를 사용하여 프로젝트 속성 지정](../misc/how-to-specify-project-properties-with-property-pages.md)을 참조하십시오.  
  
 C\+\+ 프로젝트의 MIDL 옵션을 프로그래밍 방식으로 액세스하는 방법에 대한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>을 참조하십시오.  
  
## 참고 항목  
 [MIDL 속성 페이지](../ide/midl-property-pages.md)